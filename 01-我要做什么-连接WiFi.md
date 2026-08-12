# 连接 Wi-Fi

**推荐固件：** Bruce  
**菜单路径：** `WiFi → Connect to WiFi`

## 中文说明

扫描附近 Wi-Fi，选择 SSID，输入密码后连接。

## Cardputer-ADV 限制

Cardputer-ADV 自带 ESP32-S3，只支持 **2.4GHz Wi-Fi**。

如果家里只有 5GHz：
- 路由器单独开启 2.4GHz / IoT Wi-Fi；
- 或手机热点开启 2.4GHz / 最大兼容性；
- 如果必须真正扫描/连接 5GHz，需要 ESP32-C5 类扩展。

## 常见提示

| 英文 | 中文 |
|---|---|
| `Scanning...` | 正在扫描 |
| `Connecting to...` | 正在连接 |
| `Wifi Offline` | 未成功连接到 AP |
| `Retry` | 重试 |
| `Cancel` | 取消 |
| `RSSI` | 信号强度 |

## 排障

如果密码正确却一直 `Wifi Offline`：
1. 确认 Wi-Fi 是 2.4GHz；
2. 先用简单密码热点测试；
3. 再排查 WPA3、双频合一、特殊字符输入等问题。
