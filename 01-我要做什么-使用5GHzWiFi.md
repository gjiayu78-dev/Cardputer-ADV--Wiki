# 使用 5GHz Wi-Fi

## Cardputer-ADV 原生能力

Cardputer-ADV 自带 ESP32-S3：
- 2.4GHz Wi-Fi：支持
- 5GHz Wi-Fi：不支持

换天线不能让 ESP32-S3 变成 5GHz。

## 如果只是想联网

最简单：
- 路由器开启 2.4GHz / IoT SSID；
- 手机热点开启 2.4GHz。

## 如果必须真正扫描/连接 5GHz

需要独立支持 5GHz 的无线芯片，例如 ESP32-C5 扩展。

典型架构：

`Cardputer-ADV → ESP32-C5 扩展 → 2.4GHz / 5GHz Wi-Fi`

注意：加 C5 不代表 Bruce 原生 Wi-Fi 菜单会自动获得 5GHz，仍取决于对应扩展 App/固件支持。
