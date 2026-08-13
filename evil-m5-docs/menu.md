# Evil-Cardputer v1.5.4 完整主菜单中英对照

> 这一页按上游 `Evil-Cardputer-v1-5-4.ino` 的 `menuItems[]` 顺序整理。**英文保持实机原文，中文直接放在英文后面。**
>
> Evil v1.5.4 的主菜单是 **89 项平铺长列表**，不是 Bruce 那种 15 个一级分类。下面的“分组”只是 Wiki 为了阅读方便建立的导航。

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

## 89 项全部可点击跳转

> 点击英文菜单名或中文名称，都会直接进入对应功能的详细说明位置。

### 1–12：Wi‑Fi / Portal 基础

| # | English / 英文 | 中文 |
|---:|---|---|
| 1 | [Scan WiFi](wifi-core.md#scan-wifi) | [扫描 Wi‑Fi](wifi-core.md#scan-wifi) |
| 2 | [Select Network](wifi-core.md#select-network) | [选择网络](wifi-core.md#select-network) |
| 3 | [Clone & Details](wifi-core.md#clone-details) | [克隆与详情](wifi-core.md#clone-details) |
| 4 | [Set Wifi SSID](wifi-core.md#set-wifi-ssid) | [设置 Wi‑Fi SSID](wifi-core.md#set-wifi-ssid) |
| 5 | [Set Wifi Password](wifi-core.md#set-wifi-password) | [设置 Wi‑Fi 密码](wifi-core.md#set-wifi-password) |
| 6 | [Set Mac Address](wifi-core.md#set-mac-address) | [设置 MAC 地址](wifi-core.md#set-mac-address) |
| 7 | [Start Captive Portal](wifi-core.md#start-captive-portal) | [启动强制门户](wifi-core.md#start-captive-portal) |
| 8 | [Stop Captive Portal](wifi-core.md#stop-captive-portal) | [停止强制门户](wifi-core.md#stop-captive-portal) |
| 9 | [Change Portal](wifi-core.md#change-portal) | [切换门户页面](wifi-core.md#change-portal) |
| 10 | [Check Credentials](wifi-core.md#check-credentials) | [查看捕获凭据](wifi-core.md#check-credentials) |
| 11 | [Delete All Creds](wifi-core.md#delete-all-creds) | [删除全部凭据](wifi-core.md#delete-all-creds) |
| 12 | [Monitor Status](wifi-core.md#monitor-status) | [状态监控](wifi-core.md#monitor-status) |

### 13–34：无线监听、Wardriving 与授权测试

| # | English / 英文 | 中文 |
|---:|---|---|
| 13 | [Probe Attack](wifi-radio.md#probe-attack) | [Probe 响应测试](wifi-radio.md#probe-attack) |
| 14 | [Probe Sniffing](wifi-radio.md#probe-sniffing) | [Probe 请求监听](wifi-radio.md#probe-sniffing) |
| 15 | [Karma Attack](wifi-radio.md#karma-attack) | [Karma 测试](wifi-radio.md#karma-attack) |
| 16 | [Karma Auto](wifi-radio.md#karma-auto) | [自动 Karma](wifi-radio.md#karma-auto) |
| 17 | [Karma Spear](wifi-radio.md#karma-spear) | [定向 Karma](wifi-radio.md#karma-spear) |
| 18 | [Select Probe](wifi-radio.md#select-probe) | [选择 Probe](wifi-radio.md#select-probe) |
| 19 | [Delete Probe](wifi-radio.md#delete-probe) | [删除 Probe](wifi-radio.md#delete-probe) |
| 20 | [Delete All Probes](wifi-radio.md#delete-all-probes) | [删除全部 Probe](wifi-radio.md#delete-all-probes) |
| 21 | [Wardriving](wifi-radio.md#wardriving) | [无线巡航记录](wifi-radio.md#wardriving) |
| 22 | [Wardriving Master](wifi-radio.md#wardriving-master) | [多节点巡航主机](wifi-radio.md#wardriving-master) |
| 23 | [Beacon Spam](wifi-radio.md#beacon-spam) | [Beacon 广播测试](wifi-radio.md#beacon-spam) |
| 24 | [Deauther](wifi-radio.md#deauther) | [去认证测试](wifi-radio.md#deauther) |
| 25 | [Auto Deauther](wifi-radio.md#auto-deauther) | [自动去认证测试](wifi-radio.md#auto-deauther) |
| 26 | [Evil Twin](wifi-radio.md#evil-twin) | [仿冒热点测试](wifi-radio.md#evil-twin) |
| 27 | [Handshake Master](wifi-radio.md#handshake-master) | [握手采集主机](wifi-radio.md#handshake-master) |
| 28 | [WiFi Raw Sniffing](wifi-radio.md#wifi-raw-sniffing) | [Wi‑Fi 原始数据监听](wifi-radio.md#wifi-raw-sniffing) |
| 29 | [Sniff Raw Clients](wifi-radio.md#sniff-raw-clients) | [客户端原始帧监听](wifi-radio.md#sniff-raw-clients) |
| 30 | [Wifi Channel Visualizer](wifi-radio.md#wifi-channel-visualizer) | [Wi‑Fi 信道可视化](wifi-radio.md#wifi-channel-visualizer) |
| 31 | [Client Sniffing and Deauth](wifi-radio.md#client-sniffing-and-deauth) | [客户端监听与断开测试](wifi-radio.md#client-sniffing-and-deauth) |
| 32 | [Handshake/Deauth Sniffing](wifi-radio.md#handshake-deauth-sniffing) | [握手/去认证监听](wifi-radio.md#handshake-deauth-sniffing) |
| 33 | [Check Handshakes](wifi-radio.md#check-handshakes) | [检查握手文件](wifi-radio.md#check-handshakes) |
| 34 | [Wall Of Flipper](wifi-radio.md#wall-of-flipper) | [Flipper 广播墙](wifi-radio.md#wall-of-flipper) |

### 35–64：网络、系统与实用工具

| # | English / 英文 | 中文 |
|---:|---|---|
| 35 | [Connect to network](network.md#connect-to-network) | [连接到网络](network.md#connect-to-network) |
| 36 | [SSH Shell](network.md#ssh-shell) | [SSH 终端](network.md#ssh-shell) |
| 37 | [Scan IP Ports](network.md#scan-ip-ports) | [扫描主机端口](network.md#scan-ip-ports) |
| 38 | [Scan Network Hosts](network.md#scan-network-hosts) | [扫描局域网主机](network.md#scan-network-hosts) |
| 39 | [Scan Network Full](network.md#scan-network-full) | [全网段完整扫描](network.md#scan-network-full) |
| 40 | [Scan Network List](network.md#scan-network-list) | [查看网络扫描列表](network.md#scan-network-list) |
| 41 | [Web Crawler](network.md#web-crawler) | [网页爬取 / 站点信息采集](network.md#web-crawler) |
| 42 | [PwnGrid Spam](network.md#pwngrid-spam) | [PwnGrid 广播测试](network.md#pwngrid-spam) |
| 43 | [Skimmer Detector](network.md#skimmer-detector) | [可疑蓝牙刷卡器检测](network.md#skimmer-detector) |
| 44 | [Mouse Jiggler](network.md#mouse-jiggler) | [鼠标防休眠](network.md#mouse-jiggler) |
| 45 | [BadUSB](network.md#badusb) | [USB HID 自动化](network.md#badusb) |
| 46 | [Bluetooth Keyboard](network.md#bluetooth-keyboard) | [蓝牙键盘](network.md#bluetooth-keyboard) |
| 47 | [Reverse TCP Tunnel](network.md#reverse-tcp-tunnel) | [反向 TCP 隧道](network.md#reverse-tcp-tunnel) |
| 48 | [DHCP Starvation](network.md#dhcp-starvation) | [DHCP 地址池耗尽测试](network.md#dhcp-starvation) |
| 49 | [Rogue DHCP STA](network.md#rogue-dhcp-sta) | [伪 DHCP：STA 模式](network.md#rogue-dhcp-sta) |
| 50 | [Rogue DHCP AP](network.md#rogue-dhcp-ap) | [伪 DHCP：AP 模式](network.md#rogue-dhcp-ap) |
| 51 | [Switch DNS](network.md#switch-dns) | [切换 / 重定向 DNS](network.md#switch-dns) |
| 52 | [Network Hijacking](network.md#network-hijacking) | [网络劫持测试](network.md#network-hijacking) |
| 53 | [Detect Printer](network.md#detect-printer) | [探测网络打印机](network.md#detect-printer) |
| 54 | [File Print](network.md#file-print) | [发送文件到打印机](network.md#file-print) |
| 55 | [Check printer status](network.md#check-printer-status) | [查看打印机状态](network.md#check-printer-status) |
| 56 | [HoneyPot](network.md#honeypot) | [蜜罐](network.md#honeypot) |
| 57 | [LLM Chat Stream](network.md#llm-chat-stream) | [LLM 流式聊天](network.md#llm-chat-stream) |
| 58 | [EvilChatMesh](network.md#evilchatmesh) | [EvilChat Mesh 聊天](network.md#evilchatmesh) |
| 59 | [SD on USB](network.md#sd-on-usb) | [SD 卡 USB 存储](network.md#sd-on-usb) |
| 60 | [Responder](network.md#responder) | [LLMNR/NBNS/SMB 响应测试](network.md#responder) |
| 61 | [WPAD Abuse](network.md#wpad-abuse) | [WPAD 代理自动发现测试](network.md#wpad-abuse) |
| 62 | [Crack NTLMv2](network.md#crack-ntlmv2) | [NTLMv2 离线口令验证](network.md#crack-ntlmv2) |
| 63 | [Clean NTLMv2 duplicate](network.md#clean-ntlmv2-duplicate) | [清理重复 NTLMv2 记录](network.md#clean-ntlmv2-duplicate) |
| 64 | [FileManager](network.md#filemanager) | [文件管理器](network.md#filemanager) |

### 65–88：协议、IoT、ESP32‑C5 与新功能

| # | English / 英文 | 中文 |
|---:|---|---|
| 65 | [UART Shell](io-iot.md#uart-shell) | [UART 串口终端](io-iot.md#uart-shell) |
| 66 | [SIP Scanner](io-iot.md#sip-scanner) | [SIP 扫描器](io-iot.md#sip-scanner) |
| 67 | [SIP Enumeration](io-iot.md#sip-enumeration) | [SIP 枚举](io-iot.md#sip-enumeration) |
| 68 | [SIP Message Spoof](io-iot.md#sip-message-spoof) | [SIP 消息伪装测试](io-iot.md#sip-message-spoof) |
| 69 | [SIP Flooding](io-iot.md#sip-flooding) | [SIP 压力测试](io-iot.md#sip-flooding) |
| 70 | [SIP Ring All](io-iot.md#sip-ring-all) | [SIP 批量响铃测试](io-iot.md#sip-ring-all) |
| 71 | [CCTV Toolkit](io-iot.md#cctv-toolkit) | [CCTV 网络摄像头工具箱](io-iot.md#cctv-toolkit) |
| 72 | [SSDP Poisoner](io-iot.md#ssdp-poisoner) | [SSDP 响应欺骗测试](io-iot.md#ssdp-poisoner) |
| 73 | [SkyJack](io-iot.md#skyjack) | [SkyJack 无线测试](io-iot.md#skyjack) |
| 74 | [WiFi Dead Drop](io-iot.md#wifi-dead-drop) | [Wi‑Fi 文件投递箱](io-iot.md#wifi-dead-drop) |
| 75 | [BLENameFlood](io-iot.md#blenameflood) | [BLE 名称广播测试](io-iot.md#blenameflood) |
| 76 | [Wall Of Airtag](io-iot.md#wall-of-airtag) | [AirTag 广播墙](io-iot.md#wall-of-airtag) |
| 77 | [FindMyEvil](io-iot.md#findmyevil) | [Find My 广播测试](io-iot.md#findmyevil) |
| 78 | [List UPnP Mapping](io-iot.md#list-upnp-mapping) | [查看 UPnP 端口映射](io-iot.md#list-upnp-mapping) |
| 79 | [UPnP NAT](io-iot.md#upnp-nat) | [UPnP NAT 映射工具](io-iot.md#upnp-nat) |
| 80 | [LDAPDump](io-iot.md#ldapdump) | [LDAP 域信息导出](io-iot.md#ldapdump) |
| 81 | [IMSI Catcher](io-iot.md#imsi-catcher) | [EAP‑SIM IMSI 监听器](io-iot.md#imsi-catcher) |
| 82 | [Open Wifi Checker](io-iot.md#open-wifi-checker) | [开放 Wi‑Fi 检查器](io-iot.md#open-wifi-checker) |
| 83 | [ESP32C5 Serial](io-iot.md#esp32c5-serial) | [ESP32‑C5 串口工具箱](io-iot.md#esp32c5-serial) |
| 84 | [Aircrack](io-iot.md#aircrack) | [WPA2 离线口令验证](io-iot.md#aircrack) |
| 85 | [Autodiscover Abuse](io-iot.md#autodiscover-abuse) | [Autodiscover 安全测试](io-iot.md#autodiscover-abuse) |
| 86 | [CIW Zeroclick](io-iot.md#ciw-zeroclick) | [CIW / SSID 注入测试框架](io-iot.md#ciw-zeroclick) |
| 87 | [TagTinker ESL](io-iot.md#tagtinker-esl) | [电子价签 / ESL 工具](io-iot.md#tagtinker-esl) |
| 88 | [CSI Radar](io-iot.md#csi-radar) | [Wi‑Fi CSI 存在 / 动作雷达](io-iot.md#csi-radar) |

### 89：Settings

| # | English / 英文 | 中文 |
|---:|---|---|
| 89 | [Settings](settings.md) | [设置](settings.md) |

## 使用提示

- 想知道某个菜单“是干什么的”，直接点上面的英文或中文名称。
- 详情页保持与实机菜单一致的英文名称，同时补中文解释、常见字段、运行结果和故障排查。
- 带主动发包、认证数据、连接中断、网络重定向等能力的功能，只用于自己的设备、隔离实验室或明确授权环境。

## 相关页面

- [Evil-M5Project 中文 Wiki 首页](index.md)
- [新手必读](start-here.md)
- [字段字典](fields.md)
- [故障排查](troubleshooting.md)
- [Settings 完整说明](settings.md)
