# Evil v1.5.4：Wi‑Fi / Portal 基础功能

这一页对应主菜单 **1–12**。前六项主要是扫描、选择和配置；Portal / Credentials 涉及敏感数据，只能在自己的测试网络或明确授权环境使用。

## Scan WiFi（扫描 Wi‑Fi） {#scan-wifi}

**作用：**扫描周围无线接入点（AP）。这是最适合第一次上手的功能之一。

你通常会关注：

- `SSID`：Wi‑Fi 名称。
- `BSSID`：AP 无线接口的 MAC 地址。
- `RSSI`：信号强度，单位 dBm；越接近 0 通常越强。
- `Channel`：无线频道。
- 加密类型：开放网络、WPA/WPA2 等。

扫描本身不会让你自动连接到这些网络，也不代表你获得了使用权限。

## Select Network（选择网络） {#select-network}

**作用：**从最近一次扫描结果中选择一个 AP，供后续 `Clone & Details`、信道查看或其他功能引用。

可以把它理解成“把当前操作对象指向这条扫描结果”。它本身不是连接网络。

## Clone & Details（克隆与详情） {#clone-details}

**作用：**查看所选网络的详细信息，并把部分 AP 参数作为后续 Portal / 测试功能的配置来源。

新手要区分：

- **Details**：查看信息。
- **Clone**：把名称等参数复制给 Evil 的测试配置。

仅查看自己扫描到的广播信息通常属于被动行为；用复制后的配置建立仿冒热点则属于主动测试。

## Set Wifi SSID（设置 Wi‑Fi SSID） {#set-wifi-ssid}

**作用：**手工设置 Evil 使用的 Wi‑Fi / AP 名称。

`SSID` 就是用户在手机或电脑 Wi‑Fi 列表里看到的网络名字。这里改的是 Evil 的配置，不是修改别人路由器的 SSID。

## Set Wifi Password（设置 Wi‑Fi 密码） {#set-wifi-password}

**作用：**设置 Evil 保存/使用的 Wi‑Fi 密码，例如连接自己的网络或配置某些 AP 场景。

密码属于敏感信息。不要截图公开自己的真实 Wi‑Fi 密码，也不要把公司网络密码直接提交到公开 Issue/Wiki。

## Set Mac Address（设置 MAC 地址） {#set-mac-address}

**作用：**修改 Evil 使用的 Wi‑Fi MAC 地址。

MAC 地址形如：

```text
AA:BB:CC:DD:EE:FF
```

常见用途是实验环境中的网络兼容、设备标识测试或隐私测试。修改 MAC 不会把设备“变成”另一个真实设备，也不会自动获得那个设备的权限。

## Start Captive Portal（启动强制门户） {#start-captive-portal}

**风险：🟠 主动安全测试**

**作用：**启动 Evil 的 Captive Portal 测试环境。Portal 是连接到测试 AP 后自动/手动打开的网页页面。

合法用途包括：

- 测试自己的访客 Wi‑Fi 登录页面。
- 测试员工是否会识别错误的认证页面。
- 演示 Captive Portal 工作机制。

这个功能可能收集表单输入，所以不要对不知情的第三方使用。

## Stop Captive Portal（停止强制门户） {#stop-captive-portal}

**作用：**停止当前运行的 Portal / AP 测试服务并结束对应状态。

如果你不知道 Portal 当前是否还开着，完成实验后主动停止是个好习惯。

## Change Portal（切换门户页面） {#change-portal}

**作用：**选择 SD 卡 `/evil/` 资源中的另一个 Portal 页面。

如果这里出现“文件不存在”“页面空白”之类问题，优先检查 SD 资源目录是否完整，而不是先怀疑 Wi‑Fi 模块。

## Check Credentials（查看捕获凭据） {#check-credentials}

**风险：🟡 敏感数据**

**作用：**查看本机 Portal 测试过程中保存的输入记录/凭据数据。

这些数据可能含用户名、邮箱、口令或测试字符串。只应查看你自己的实验数据；完成测试后应及时清理。

## Delete All Creds（删除全部凭据） {#delete-all-creds}

**作用：**删除 Evil 本机保存的凭据记录。

适合在：

- 演示结束后清理测试数据；
- 换实验对象前清空旧记录；
- 排查“为什么还显示上一次数据”时重置状态。

删除前如果是合法测试证据，先按你的组织流程备份；删除后通常无法从 Evil 菜单直接恢复。

## Monitor Status（状态监控） {#monitor-status}

**作用：**查看 Evil 当前系统/服务状态。v1.5.4 代码中状态页会显示包括 RAM、Battery 等运行信息。

新手遇到卡顿、异常退出、长时间扫描时，可以先看状态页：

- 电量是否太低；
- RAM 是否紧张；
- AP / Portal 是否仍运行；
- 当前是否已经连接网络。

## 下一页

- [无线监听、Wardriving、Handshake、Deauth 等菜单](wifi-radio.md)
- [字段字典](fields.md)
- [故障排查](troubleshooting.md)
