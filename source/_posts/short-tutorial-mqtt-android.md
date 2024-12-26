---
title: 【精简版】新手快速接入 Meshtastic MQTT 官方服务器
date: 2024-12-19 18:31:20
description: 涵盖固件烧录、设备连接、基础设置以及消息测试，步骤清晰，操作简单，帮助用户在最短时间内完成 MQTT 配置并投入使用。
categories:
 - 教程
---

> 感谢广州群友 Yuri 将自己的经验提炼并整理成大纲，本文内容框架基于 Yuri 的贡献。

## 1. 烧录固件
- **nRF 芯片设备**：将固件文件拖到设备弹出的 U 盘窗口中完成烧录。
- **ESP32 设备**：使用网页串口工具烧录固件（确保电脑安装串口驱动）。具体操作可参考这篇为 [Ebyte EoRa 烧录固件的文章](http://localhost:4000/flash-meshtastic-firmware-ebyte-eora-s3/)。

## 2. 连接设备
1. **安装手机 APP**，在设备页面点击「加号」添加蓝牙设备，例如：Meshtastic_1234。
2. **选择设备**并输入配对码：
   - 有屏幕设备：输入设备屏幕显示的配对码。
   - 无屏幕设备：默认配对码为 **123456**。

## 3. 设置设备（安卓）

iOS 设置请参考 MeshCN 社区的另一篇文章—— [《如何设置 Meshtastic MQTT 功能》](https://meshcn.net/how-to-connect-meshtastic-mqtt/)。

1. **地区设定**  
   - 在设备页面右上角，将地区选项由默认的 **UNSET** 改为 **CN (China)**。
   - 设备会自动重启并重新连接。

2. **MQTT 设置**  
   - 点击右上角三点菜单，选择「设备设定」。  
   - 打开以下选项：
     - MQTT enable
     - Proxy to client enable
     - Map reporting 
   - 点击「传送」，设备会重启。

3. **频道设置**  
   - 进入 **Channels**，选择 **0 LongFast**（iOS 端叫 Primary Channel）：
     - 打开 Uplink enable
     - 打开 Downlink enable
     - 打开 Position enable  
   - 点击「存储」并「传送」，返回主菜单。

4. **LoRa 设置**  
   - 打开 **OK to MQTT**，然后点击「传送」，设备会再次重启。

## 4. 测试连接
1. 确保手机能正常联网（**Proxy to client enable** 依赖手机网络转发 MQTT 数据）。
2. 返回主页面，进入 **0 LongFast**（iOS 称为 **Primary Channel**），发送一条消息，测试发送和接收功能，这样可以测试 MQTT 服务器的成效。注意消息传输约需 1 分钟。

设置完成！🎉

---

有任何问题可以访问 [MeshCN - Meshtastic 中国社区](https://meshcn.net)。