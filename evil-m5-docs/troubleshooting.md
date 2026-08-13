# Evil-Cardputer v1.5.4 故障排查

这页优先收录“机器屏幕上真的会遇到”的问题。排查原则：先看 SD、电源、接线、版本和配置，再怀疑硬件损坏。

## `SD Card Error / Evil cannot work without SD card`

你当前机器出现过的提示就是：

```text
SD Card Error
Evil cannot work without SD card
```

### 这代表什么

Evil 启动阶段没有正常挂载/读取 microSD。Evil 的 Portal、图片、音频、配置、脚本、记录等大量功能依赖 SD，所以固件会把这当成关键错误。

### 建议排查顺序

1. **彻底关机**，拔下 microSD，再重新插到底。
2. 把卡插电脑，确认可以正常创建、复制、删除一个测试文件。
3. 检查格式。优先使用 **FAT32 / SDHC**；上游建议最大 16 GB，8 GB 已足够。
4. 检查目录：SD 根目录应该有 `evil` 文件夹。
5. 确认项目资源不是多套了一层目录。例如不要出现 `/Evil-M5Project/evil/...` 才是真正资源的情况。
6. 重新复制上游 `SD-Card-File` 对应资源。
7. 换另一张质量可靠的小容量 SDHC 卡交叉测试。
8. 如果两张确认正常的 FAT32 卡都不识别，再检查卡槽触点、供电、固件版本或设备硬件。

### 正确结构的概念

```text
SD_ROOT/
└─ evil/
   ├─ config/
   ├─ img/
   ├─ audio/
   ├─ sites/
   └─ ...
```

## 开机有 Evil 画面，但图片/声音/Portal 缺失

这通常说明“SD 卡可能已经挂载”，但 `/evil/` 下的资源不完整、路径不对或配置文件指向了不存在的文件。

重点检查：

```text
/evil/img/
/evil/audio/
/evil/sites/
/evil/config/config.txt
```

如果你升级了固件但一直沿用很旧的 SD 资源包，也可能出现固件有新功能、SD 却缺资源的情况。升级固件时最好同步检查上游 `SD-Card-File`。

## 配置重启后不保存

v1.5.4 的主要配置文件路径是：

```text
/evil/config/config.txt
```

检查：

- SD 卡是否只读/损坏；
- `evil/config` 目录是否存在；
- 电脑上是否能正常写入这张卡；
- 是否在保存完成前直接断电；
- 配置文件是否异常为 0 字节。

## Wi‑Fi 扫描不到网络

按这个顺序判断：

1. 确认附近确实有 2.4 GHz Wi‑Fi。
2. 重启后先运行 `Scan WiFi`，不要先开复杂测试模式。
3. 确认 Wi‑Fi 没被其他功能留在异常 AP/Promiscuous 状态；返回主菜单或重启可帮助恢复干净状态。
4. 换位置扫描，排除距离/屏蔽影响。
5. 如果只看不到 5 GHz 网络，这是正常方向：Cardputer ADV 本机 ESP32-S3 不是靠普通 Wi‑Fi 扫描直接获得 5 GHz；5 GHz 扩展看 `ESP32C5 Serial`。

## `ESP32C5 ERROR / No response on UART / Check wiring / power`

v1.5.4 在 `ESP32C5 Serial` 启动检测失败时会明确显示：

```text
ESP32C5 ERROR
No response on UART
Check wiring / power
```

排查：

- ESP32‑C5 是否供电；
- C5 是否刷入与 Evil 串口协议匹配的固件；
- TX/RX 是否接反：一般 A.TX → B.RX，A.RX → B.TX；
- 两端是否共地；
- 串口波特率是否一致；
- 引脚是否被其他外设占用；
- 使用 `Raw monitor` 看是否有原始串口返回。

如果 C5 完全无响应，换天线通常解决不了，因为这是 UART 通信层问题。

## ESP32‑C5 能连接，但 5 GHz 扫描结果为空

先看 `Band (ALL/2G/5G)` 是否选到了预期频段，再确认：

- C5 固件/地区信道支持；
- 目标 AP 是否真的在 5 GHz；
- AP 是否使用当前硬件/固件不支持的信道配置；
- 距离和天线是否合理。

不要把“没有扫到”直接理解为附近没有 5 GHz 网络。

## GPS 没定位

