# Evil-M5Project 字段字典

这页不是功能菜单，而是给新手查屏幕上反复出现的英文缩写。建议遇到不懂的字段先来这里找。

## Wi‑Fi 基础

| 字段 | 中文理解 | 你该怎么看 |
|---|---|---|
| `SSID` | Wi‑Fi 网络名称 | 手机 Wi‑Fi 列表里看到的名字 |
| `BSSID` | AP 无线接口 MAC | 常用于唯一标识某个 AP/频段接口 |
| `MAC` | 网络接口硬件地址 | 形如 `AA:BB:CC:DD:EE:FF` |
| `RSSI` | 接收信号强度 | 单位 dBm，通常越接近 0 越强 |
| `Channel` / `Chan` | Wi‑Fi 信道 | 2.4 GHz 常见 1–13/14，取决于地区与硬件 |
| `AP` | Access Point | 无线接入点/热点 |
| `STA` | Station | 连接热点的客户端设备 |
| `Open` | 开放网络 | Wi‑Fi 层不要求常规 WPA 密码，不等于允许使用 |
| `WPA/WPA2` | Wi‑Fi 安全协议 | 决定认证/加密方式的一部分 |
| `EAPOL` | 802.1X/EAP over LAN | WPA/WPA2 握手分析中常见 |
| `Handshake` | 握手数据 | 认证交换记录，不等于明文密码 |
| `PMKID` | WPA 认证相关标识 | 某些离线安全验证中会用到 |

### RSSI 怎么看

只是粗略经验，不是统一标准：

| RSSI | 大致感受 |
|---|---|
| -30 dBm 左右 | 非常强，通常离 AP 很近 |
| -50 dBm 左右 | 很强/稳定 |
| -60 ～ -67 dBm | 一般仍可正常使用 |
| -70 dBm 左右 | 较弱 |
| -80 dBm 以下 | 很弱，容易不稳定 |

天线、方向、人体遮挡、墙体、多径都会让 RSSI 波动。

## Probe / Karma / Portal

| 字段 | 中文理解 |
|---|---|
| `Probe Request` | 客户端询问附近是否存在某个网络的管理帧 |
| `Probe Response` | AP 对 Probe 的响应 |
| `Karma` | 测试客户端是否错误信任其正在寻找的网络 |
| `Captive Portal` | 连接热点后出现的门户/登录网页 |
| `Credentials` / `Creds` | 用户名、口令等认证输入；敏感数据 |
| `Clone` | 把名称/配置复制到 Evil 的测试配置中 |

## IP / 网络扫描

| 字段 | 中文理解 | 示例/说明 |
|---|---|---|
| `IP` | IP 地址 | 如 `192.168.1.20` |
| `Gateway` | 默认网关 | 局域网通往其他网络的出口 |
| `Subnet` / `Netmask` | 子网/掩码 | 决定哪些地址属于本地网段 |
| `DNS` | 域名解析服务器 | 把域名解析成 IP |
| `DHCP` | 自动分配网络参数的协议 | 分配 IP、网关、DNS 等 |
| `Port` | 网络端口 | 如 SSH 22、HTTP 80、HTTPS 443 |
| `TCP` | 面向连接的传输协议 | SSH/HTTP 等大量服务使用 |
| `UDP` | 无连接传输协议 | DNS、发现协议等常见 |
| `Host` | 主机 | 网络中的电脑、NAS、摄像头、路由器等 |
| `NAT` | 网络地址转换 | 家用路由器常用 |
| `UPnP` | 即插即用网络协议族 | 可用于设备发现/NAT 映射 |
| `SSDP` | UPnP 常用发现协议 | 局域网设备发现中常见 |

## SSH / UART

| 字段 | 中文理解 |
|---|---|
| `Host` | 目标服务器 IP/域名 |
| `User` | 登录用户名 |
| `Password` | 登录密码 |
| `Port 22` | SSH 常见默认端口 |
| `UART` | 串口通信接口 |
| `TX` | 发送引脚 |
| `RX` | 接收引脚 |
| `Baudrate` | 串口速率，如 9600/115200 |
| `GND` | 地线；两个串口设备通常需要共地 |

串口最常见接法原则是 **设备 A 的 TX → 设备 B 的 RX，A 的 RX → B 的 TX，GND 共地**。具体电压/引脚仍以模块手册为准。

## GPS / Wardriving

