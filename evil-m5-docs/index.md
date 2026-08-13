# Evil-M5Project / Evil-Cardputer v1.5.4 中文 Wiki

> 适用设备：M5Stack Cardputer / Cardputer ADV 运行 **Evil-Cardputer v1.5.4**。
>
> 本页和本目录以 Evil-M5Project 上游 `Evil-Cardputer-v1-5-4.ino` 为菜单基准。菜单英文保留固件原文，中文放在英文后方，方便拿着机器逐项对照。

## 从这里开始

- [新手必读：安装、SD 卡、开机与按键](start-here.md)
- [v1.5.4 完整主菜单中英对照](menu.md)
- [Wi‑Fi / Portal 基础功能](wifi-core.md)
- [无线扫描、监听与授权测试功能](wifi-radio.md)
- [网络、系统与实用工具](network.md)
- [协议、IoT、ESP32‑C5、TagTinker、CSI Radar](io-iot.md)
- [Settings（设置）完整说明](settings.md)
- [字段字典：SSID / BSSID / RSSI / Channel / NTLMv2 等](fields.md)
- [故障排查：SD Card Error、C5、GPS、网络等](troubleshooting.md)

## 先理解 Evil 的菜单结构

Evil-Cardputer v1.5.4 和 Bruce 的菜单结构不一样：**Evil 的主菜单本身就是一条很长的平铺列表**。v1.5.4 源码中主菜单从 `Scan WiFi` 一直到 `Settings`，共 89 个入口。

为了让中文 Wiki 更好找，本 Wiki 会把它们按“Wi‑Fi 基础 / 无线测试 / 网络工具 / 协议与 IoT / 设置”分成几个页面。**这些分组只是文档导航，不是我擅自修改的实机菜单层级。**

## 风险标识

| 标识 | 含义 |
|---|---|
| 🟢 | 日常、被动查看、本机功能，通常风险较低 |
| 🟡 | 扫描、配置或可能接触敏感数据，只在自己的设备/网络使用 |
| 🟠 | 主动安全测试，会影响目标设备或网络，只用于明确授权环境 |
| 🔴 | 可能中断网络、诱导认证或造成明显干扰，仅限隔离实验室/明确授权测试 |

## 本 Wiki 的写法

每个功能尽量回答四件事：**英文菜单叫什么、中文是什么意思、打开后看什么、什么时候会用到。** 对扫描、状态查看、SSH、文件管理等正常功能会写得更具体；对去认证、伪 DHCP、凭据捕获、SIP Flooding、CIW Zeroclick 等主动安全测试，只解释菜单、字段、结果和合法实验环境，不提供针对第三方网络的攻击步骤。

## 版本提示

Evil-M5Project 更新频率较高。本文档固定以 **Evil-Cardputer v1.5.4（2026）** 为当前基线；如果以后机器升级到 v1.5.5 / v1.6.x，优先以新固件屏幕上的英文菜单为准，再更新本 Wiki。
