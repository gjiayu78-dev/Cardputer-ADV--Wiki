# Evil v1.5.4：Settings（设置）

这一页对应主菜单最后一项 `Settings`。下面按 v1.5.4 源码 `showSettingsMenu()` 中的实际选项整理。

## Settings 二级菜单中英对照

```text
Settings（设置）
├─ Brightness（屏幕亮度）
├─ Disable Sound / Enable Sound（关闭声音 / 开启声音）
├─ Disable LED / Enable LED（关闭 LED / 开启 LED）
├─ Switch GPS Pins to: ...（切换 GPS 引脚）
├─ Set GPS Baudrate（设置 GPS 波特率）
├─ Set Startup Image（设置启动图片）
├─ Set Startup Volume（设置启动音量）
├─ Set Startup Sound（设置启动声音）
├─ Disable Random startup / Enable Random startup（关闭 / 开启随机启动素材）
├─ Save current Portal & SSID（保存当前 Portal 与 SSID）
├─ Disable Auto at boot / Enable Auto at boot（关闭 / 开启开机自动运行）
├─ Set Auto Function（设置开机自动功能）
├─ Set Auto Countdown（设置自动启动倒计时）
├─ Set CPU Frequency（设置 CPU 频率）
└─ Change Portal IP（修改 Portal IP）
```

部分项目会根据当前状态动态显示 `Enable` 或 `Disable`，所以你机器上看到其中一边是正常的。

## Brightness（屏幕亮度） {#brightness}

调整屏幕背光亮度。v1.5.4 默认亮度配置约为 35%。如果你觉得续航下降很快，降低亮度通常比改 CPU 频率更直观。

## Disable Sound / Enable Sound（声音开关） {#sound-toggle}

控制 Evil 的声音功能。菜单文字显示的是“点击后要执行的动作”：

- 当前声音已开 → 显示 `Disable Sound`。
- 当前声音已关 → 显示 `Enable Sound`。

## Disable LED / Enable LED（LED 开关） {#led-toggle}

控制设备 LED 是否启用。逻辑与声音开关一样，菜单会随当前状态变化。

## Switch GPS Pins to: ...（切换 GPS 引脚） {#switch-gps-pins}

在不同 GPS 接线方案间切换。v1.5.4 代码会根据当前模式显示类似：

```text
Switch GPS Pins to: 1/2
Switch GPS Pins to: 15/13
Switch GPS Pins to: Auto
```

如果 GPS 没有数据，先核对你实际使用的 GPS 模块接线，再选择对应引脚模式。

## Set GPS Baudrate（设置 GPS 波特率） {#set-gps-baudrate}

v1.5.4 提供：

```text
9600
19200
115200
```

波特率必须与 GPS 模块实际输出一致。错误时最常见现象是“串口有数据但都是乱码”或完全无法正确解析 NMEA。

## Set Startup Image（设置启动图片） {#set-startup-image}

从 SD 卡 `/evil/` 资源中选择启动时显示的图片。默认配置指向类似：

```text
/evil/img/startup-cardputer.jpg
```

图片不存在时优先检查 SD 卡文件路径和资源包是否完整。

## Set Startup Volume（设置启动音量） {#set-startup-volume}

调整启动音频播放音量。音量值最终由 Cardputer 扬声器配置保存。

## Set Startup Sound（设置启动声音） {#set-startup-sound}

选择启动时播放的音频资源，默认配置会从 `/evil/audio/` 下读取文件。

## Disable Random startup / Enable Random startup（随机启动素材） {#random-startup}

开启后，Evil 会在启动时随机选择可用的启动图片/声音；关闭后使用你指定的固定启动资源。

## Save current Portal & SSID（保存当前 Portal 与 SSID） {#save-current-portal-ssid}

把当前 Portal 与 SSID 相关配置保存，避免重启后重新选择。保存的是 Evil 自己的测试配置，不是修改真实路由器。

## Disable Auto at boot / Enable Auto at boot（开机自动运行） {#auto-at-boot}

开启后可以让 Evil 开机倒计时结束后自动进入某一个主菜单功能。

新手建议先保持关闭，确认所有参数都正确后再使用。特别是不要把 Deauth、DHCP Starvation、Responder、CIW 等主动安全测试功能设成开机自动运行，以免一开机就对周围网络产生非预期影响。

## Set Auto Function（设置开机自动功能） {#set-auto-function}

从完整 `menuItems[]` 中选择开机自动进入的菜单项。v1.5.4 会按菜单索引列出功能。

适合的低风险例子：状态查看、自己环境的扫描/监测等。

## Set Auto Countdown（设置自动启动倒计时） {#set-auto-countdown}

v1.5.4 提供 **0–10 秒**倒计时。作用是给你一个开机后取消/观察的缓冲时间。

## Set CPU Frequency（设置 CPU 频率） {#set-cpu-frequency}

v1.5.4 可选：

```text
80 MHz
160 MHz
240 MHz
```

一般理解：

- 80 MHz：更省电，但部分复杂功能可能更慢。
- 160 MHz：折中。
- 240 MHz：性能优先，功耗/发热通常更高。

如果你只是在排查某个功能故障，不建议把“改 CPU 频率”当第一解决方案。

## Change Portal IP（修改 Portal IP） {#change-portal-ip}

修改 Evil Captive Portal 使用的 AP/Portal IP 配置。只有在你清楚当前测试网络地址规划时再改；否则保持默认更容易排查问题。

## 配置文件在哪里

v1.5.4 代码使用：

```text
/evil/config/config.txt
```

保存亮度、声音、LED、Wi‑Fi、GPS、启动项、CPU 等配置。出现“重启后配置没保存”时，除了看代码逻辑，也要先确认 SD 卡可写、`/evil/config/` 正常存在。

返回：[完整主菜单中英对照](menu.md)。