| 字段 | 中文理解 |
|---|---|
| `GPS` | 全球卫星定位系统，实际模块可能兼容多 GNSS |
| `Latitude` | 纬度 |
| `Longitude` | 经度 |
| `Fix` | 是否已经获得有效定位 |
| `Satellites` | 当前参与定位的卫星数量/可见信息 |
| `HDOP` | 水平精度因子，通常越小越好 |
| `NMEA` | GPS 模块常见文本输出协议 |
| `Wigle CSV` | 无线测绘常用的 CSV 记录格式 |

## Windows / 企业网络认证

| 字段 | 中文理解 |
|---|---|
| `LLMNR` | Windows 局域网名称解析机制之一 |
| `NBNS` | NetBIOS 名称服务 |
| `SMB` | Windows 文件共享相关协议 |
| `NTLMv2` | Windows 常见挑战-响应认证协议 |
| `NTLMv2 hash/response` | 认证响应数据，属于敏感安全数据 |
| `WPAD` | Web Proxy Auto-Discovery，代理自动发现 |
| `LDAP` | 目录服务访问协议 |
| `AD` | Active Directory，微软域目录服务 |

注意：Evil 屏幕上所谓 `NTLMv2` 捕获通常不是“已经得到用户明文密码”，而是可用于授权离线强度测试的认证响应数据。

## SIP / VoIP

| 字段 | 中文理解 |
|---|---|
| `SIP` | Session Initiation Protocol，会话发起协议 |
| `PBX` | 企业电话交换/呼叫系统 |
| `Extension` | 分机号 |
| `REGISTER` | SIP 注册动作 |
| `INVITE` | SIP 发起会话/呼叫的常见方法 |
| `Enumeration` | 枚举可见用户/分机/服务信息 |

## BLE / Find My

| 字段 | 中文理解 |
|---|---|
| `BLE` | Bluetooth Low Energy，低功耗蓝牙 |
| `Advertisement` | BLE 广播包 |
| `Beacon` | 周期性广播标识/数据的设备或模式 |
| `AirTag` | Apple Find My 生态中的追踪配件 |
| `Find My` | Apple 的查找网络生态 |

无线广播只能提供设备/协议特征，不应该拿单次扫描结果直接推断具体人员身份。

## ESP32‑C5

| 字段 | 中文理解 |
|---|---|
| `Band ALL/2G/5G` | 扫描/工作频段选择 |
| `Target SSID` | 指定网络名称 |
| `Target BSSID` | 指定 AP MAC |
| `Target INDEX` | 用扫描列表索引选择目标 |
| `Chan SET` | 设置信道集合/当前信道 |
| `Chan ADD` | 加入一个信道 |
| `Chan RESET` | 重置为默认信道配置 |
| `Interval (ms)` | 操作/轮询间隔，毫秒 |
| `History (ms)` | 保留/观察历史时间窗口 |
| `Raw monitor` | 查看 C5 串口原始输出 |

`ESP32C5 Serial` 代表 **Cardputer 通过 UART 控制外部 ESP32‑C5**，不是 S3 本机直接变成 5 GHz 芯片。

## CSI Radar

| 字段 | 中文理解 |
|---|---|
| `CSI` | Channel State Information，信道状态信息 |
| `Single Beacon` | 单个 CSI Beacon 模式 |
| `Multi Beacons` | 多 Beacon 模式 |
| `CALIBRATING` | 正在采集环境基线 |
| `MOTION` | 算法检测到较明显变化 |
| `PRESENCE` | 算法判断存在持续变化特征 |
| `T:` | Turbulence/扰动指标 |
| `S:` | Sensitivity/灵敏度 |
| `BPM:` | 算法显示的周期性估计值，不能当医疗测量 |

CSI 很容易受墙体、人体、家具移动、风扇、门、反射和多径影响；它是无线感知实验，不是精确身份识别雷达。

## TagTinker ESL

| 字段 | 中文理解 |
|---|---|
| `ESL` | Electronic Shelf Label，电子货架标签/电子价签 |
| `Tag` | 一个价签设备 |
| `Barcode` | 项目用于识别/保存目标价签的条码标识 |
| `Push Text` | 向授权价签写入/推送文本 |
| `Push Image` | 推送图片 |
| `Broadcast` | 广播给多个/全部兼容价签 |
| `Raw Frame` | 原始协议帧测试 |

商场/超市的 ESL 是第三方生产设备，不要用 TagTinker 修改不属于你的价签。

返回：[Evil v1.5.4 完整菜单](menu.md)。
