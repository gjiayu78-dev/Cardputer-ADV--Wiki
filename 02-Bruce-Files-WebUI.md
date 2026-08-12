# Bruce：Files / WebUI

## LittleFS

ESP32 内部文件系统。即使没有 SD 卡，也可以保存部分配置、脚本和文件。

常见操作：
- `View`：查看
- `Rename`：重命名
- `Copy`：复制
- `Delete`：删除
- `File Info`：文件信息

## SD

插入 microSD 后可管理：
- 日志
- 抓取结果
- 音频
- RF 文件
- 脚本
- 图片
- Wardriving 数据

## WebUI

**路径：** `Files → WebUI`

启动方式：
- `My Network`：使用当前已连接 Wi-Fi
- `AP Mode`：Cardputer 自己创建热点

适合用手机/电脑浏览器进行文件管理和部分远程操作。

默认账户常见为：
- Username：`admin`
- Password：`bruce`

建议首次使用后修改。
