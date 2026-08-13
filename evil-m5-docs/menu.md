# Evil-Cardputer v1.5.4 完整主菜单中英对照

> 这一页按上游 `Evil-Cardputer-v1-5-4.ino` 的 `menuItems[]` 顺序整理。**英文不改，中文直接放在英文后面。**
>
> Evil v1.5.4 的主菜单是 89 项平铺长列表，不是 Bruce 那种 15 个一级分类。下面的“分组”只是 Wiki 为了阅读方便建立的导航。

## 实机主菜单树

```text
Evil-Cardputer v1.5.4 Main Menu（主菜单）
├─ Scan WiFi（扫描 Wi‑Fi）
├─ Select Network（选择网络）
├─ Clone & Details（克隆与详情）
├─ Set Wifi SSID（设置 Wi‑Fi SSID）
├─ Set Wifi Password（设置 Wi‑Fi 密码）
├─ Set Mac Address（设置 MAC 地址）
├─ Start Captive Portal（启动强制门户）
├─ Stop Captive Portal（停止强制门户）
├─ Change Portal（切换门户页面）
├─ Check Credentials（查看捕获凭据）
├─ Delete All Creds（删除全部凭据）
├─ Monitor Status（状态监控）
├─ Probe Attack（Probe 响应测试）
├─ Probe Sniffing（Probe 请求监听）
├─ Karma Attack（Karma 测试）
├─ Karma Auto（自动 Karma）
├─ Karma Spear（定向 Karma）
├─ Select Probe（选择 Probe）
├─ Delete Probe（删除 Probe）
├─ Delete All Probes（删除全部 Probe）
├─ Wardriving（无线巡航记录）
├─ Wardriving Master（多节点巡航主机）
├─ Beacon Spam（Beacon 广播测试）
├─ Deauther（去认证测试）
├─ Auto Deauther（自动去认证测试）
├─ Evil Twin（仿冒热点测试）
├─ Handshake Master（握手采集主机）
├─ WiFi Raw Sniffing（Wi‑Fi 原始数据监听）
├─ Sniff Raw Clients（客户端原始帧监听）
├─ Wifi Channel Visualizer（Wi‑Fi 信道可视化）
├─ Client Sniffing and Deauth（客户端监听与断开测试）
├─ Handshake/Deauth Sniffing（握手/去认证监听）
├─ Check Handshakes（检查握手文件）
├─ Wall Of Flipper（Flipper 广播墙）
├─ Connect to network（连接到网络）
├─ SSH Shell（SSH 终端）
├─ Scan IP Ports（扫描主机端口）
├─ Scan Network Hosts（扫描局域网主机）
├─ Scan Network Full（全网段完整扫描）
├─ Scan Network List（查看网络扫描列表）
├─ Web Crawler（网页爬取 / 站点信息采集）
├─ PwnGrid Spam（PwnGrid 广播测试）
├─ Skimmer Detector（可疑蓝牙刷卡器检测）
├─ Mouse Jiggler（鼠标防休眠）
├─ BadUSB（USB HID 自动化）
├─ Bluetooth Keyboard（蓝牙键盘）
├─ Reverse TCP Tunnel（反向 TCP 隧道）
├─ DHCP Starvation（DHCP 地址池耗尽测试）
├─ Rogue DHCP STA（伪 DHCP：STA 模式）
├─ Rogue DHCP AP（伪 DHCP：AP 模式）
├─ Switch DNS（切换 / 重定向 DNS）
├─ Network Hijacking（网络劫持测试）
├─ Detect Printer（探测网络打印机）
├─ File Print（发送文件到打印机）
├─ Check printer status（查看打印机状态）
├─ HoneyPot（蜜罐）
├─ LLM Chat Stream（LLM 流式聊天）
├─ EvilChatMesh（EvilChat Mesh 聊天）
├─ SD on USB（SD 卡 USB 存储）
├─ Responder（LLMNR/NBNS/SMB 响应测试）
├─ WPAD Abuse（WPAD 代理自动发现测试）
├─ Crack NTLMv2（NTLMv2 离线口令验证）
├─ Clean NTLMv2 duplicate（清理重复 NTLMv2 记录）
├─ FileManager（文件管理器）
├─ UART Shell（UART 串口终端）
├─ SIP Scanner（SIP 扫描器）
├─ SIP Enumeration（SIP 枚举）
├─ SIP Message Spoof（SIP 消息伪装测试）
├─ SIP Flooding（SIP 压力测试）
├─ SIP Ring All（SIP 批量响铃测试）
├─ CCTV Toolkit（CCTV 网络摄像头工具箱）
├─ SSDP Poisoner（SSDP 响应欺骗测试）
├─ SkyJack（SkyJack 无线测试）
├─ WiFi Dead Drop（Wi‑Fi 文件投递箱）
├─ BLENameFlood（BLE 名称广播测试）
├─ Wall Of Airtag（AirTag 广播墙）
├─ FindMyEvil（Find My 广播测试）
├─ List UPnP Mapping（查看 UPnP 端口映射）
├─ UPnP NAT（UPnP NAT 映射工具）
├─ LDAPDump（LDAP 域信息导出）
├─ IMSI Catcher（EAP‑SIM IMSI 监听器）
├─ Open Wifi Checker（开放 Wi‑Fi 检查器）
├─ ESP32C5 Serial（ESP32‑C5 串口工具箱）
├─ Aircrack（WPA2 离线口令验证）
├─ Autodiscover Abuse（Autodiscover 安全测试）
├─ CIW Zeroclick（CIW / SSID 注入测试框架）
├─ TagTinker ESL（电子价签 / ESL 工具）
├─ CSI Radar（Wi‑Fi CSI 存在 / 动作雷达）
└─ Settings（设置）
```