### 完全没有串口数据

优先查：

- `Settings → Switch GPS Pins to: ...`
- TX/RX/GND 接线；
- GPS 模块供电；
- `Set GPS Baudrate` 是否与模块一致。

### 有数据但一直没有 Fix

把设备拿到窗边或室外开阔处，给冷启动一些时间。室内深处、金属遮挡、刚上电都会让首次定位明显变慢。

## UART Shell 乱码

通常不是 Evil“翻译错了”，而是串口参数不一致。检查：

- Baudrate；
- 数据位/停止位/校验位（如果外设有特殊设置）；
- 电平是否兼容；
- GND 是否共地；
- TX/RX 方向。

## SSH Shell 连不上

先把问题拆成四层：

1. Evil 是否已经 `Connect to network` 成功；
2. 是否能在局域网找到目标 IP；
3. 目标服务器 SSH 服务是否开启、端口是否正确；
4. 用户名/密码/服务器认证策略是否允许登录。

`Connection refused` 更像目标端口没服务或被拒绝；超时更像网络不可达/防火墙；认证失败才重点看账号密码。

## `Scan IP Ports` 什么都没发现

可能原因：

- IP 写错；
- 设备不在线；
- Evil 和目标不在可达网段；
- 防火墙丢弃扫描请求；
- 目标服务监听在别的端口；
- Wi‑Fi 客户端隔离导致设备之间不能互访。

“扫描不到端口”不等于机器不存在。

## CCTV Toolkit 找不到房间里的摄像头

这是常见误解。CCTV Toolkit 主要处理**可达的网络摄像头/网络服务**。它很难发现：

- 不联网、只写本地 SD 的针孔摄像头；
- 4G/蜂窝摄像头；
- 只接有线网络且与你不在同一可达网络的摄像头；
- 使用其他专用无线频段的摄像头；
- 完全不广播/不开放可扫描服务的设备。

所以它不能作为“房间里有没有偷拍摄像头”的单一结论工具。

## CSI Radar 提示 `No CSI-Beacon found!`

v1.5.4 的 Single Beacon 模式会寻找名称以 `CSI-Beacon` 开头的 AP。如果没有对应 Beacon，会提示类似：

```text
No CSI-Beacon found!
Flash CSI-Beacon firmware
on any ESP32 (C3/C6/S3)
```

这表示缺少配套 Beacon，不是 Cardputer 的 CSI 芯片坏了。先准备/启动受支持的测试 Beacon，再重试。

## CSI Radar 一直 WAITING / 很容易误报

CSI 是环境感知，容易受多径和环境变化影响。建议先确认 Beacon 信号稳定，并在环境静止时重新校准。门、风扇、人走动、家具移动甚至设备位置改变都可能改变 CSI。

`MOTION` / `PRESENCE` 是算法状态，不是“检测到某个具体人”的身份判定。

## TagTinker ESL 没反应

只对你自己的测试 ESL 排查：

- 价签协议/型号是否兼容；
- 红外发射方向和距离；
- 保存的 Tag/Barcode 是否正确；
- 是否使用了适合该标签尺寸/协议的内容；
- 先用 `Tag Info`、`LED Test` 等低影响功能确认链路，再考虑写入内容。

不要拿商场/超市的实际价签做排障对象。

## 功能运行后菜单/网络状态异常

Evil 的很多功能会切换 Wi‑Fi STA/AP、Promiscuous、ESP‑NOW、DNS/WebServer 等状态。某个复杂功能异常退出后，如果下一个功能表现怪异：

1. 先按 `Backspace` 正常退回主菜单；
2. 停止正在运行的 Portal/扫描/监听；
3. 仍异常就重启 Evil，让 Wi‑Fi/串口状态重新初始化；
4. 再从一个简单功能（如 `Scan WiFi`）验证基础功能。

## 什么时候考虑重新刷固件

下面情况才把“重刷”提到前面：

- SD 已确认正常且资源完整；
- 同一硬件过去能用，现在核心功能普遍异常；
- 升级/烧录过程中断电或报错；
- 版本显示不对；
- 多项基础功能同时异常且重启无效。

不要遇到一个目录缺文件就反复刷 Flash——那类问题通常应该先修 SD 资源。

返回：[新手必读](start-here.md) · [完整菜单](menu.md) · [字段字典](fields.md)
