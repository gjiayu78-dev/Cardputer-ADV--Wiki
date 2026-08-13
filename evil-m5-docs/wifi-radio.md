# Evil v1.5.4：无线监听、Wardriving 与授权测试

这一页对应主菜单 **13–34**。这组功能里既有被动监听，也有会主动发包、影响连接的测试功能。凡是带 🟠 / 🔴 的项目，都只用于自己的设备、隔离实验室或明确授权的网络。

## Probe Attack（Probe 响应测试） {#probe-attack}

**风险：🟠**。Wi‑Fi 终端有时会发送 Probe Request，询问附近是否存在某个曾连接过的网络。该功能用于研究/测试设备对 Probe 响应的行为。

新手重点理解两个词：`Probe Request` 是终端发出的询问，`Probe Response` 是 AP 侧回应。不要把它当成“自动破解 Wi‑Fi”。

## Probe Sniffing（Probe 请求监听） {#probe-sniffing}

**风险：🟡 被动采集。**监听附近终端广播出来的 Probe 请求，并记录可见 SSID 等信息。即使不主动攻击，这类数据也可能反映设备曾连接过的网络名称，因此属于敏感无线元数据。

## Karma Attack（Karma 测试） {#karma-attack}

**风险：🟠**。用于测试终端是否会因为收到“它正在寻找的网络”的响应而错误连接。核心目的是验证客户端自动连接策略是否安全。

Wiki 不提供对第三方设备实施 Karma 的操作步骤；合法测试时只观察受控终端是否出现错误信任/连接行为。

## Karma Auto（自动 Karma） {#karma-auto}

**风险：🟠**。自动化处理 Probe 与 Karma 测试流程。相比普通 Karma，更容易持续响应多个观察到的网络名称，因此实验范围要严格限制。

## Karma Spear（定向 Karma） {#karma-spear}

**风险：🟠**。更偏向选定 Probe/SSID 后进行定向测试。适合安全演练中验证某一台受控终端对特定已知网络名的信任行为。

## Select Probe（选择 Probe） {#select-probe}

从已监听/保存的 Probe 记录中选择一条，供后续功能引用。它本身主要是“选对象”，不是攻击动作。

## Delete Probe（删除 Probe） {#delete-probe}

删除当前/选定的 Probe 记录。用于清理测试数据或避免旧数据干扰下一轮实验。

## Delete All Probes（删除全部 Probe） {#delete-all-probes}

一次清空保存的 Probe 数据。操作前确认是否还需要保留测试记录。

## Wardriving（无线巡航记录） {#wardriving}

**风险：🟢/🟡。**配合 GPS 在移动过程中记录附近 Wi‑Fi AP 的 SSID、BSSID、频道、RSSI、位置等信息，通常可用于覆盖分析、资产盘点或 Wigle 兼容记录。

合规使用时只把它当“无线环境测绘”，不要尝试连接陌生网络。

## Wardriving Master（多节点巡航主机） {#wardriving-master}

Cardputer 作为主机，接收一个或多个 ESP32 slave 的扫描结果。多个从机可以分担不同 2.4 GHz 频道，减少单设备跳频带来的漏扫，再由 Cardputer + GPS 汇总记录。

适合做自己的场地无线覆盖调查。

## Beacon Spam（Beacon 广播测试） {#beacon-spam}

**风险：🟠**。广播大量测试 SSID/Beacon，用来验证 Wi‑Fi 扫描器、终端 UI 或无线监控系统在大量网络广播下的表现。

它会制造明显的无线噪声和大量虚拟网络名，不要在公共场所或生产网络随便开启。

## Deauther（去认证测试） {#deauther}

**风险：🔴 可能中断连接。**用于验证受控 Wi‑Fi 客户端/AP 对 Deauthentication 管理帧的处理能力。

现象通常是测试客户端掉线、重新连接或触发监控告警。这里只说明功能和结果，不提供对第三方 AP 的操作方法。

## Auto Deauther（自动去认证测试） {#auto-deauther}