## 可点击跳转

### 1–12：Wi‑Fi / Portal 基础

| # | 菜单 | 中文 | 说明 |
|---:|---|---|---|
| 1 | [Scan WiFi](wifi-core.md#scan-wifi) | 扫描 Wi‑Fi | 🟢 扫描周围 AP |
| 2 | [Select Network](wifi-core.md#select-network) | 选择网络 | 🟢 从扫描结果选目标 |
| 3 | [Clone & Details](wifi-core.md#clone-details) | 克隆与详情 | 🟡 查看/复制选中 AP 参数 |
| 4 | [Set Wifi SSID](wifi-core.md#set-wifi-ssid) | 设置 Wi‑Fi SSID | 🟢 设置 Evil 使用的 SSID |
| 5 | [Set Wifi Password](wifi-core.md#set-wifi-password) | 设置 Wi‑Fi 密码 | 🟢 设置密码 |
| 6 | [Set Mac Address](wifi-core.md#set-mac-address) | 设置 MAC 地址 | 🟡 修改本机 Wi‑Fi MAC |
| 7 | [Start Captive Portal](wifi-core.md#start-captive-portal) | 启动强制门户 | 🟠 授权测试 |
| 8 | [Stop Captive Portal](wifi-core.md#stop-captive-portal) | 停止强制门户 | 🟢 停止 Portal |
| 9 | [Change Portal](wifi-core.md#change-portal) | 切换门户页面 | 🟡 选择 SD 中的 Portal |
| 10 | [Check Credentials](wifi-core.md#check-credentials) | 查看捕获凭据 | 🟡 敏感数据 |
| 11 | [Delete All Creds](wifi-core.md#delete-all-creds) | 删除全部凭据 | 🟢 清理本机数据 |
| 12 | [Monitor Status](wifi-core.md#monitor-status) | 状态监控 | 🟢 系统状态 |

### 13–34：无线监听与授权测试

[进入这一组完整说明 →](wifi-radio.md)

`Probe Attack` · `Probe Sniffing` · `Karma Attack` · `Karma Auto` · `Karma Spear` · `Select Probe` · `Delete Probe` · `Delete All Probes` · `Wardriving` · `Wardriving Master` · `Beacon Spam` · `Deauther` · `Auto Deauther` · `Evil Twin` · `Handshake Master` · `WiFi Raw Sniffing` · `Sniff Raw Clients` · `Wifi Channel Visualizer` · `Client Sniffing and Deauth` · `Handshake/Deauth Sniffing` · `Check Handshakes` · `Wall Of Flipper`

### 35–64：网络、系统与实用工具

[进入这一组完整说明 →](network.md)

`Connect to network` · `SSH Shell` · `Scan IP Ports` · `Scan Network Hosts` · `Scan Network Full` · `Scan Network List` · `Web Crawler` · `PwnGrid Spam` · `Skimmer Detector` · `Mouse Jiggler` · `BadUSB` · `Bluetooth Keyboard` · `Reverse TCP Tunnel` · `DHCP Starvation` · `Rogue DHCP STA` · `Rogue DHCP AP` · `Switch DNS` · `Network Hijacking` · `Detect Printer` · `File Print` · `Check printer status` · `HoneyPot` · `LLM Chat Stream` · `EvilChatMesh` · `SD on USB` · `Responder` · `WPAD Abuse` · `Crack NTLMv2` · `Clean NTLMv2 duplicate` · `FileManager`

### 65–88：协议、IoT、5 GHz 与新功能

[进入这一组完整说明 →](io-iot.md)

`UART Shell` · `SIP Scanner` · `SIP Enumeration` · `SIP Message Spoof` · `SIP Flooding` · `SIP Ring All` · `CCTV Toolkit` · `SSDP Poisoner` · `SkyJack` · `WiFi Dead Drop` · `BLENameFlood` · `Wall Of Airtag` · `FindMyEvil` · `List UPnP Mapping` · `UPnP NAT` · `LDAPDump` · `IMSI Catcher` · `Open Wifi Checker` · `ESP32C5 Serial` · `Aircrack` · `Autodiscover Abuse` · `CIW Zeroclick` · `TagTinker ESL` · `CSI Radar`

### 89：Settings

[Settings（设置）完整二级菜单 →](settings.md)

## 重要提醒

菜单里同时混有日常工具、被动扫描、敏感数据工具和主动安全测试。**菜单出现并不等于可以在任意网络上使用。** 对会影响连接、网络分配、认证流程或通信服务的功能，只在自己的实验设备、隔离网络或获得明确授权的环境中测试。
