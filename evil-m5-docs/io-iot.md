# Evil v1.5.4：协议、IoT、ESP32‑C5、TagTinker 与 CSI Radar

这一页对应主菜单 **65–88**。其中 `TagTinker ESL` 和 `CSI Radar` 是 v1.5.4 主菜单里新增/明确出现的重要入口。

## UART Shell（UART 串口终端） {#uart-shell}

**风险：🟢/🟡。**通过 UART 与你自己的开发板、模块或串口设备收发文本/命令。常见参数包括 TX/RX、Baudrate、数据格式等。

如果只看到乱码，第一优先排查波特率是否一致，其次检查 TX/RX 是否交叉以及 GND 是否共地。

## SIP Scanner（SIP 扫描器） {#sip-scanner}

**风险：🟡 授权扫描。**发现自己网络中开放的 SIP/VoIP 服务，例如 PBX、软交换或测试电话系统。

扫描到 SIP 端口只代表服务存在，不代表可以登录或调用。

## SIP Enumeration（SIP 枚举） {#sip-enumeration}

**风险：🟠。**在授权 VoIP 环境中测试 SIP 服务是否泄露用户/分机等可枚举信息。

## SIP Message Spoof（SIP 消息伪装测试） {#sip-message-spoof}

**风险：🔴。**用于测试自己的 SIP 系统是否会信任伪造/异常消息。可能造成误导性来电/消息显示，仅限隔离 VoIP 实验环境。

## SIP Flooding（SIP 压力测试） {#sip-flooding}

**风险：🔴 可能中断服务。**用于授权环境评估 SIP 服务器在大量请求下的稳定性。不要对生产 PBX、运营商或第三方电话系统执行。

## SIP Ring All（SIP 批量响铃测试） {#sip-ring-all}

**风险：🔴。**在受控 SIP 测试环境中验证批量呼叫/响铃行为，会明显干扰终端，只能对自己的实验分机使用。

## CCTV Toolkit（CCTV 网络摄像头工具箱） {#cctv-toolkit}

**风险：🟡 授权网络工具。**用于发现/分析自己局域网内可通过网络访问的摄像头、NVR 或相关服务。

它不是“万能找针孔摄像头”。下面这些情况不能指望靠 CCTV Toolkit 直接发现：

- 纯本地 SD 卡录像、完全不联网的摄像头；
- 摄像头走 4G/蜂窝网络，不在你的局域网；
- 只接有线网络但 Cardputer 不在同一可达网段；
- 使用 Evil/Cardputer 无法监听的专用无线频段；
- 设备完全关闭网络广播且没有可达服务。

所以 CCTV Toolkit 更准确的定位是“**网络摄像头工具箱**”，不是物理空间摄像头探测器。

## SSDP Poisoner（SSDP 响应欺骗测试） {#ssdp-poisoner}

**风险：🟠/🔴。**测试 UPnP/SSDP 客户端是否会信任伪造的设备发现响应。只在自己的 IoT 实验网络使用。

## SkyJack（SkyJack 无线测试） {#skyjack}

**风险：🟠。**项目中的无线/设备安全测试入口。具体可用能力取决于版本和所连接硬件；只对自有测试设备使用。

## WiFi Dead Drop（Wi‑Fi 文件投递箱） {#wifi-dead-drop}

**风险：🟢/🟡。**利用 Evil 提供局域网文件投递/交换入口，类似临时无线“死信箱”。适合自己的设备之间传文件。

投递箱开放期间要留意谁能访问，测试结束后关闭并清理不需要的文件。

## BLENameFlood（BLE 名称广播测试） {#blenameflood}

**风险：🟠。**广播大量 BLE 名称，用于测试扫描器/手机蓝牙列表面对大量广播时的表现。公共场所不要长时间开启。

## Wall Of Airtag（AirTag 广播墙） {#wall-of-airtag}

**风险：🟡。**扫描/展示与 AirTag/Find My 生态相关的广播特征。结果是无线广播线索，不等于能确认某个 AirTag 的真实主人或身份。

