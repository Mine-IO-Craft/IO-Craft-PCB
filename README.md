# Mine IO Craft

基于 ESP32-S3 的主控板，使用嘉立创 EDA 专业版（EasyEDA Pro）设计。

## 主要功能

**主控**

- ESP32-S3-WROOM-1-N16R8（16 MB Flash / 8 MB PSRAM，2.4 GHz Wi-Fi + BLE）

**电源**

- 1S 锂电池充放电（ETA6002E8A：USB 5V 充电 + 升压输出）
- SY8089A 同步降压，输出 3.3V 数字主轨
- PH2.0-2P 电池接口，USB-C 供电输入

**显示与交互**

- 20-pin FPC 接口（上接式），用于连接 LCD 显示屏
- 旋转编码器（EC251V202000）
- BOOT / RESET 按键
- 8 颗 WS2812C-2427 可编程 RGB 灯（菊花链）

**接口**

- 26-pin（2×13，2.54 mm）扩展排针，引出 GPIO / 3.3V / VOUT / GND
- 2 路 USB-C：
  - **USB1**（丝印 JTAG 的口）：CH340C USB 转串口，用于固件下载与串口通信
  - **USB2**：另一路 Type-C

## 注意事项

1. **没有电池反接保护。** 连接电池前请确认极性（PH2.0-2P：1 = VBAT，2 = GND）。接反可能直接损坏充电芯片。
2. **只支持 1S 锂电池**（标称 3.7 V，满电 4.2 V）。不要接 2S 及以上电池组。
3. **下载固件请使用 USB1**（丝印 JTAG 的那个口），USB2 不用于固件下载。

## 文件

- `Mine IO Craft.eprj2` — EasyEDA Pro 工程（原理图 + PCB）
- `板框.DWG` / `板框.DXF` / `板框.SLDPRT` — 板框机械图（圆形 Ø70 mm）
- `ProLib_1pcs_2026-10-14.elibz2` — 个人库导出

## 打开方式

用立创 EDA 专业版（EasyEDA Pro）打开 `Mine IO Craft.eprj2`。