**风险：🔴。**把 Deauth 测试自动化/持续化，比单次测试更容易造成网络中断。仅在隔离实验室使用，并确保不会波及相邻网络。

## Evil Twin（仿冒热点测试） {#evil-twin}

**风险：🟠/🔴。**建立与测试目标相似的 AP/Portal，用于验证用户和终端能否识别仿冒热点、错误证书或异常门户。

合法场景是公司红队/培训中的受控演练。不要仿冒真实公共 Wi‑Fi 去诱导不知情用户。

## Handshake Master（握手采集主机） {#handshake-master}

**风险：🟡/🟠。**用于观察/收集 WPA/WPA2 认证相关握手数据，帮助判断自己的无线网络是否存在弱密码风险，或用于离线实验验证。

Handshake 文件本身不等于密码；是否能离线验证取决于捕获完整度、协议和口令强度。

## WiFi Raw Sniffing（Wi‑Fi 原始数据监听） {#wifi-raw-sniffing}

**风险：🟡。**进入更底层的 Wi‑Fi 帧监听模式。适合协议学习、排查自己的无线设备通信和观察管理帧。

Raw 帧信息量大，新手优先看 `type/subtype`、`source/destination MAC`、`channel`、`RSSI`，不要一上来试图理解全部字节。

## Sniff Raw Clients（客户端原始帧监听） {#sniff-raw-clients}

**风险：🟡。**更偏向观察客户端（STA）相关无线帧，用于识别活跃终端与基本通信特征。MAC 地址属于设备标识数据，记录和共享时注意隐私。

## Wifi Channel Visualizer（Wi‑Fi 信道可视化） {#wifi-channel-visualizer}

**风险：🟢。**把频道占用/周边 AP 分布以更直观方式显示。适合家庭或办公室选 2.4 GHz 信道时参考。

重点不是“哪个频道数字最大”，而是看同频/邻频网络数量和信号强度。

## Client Sniffing and Deauth（客户端监听与断开测试） {#client-sniffing-and-deauth}

**风险：🔴。**把客户端观察和主动 Deauth 测试放在同一工作流中，便于授权实验中选择受控客户端并观察断线/重连行为。

因为包含主动断开能力，本 Wiki 不提供对第三方客户端的执行步骤。

## Handshake/Deauth Sniffing（握手/去认证监听） {#handshake-deauth-sniffing}

**风险：🟡 被动监听。**监听 EAPOL/Handshake 相关流量以及 Deauth 事件。非常适合判断“我的网络是否正在发生异常掉线/去认证事件”。

注意：监听到 Deauth 不等于一定有人攻击，也可能来自 AP 重启、漫游、客户端主动断开等正常原因。

## Check Handshakes（检查握手文件） {#check-handshakes}

**风险：🟢 本地。**检查 SD 卡上已经保存的握手/PCAP 数据，确认文件是否存在、是否包含可识别的握手信息。

这是排查“为什么 Aircrack/离线验证没有输入”的第一站。

## Wall Of Flipper（Flipper 广播墙） {#wall-of-flipper}

**风险：🟡。**监听/展示与 Flipper Zero 等设备广播相关的可识别 BLE/无线活动，主要用于演示和设备发现。不要把一次匹配就当成对附近人员身份的确定结论。

## 怎么区分这组功能

| 类别 | 代表菜单 | 新手理解 |
|---|---|---|
| 被动观察 | Probe Sniffing、Raw Sniffing、Channel Visualizer | 看无线环境，不主动让别人掉线 |
| 测绘记录 | Wardriving、Wardriving Master | 把 AP + 信号 + GPS 记录下来 |
| 认证研究 | Handshake Master、Check Handshakes | 研究自己网络的认证数据 |
| 主动测试 | Karma、Beacon Spam、Evil Twin | 主动广播/模拟测试场景 |
| 中断性测试 | Deauther、Auto Deauther | 可能让测试客户端掉线 |

下一页：[网络、系统与实用工具](network.md)。