## FindMyEvil（Find My 广播测试） {#findmyevil}

**风险：🟠。**用于研究/模拟 Find My 相关广播行为和兼容性测试。它并不是合法的“追踪陌生人”功能，也不应被用于绕过隐私保护。

## List UPnP Mapping（查看 UPnP 端口映射） {#list-upnp-mapping}

**风险：🟡。**查看自己路由器/网关暴露的 UPnP NAT 映射。适合排查为什么某个内网服务被自动映射到外网。

重点字段通常是外部端口、内部 IP、内部端口、协议和描述。

## UPnP NAT（UPnP NAT 映射工具） {#upnp-nat}

**风险：🟡/🟠。**在你管理的网关上测试创建/管理 UPnP NAT 端口映射。错误映射可能把内网服务暴露到外网，使用后应检查并删除不需要的规则。

## LDAPDump（LDAP 域信息导出） {#ldapdump}

**风险：🟡 敏感目录信息。**在授权的 LDAP/AD 测试环境中查看服务器允许读取的域/目录信息，例如对象、用户、组或目录结构。

读取权限由 LDAP 服务端决定；不要把企业目录数据复制到公开位置。

## IMSI Catcher（EAP‑SIM IMSI 监听器） {#imsi-catcher}

**风险：🔴 高敏感。**用于安全研究中分析 EAP‑SIM/相关身份数据暴露。IMSI 属于高度敏感的蜂窝身份标识，法律和隐私风险明显。

本 Wiki 只说明菜单含义和风险，不提供捕获第三方 IMSI 的操作方法。

## Open Wifi Checker（开放 Wi‑Fi 检查器） {#open-wifi-checker}

**风险：🟢/🟡。**检查附近扫描结果中哪些 AP 显示为开放网络，并可用于自己的测试热点验证开放/加密状态。

“Open” 只表示 Wi‑Fi 层没有常规口令加密，不代表允许使用，也不代表连接后一定能上网。

## ESP32C5 Serial（ESP32‑C5 串口工具箱） {#esp32c5-serial}

Evil v1.5.4 通过串口连接外部 ESP32‑C5，可把 5 GHz 相关扫描/无线能力交给 C5。Cardputer ADV 本机 ESP32‑S3 不会因为打开这个菜单就原生支持 5 GHz。

v1.5.4 源码中的二级菜单为：

```text
ESP32C5 Serial（ESP32‑C5 串口工具箱）
├─ Start（启动）
├─ Stop（停止）
├─ Scan ALL（扫描全部）
├─ Scan (single)（单次扫描）
├─ List（列表）
├─ Band (ALL/2G/5G)（频段：全部/2.4G/5G）
├─ Deauth toggle（去认证测试开关）
├─ Ward toggle（巡航记录开关）
├─ Ward history (ms)（巡航历史时长）
├─ Sniff toggle（监听开关）
├─ Sniff timeout (ms)（监听超时）
├─ Target SSID（目标 SSID）
├─ Target BSSID（目标 BSSID）
├─ Target INDEX (manual)（手动目标索引）
├─ Target clear（清除目标）
├─ Chan SET（设置信道）
├─ Chan ADD（添加信道）
├─ Chan RESET（重置信道）
├─ Chan CLEAR（清空信道）
├─ Chan LIST（查看信道列表）
├─ Interval (ms)（间隔）
├─ History (ms)（历史时长）
├─ Info（信息）
├─ Config（配置）
├─ Help（帮助）
├─ Send custom CMD（发送自定义命令）
├─ Raw monitor（原始监视器）
└─ Back to menu（返回主菜单）
```

进入时如果显示：

```text
ESP32C5 ERROR
No response on UART
Check wiring / power
```

优先排查 C5 是否供电、UART 接线、固件和串口参数，不要先怀疑 5 GHz 天线。

其中 `Scan` / `List` / `Band` / `Info` 可用于自己的无线环境诊断；`Deauth toggle` 属于可能中断网络的主动测试，只限授权实验。

