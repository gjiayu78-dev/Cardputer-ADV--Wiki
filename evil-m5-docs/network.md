# Evil v1.5.4：网络、系统与实用工具

这一页对应主菜单 **35–64**。这里既有正常的 SSH、端口扫描、打印机、文件管理，也有 DHCP / Responder / WPAD 等主动安全测试功能。

## Connect to network（连接到网络） {#connect-to-network}

**风险：🟢。**让 Evil 作为 Wi‑Fi 客户端连接到你自己的无线网络。需要正确的 SSID 和密码。

连接成功后，SSH、网络扫描、Web Crawler、LLM 等需要局域网或互联网的功能才有网络基础。

## SSH Shell（SSH 终端） {#ssh-shell}

**风险：🟢/🟡。**从 Cardputer 连接你有权限登录的 Linux、NAS、服务器或电脑 SSH 服务。

常见字段：

- `Host`：服务器 IP/域名。
- `Port`：默认通常 22。
- `User`：SSH 用户名。
- `Password`：密码认证时使用。

Evil 只是 SSH 客户端，不会因为打开该菜单就绕过服务器登录认证。

## Scan IP Ports（扫描主机端口） {#scan-ip-ports}

**风险：🟡 授权扫描。**检查指定 IP 上哪些 TCP/网络端口有响应。适合排查自己的 NAS、服务器为什么某项服务打不开。

例如发现 22、80、443、445 等端口开放，只代表对应端口有服务/响应，**不等于存在漏洞**。

## Scan Network Hosts（扫描局域网主机） {#scan-network-hosts}

**风险：🟡。**发现同一局域网中的在线设备，通常会得到 IP、MAC 或可识别主机信息。

适合做家庭/公司授权网络资产盘点。

## Scan Network Full（全网段完整扫描） {#scan-network-full}

**风险：🟡。**在主机发现基础上做更完整的网络/端口枚举。比 `Scan Network Hosts` 更耗时、流量更多。

生产网络里应控制扫描范围和时间，避免让低性能 IoT 设备被大量探测请求影响。

## Scan Network List（查看网络扫描列表） {#scan-network-list}

**风险：🟢 本地。**查看此前网络扫描得到的设备/端口结果。用于回看，不需要重新发起扫描。

## Web Crawler（网页爬取 / 站点信息采集） {#web-crawler}

**风险：🟡。**对你有权限访问的网站进行页面/链接信息采集。适合自己的 Web 服务资产检查、页面路径整理和实验环境分析。

网页可公开访问并不代表允许高频自动化抓取；实际使用仍要遵守站点规则和授权范围。

## PwnGrid Spam（PwnGrid 广播测试） {#pwngrid-spam}

**风险：🟠。**生成/广播 PwnGrid 风格测试流量，用来研究兼容设备的发现与显示行为。会在无线环境中产生主动广播。

## Skimmer Detector（可疑蓝牙刷卡器检测） {#skimmer-detector}

**风险：🟢/🟡。**扫描附近 BLE 设备并根据已知特征提示可能的可疑刷卡器/Skimmer。

重要：**检测结果只是线索，不是定论。** 普通 BLE 设备也可能出现相似名称/MAC/服务特征，不能据此认定某商户设备违法。

## Mouse Jiggler（鼠标防休眠） {#mouse-jiggler}

**风险：🟢 本机。**把 Cardputer 当 USB HID，周期性产生轻微鼠标活动，避免自己的电脑自动休眠/锁屏。

公司电脑是否允许这种做法取决于 IT 策略。

## BadUSB（USB HID 自动化） {#badusb}

**风险：🟡/🟠。**把 Cardputer 伪装为键盘/鼠标等 HID，执行 SD 卡中的自动化脚本。

正常用途：自己的电脑上做重复输入、演示或测试。不要在别人电脑上插入并执行脚本。

## Bluetooth Keyboard（蓝牙键盘） {#bluetooth-keyboard}

**风险：🟢。**让 Evil 通过 BLE HID 作为蓝牙键盘使用。适合连接自己的手机/平板/电脑输入文本或快捷键。

## Reverse TCP Tunnel（反向 TCP 隧道） {#reverse-tcp-tunnel}

**风险：🟡。**建立反向 TCP 通道，用于自己网络里的远程调试/端口转发实验。

它不是 VPN，也不会自动突破防火墙；是否能连通取决于双方网络、端口和服务配置。

## DHCP Starvation（DHCP 地址池耗尽测试） {#dhcp-starvation}

**风险：🔴 可能影响整个局域网。**用于授权实验中测试 DHCP 服务器面对大量租约请求时的抗压/防护能力。

