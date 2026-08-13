# Evil-Cardputer v1.5.4 新手必读

这页按“刚拿到 Cardputer ADV、刚刷好 Evil”的顺序写。

## 1. 开机先看版本

正常启动时会看到类似：

```text
Evil-Cardputer
By 7h30th3r0n3
v1.5.4 2026
```

本 Wiki 当前就是按 **v1.5.4** 整理的。

## 2. Evil 必须准备 microSD

Evil 和 Bruce 最大的使用差异之一，是 Evil 对 SD 卡资源依赖很强。上游要求 SD 卡使用 **FAT32 / SDHC**，并建议容量不超过 16 GB；8 GB 已足够放项目资源。

SD 卡根目录需要有 `evil` 文件夹，典型结构可以理解成：

```text
SD Card
└─ evil/
   ├─ img/
   ├─ audio/
   ├─ sites/
   ├─ config/
   └─ ...
```

不要把 `img`、`sites` 等文件夹直接散放在 SD 根目录。新版项目要求它们位于 `/evil/` 下。

## 3. 你照片里的 `SD Card Error` 是什么意思

如果开机显示：

```text
SD Card Error
Evil cannot work without SD card
```

意思不是 Wi‑Fi 坏了，也不是固件一定刷坏了，而是 **Evil 没有成功挂载 SD 卡**。按下面顺序排查：

1. 关机后重新插拔 microSD，确认卡完全到位。
2. 在电脑上确认这张卡能正常读写。
3. 优先使用 FAT32 格式；不要用 exFAT/NTFS 当作首选。
4. 确认 SD 根目录存在 `/evil/`，并且项目资源已经复制进去。
5. 如果仍报错，用另一张容量较小、质量可靠的 SDHC 卡交叉测试。
6. 若卡能在电脑读取但 Evil 始终无法识别，再考虑卡槽接触、格式化方式或固件/硬件问题。

## 4. 安装方式怎么选

### M5Burner

对新手最省事。选择对应 Cardputer 的 Evil 固件烧录，然后把项目的 SD 资源放到卡上的 `/evil/`。

### Arduino IDE 自行编译

适合需要改源码的人。Cardputer 构建时要特别注意 Flash / Partition 配置以及项目依赖库。新手如果只是使用功能，不建议一开始就从源码编译排错。

### M5Launcher

如果你已经在 Cardputer ADV 上使用 M5Launcher，也可以把它当作固件管理入口；但 **Evil 的 SD 卡资源仍然需要正确准备**，Launcher 不能替代 `/evil/` 资源目录。

## 5. 菜单怎么操作

Evil 的 Cardputer 界面大量列表使用相同的键位逻辑：

| 按键 | 常见作用 |
|---|---|
| `;` | 向上 |
| `.` | 向下 |
| `Enter` | 进入 / 确认 |
| `Backspace` | 返回 / 退出 |
| `,` / `/` | 某些参数页减小 / 增大 |

不同功能可能有额外快捷键，屏幕底部通常会显示提示；遇到本页没写到的，以屏幕提示为准。

## 6. 第一次开机建议先用哪些功能

建议先从这些低风险功能熟悉界面：

- `Scan WiFi（扫描 Wi‑Fi）`：看看周围 AP、SSID、信号强度和频道。
- `Select Network（选择网络）`：在扫描结果中选择一个网络供后续查看。
- `Monitor Status（状态监控）`：查看运行状态、内存、电量等。
- `Connect to network（连接到网络）`：连接你自己的 Wi‑Fi。
- `Scan IP Ports（扫描主机端口）` / `Scan Network Hosts（扫描局域网主机）`：只扫描自己管理的局域网。
- `FileManager（文件管理器）`：查看 SD 文件。
- `Settings（设置）`：调整亮度、声音、GPS、启动项和 CPU 频率。

## 7. 先不要随便点的功能

看到下面这些名字时不要把它们理解为“普通扫描”：

`Deauther`、`Auto Deauther`、`Evil Twin`、`DHCP Starvation`、`Rogue DHCP`、`Responder`、`WPAD Abuse`、`SIP Flooding`、`SSDP Poisoner`、`IMSI Catcher`、`Autodiscover Abuse`、`CIW Zeroclick` 等都属于主动安全测试或敏感协议测试。

它们可能中断连接、改变网络行为、诱导客户端认证或收集认证数据。只在你自己的实验设备、隔离测试网或已获得明确授权的环境使用。

## 8. Cardputer ADV 与 5 GHz

Cardputer ADV 本机 ESP32-S3 的 Wi‑Fi 主要用于 2.4 GHz。Evil v1.5.4 的 `ESP32C5 Serial（ESP32‑C5 串口工具箱）` 是通过外接 ESP32‑C5 扩展 2.4/5 GHz 扫描与相关能力；它不是“换根天线就让 S3 直接支持 5 GHz”。

下一步直接看：[v1.5.4 完整主菜单中英对照](menu.md)。