## Aircrack（WPA2 离线口令验证） {#aircrack}

**风险：🟡。**对你自己的 WPA2 握手/测试样本进行离线口令强度验证。它依赖有效握手数据和候选口令/字典，不能凭空“显示 Wi‑Fi 密码”。

## Autodiscover Abuse（Autodiscover 安全测试） {#autodiscover-abuse}

**风险：🔴。**用于受控企业环境验证客户端/邮件自动发现机制是否会错误连接到非预期服务或泄露认证信息。仅限明确授权的实验环境。

## CIW Zeroclick（CIW / SSID 注入测试框架） {#ciw-zeroclick}

**风险：🔴。**v1.5.4 中的 CIW Zeroclick 属于针对 SSID/无线输入处理的安全测试框架。其目的是验证受控客户端在接收特殊构造的无线名称/数据时是否存在异常行为。

本 Wiki 不提供面向第三方设备的利用载荷、批量投放或规避检测步骤；只建议在隔离实验设备上验证版本是否受影响并记录结果。

## TagTinker ESL（电子价签 / ESL 工具） {#tagtinker-esl}

v1.5.4 源码把 TagTinker ESL 作为独立主菜单入口，Cardputer 使用内置 IR 相关能力研究电子价签（Electronic Shelf Label）协议。**只对你拥有或获授权的测试价签使用。**

二级菜单原文为：

```text
TagTinker ESL（电子价签 / ESL 工具）
├─ Saved Tags（已保存价签）
├─ Tag Info（价签信息）
├─ NFC Decoder（NFC 解码器）
├─ Push Text（推送文本）
├─ Push Text ALL（向全部已保存价签推送文本）
├─ Push Image（推送图片）
├─ Push Image ALL（向全部已保存价签推送图片）
├─ Online Content（在线内容）
├─ Text Presets（文本预设）
├─ LED Test（LED 测试）
├─ Broadcast Page Flip（广播翻页）
├─ Broadcast Debug（广播调试）
├─ Broadcast LED（广播 LED）
├─ WiFi Icon ON (Broadcast)（广播打开 Wi‑Fi 图标）
├─ WiFi Icon OFF (All)（关闭全部 Wi‑Fi 图标）
├─ Raw Frame（原始帧）
├─ LED Explorer（LED 探索）
├─ Protocol Lab（协议实验室）
└─ Settings（设置）
```

`Raw Frame`、广播写入、批量推送等会改变真实价签显示/状态，不要对商场、超市等第三方 ESL 设备测试。

## CSI Radar（Wi‑Fi CSI 存在 / 动作雷达） {#csi-radar}

**风险：🟢/🟡。**v1.5.4 使用 Wi‑Fi CSI（Channel State Information）变化检测空间中的存在/运动。源码说明其算法基于空间扰动、滤波和移动方差；单天线方案**不能给出方向**，重点是存在/动作变化。

进入后会看到：

```text
CSI RADAR - Select Mode
1. Single Beacon（单 Beacon）
2. Multi Beacons（多 Beacon）
```

- `Single Beacon`：使用 1 个刷入 CSI-Beacon 固件的 ESP32 作为 AP/Beacon。
- `Multi Beacons`：使用 2 个或更多 ESP32 Beacon，帮助提高空间采样稳定性。

运行界面可能显示：

- `WAITING`：等待有效 CSI 数据。
- `CALIBRATING`：正在校准空环境基线。
- `MOTION`：检测到较明显变化。
- `PRESENCE`：检测到持续存在/变化特征。
- `T:`：当前 turbulence/扰动指标。
- `S:`：Sensitivity/灵敏度。
- `BPM:`：算法估计的周期性指标（有数据时）。

底部提示 `+/-=sens R=cal BACK=exit`，即调灵敏度、重新校准、返回。

**这不是医学级生命体征仪，也不是“隔墙精确识别人是谁”的雷达。** 环境、距离、反射、多径、家具移动都会影响结果。

下一页：[Settings（设置）完整说明](settings.md)。