可能造成正常设备暂时拿不到 IP，因此不要在家庭主网、公司生产网或公共网络试验。本 Wiki 不提供造成地址池耗尽的执行步骤。

## Rogue DHCP STA（伪 DHCP：STA 模式） {#rogue-dhcp-sta}

**风险：🔴。**在 STA 场景研究客户端是否会接受错误 DHCP 参数，如网关/DNS 等。

## Rogue DHCP AP（伪 DHCP：AP 模式） {#rogue-dhcp-ap}

**风险：🔴。**在 Evil 自建 AP 场景模拟 DHCP 服务，测试受控客户端对网络参数的信任行为。

以上两项都可能改变客户端流量走向，只用于隔离实验。

## Switch DNS（切换 / 重定向 DNS） {#switch-dns}

**风险：🟠。**切换测试环境中的 DNS 处理/指向，用于验证自己的客户端或 Portal 对 DNS 配置变化的表现。

## Network Hijacking（网络劫持测试） {#network-hijacking}

**风险：🔴。**用于研究受控网络中的流量重定向/劫持风险。属于主动安全测试，不应对第三方网络使用。

## Detect Printer（探测网络打印机） {#detect-printer}

**风险：🟡。**在自己的局域网查找可访问的网络打印机及相关服务。

发现打印端口并不意味着应该发送打印任务；先确认设备归属。

## File Print（发送文件到打印机） {#file-print}

**风险：🟡。**把本机/SD 中的文件发送到你有权限使用的网络打印机。适合验证打印链路或做简单远程打印。

## Check printer status（查看打印机状态） {#check-printer-status}

**风险：🟢/🟡。**读取网络打印机状态，例如在线、队列或可返回的设备信息。适合排查“为什么打印没反应”。

## HoneyPot（蜜罐） {#honeypot}

**风险：🟡。**在自己的网络建立诱捕/观测服务，用于记录扫描、访问或测试事件。有些版本可结合 Webhook 做通知。

蜜罐记录可能包含访问者 IP、请求等数据，部署时注意隐私和公司政策。

## LLM Chat Stream（LLM 流式聊天） {#llm-chat-stream}

**风险：🟢。**连接配置好的 LLM 服务并以流式方式显示回复。是否需要互联网取决于你配置的是本地模型服务器还是云 API。

相关配置通常包括 host、port、API path、账号/密码、model、max tokens 等。

## EvilChatMesh（EvilChat Mesh 聊天） {#evilchatmesh}

**风险：🟢/🟡。**设备间的 Mesh/无线聊天功能。适合自己的 Evil 设备之间进行近距离消息实验。

## SD on USB（SD 卡 USB 存储） {#sd-on-usb}

**风险：🟢。**把 Cardputer 的 SD 卡以 USB 存储方式提供给电脑，方便复制文件。

使用时注意安全弹出，避免电脑正在写卡时直接断电导致文件系统损坏。

## Responder（LLMNR/NBNS/SMB 响应测试） {#responder}

**风险：🔴/敏感认证数据。**用于授权 Windows 网络实验，观察 LLMNR/NBNS 名称解析和 SMB/NTLMv2 认证暴露风险。可能保存 NTLMv2 认证响应。

这类数据应按凭据/安全测试证据管理。本 Wiki 不提供诱导第三方主机提交认证信息的步骤。

## WPAD Abuse（WPAD 代理自动发现测试） {#wpad-abuse}

**风险：🔴。**测试客户端是否会错误信任 WPAD/代理自动发现结果，从而把流量交给非预期代理。仅限受控终端和隔离网络。

## Crack NTLMv2（NTLMv2 离线口令验证） {#crack-ntlmv2}

**风险：🟡 敏感数据。**对你合法持有的 NTLMv2 测试样本进行本地/离线口令强度验证。弱密码可能被字典命中，强密码则可能无法在设备能力范围内验证出来。

不要导入来源不明或未经授权的真实用户认证数据。

## Clean NTLMv2 duplicate（清理重复 NTLMv2 记录） {#clean-ntlmv2-duplicate}

**风险：🟢 本地。**去除保存记录中的重复 NTLMv2 条目，让测试文件更容易审计和后续分析。

## FileManager（文件管理器） {#filemanager}

**风险：🟢。**浏览/管理 SD 卡中的项目文件、记录、脚本、Portal 资源等。

对新手来说，排查资源问题时重点看：

```text
/evil/
/evil/config/
/evil/sites/
/evil/img/
/evil/audio/
```

具体目录会随版本变化，不要随意删除不认识的项目文件。

下一页：[协议、IoT、ESP32‑C5、TagTinker、CSI Radar](io-iot.md)。
