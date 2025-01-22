---
title: 如何为你的 ESP32 Meshtastic 节点添加铃声
date: 2025-01-21 10:12:20
thumbnail: /how-to-add-buzzer-to-diy-esp32-heltec-lora-meshtastic-node/kevin-albrich-6HTTlcLwnBc-unsplash-cropped.webp
description: "为你的 Meshtastic DIY 项目加点「声」色！这篇文章将带你轻松搞定如何为 ESP32 Lora Meshtastic 节点添加蜂鸣器。不仅硬件布线手把手教你，软件设置也一步步详解。"
categories:
 - 教程
tags:
 - 蜂鸣器
 - 铃声
mathjax: false
---

{% note info 翻译声明 %}

本文翻译自 Adrelien 的文章《 [How To Add Buzzer To Your Meshtastic Node](https://adrelien.com/blog/how-to-add-buzzer-to-diy-esp32-heltec-lora-meshtastic-node/) 》。他的博客中有许多有趣且创新的 Meshtastic 相关文章，内容丰富且实用。强烈推荐读者感兴趣的话去拜读学习，相信你会发现更多灵感！

{% endnote %}  

在本指南中，我们将向你展示如何为现有的 ESP32 Lora Meshtastic 节点添加蜂鸣器（buzzer）。本指南同样适用于其他基于 ESP32 的开发板，如 Heltec V3 Lora、TTGo 或 T-Beam，但可能需要进行一些调整。

## 硬件准备

首先，让我们准备需要的硬件：

![硬件图片](https://adrelien.com/blog/content/images/2024/03/How-To-Add-Buzzer-To-DIY-ESP32---Heltec-Lora--Meshtastic-Node-1.png)

## 组装

硬件准备好后，我们开始布线。以下是布线图。

### 蜂鸣器 - DIY ESP32 Meshtastic 节点

![布线图](https://adrelien.com/blog/content/images/2024/03/How-To-Add-Buzzer-To-DIY-ESP32---Heltec-Lora--Meshtastic-Node.png)  

蜂鸣器 - DIY ESP32 Meshtastic 节点  

- 正极 -> GPIO 15  
- 负极 -> GND  

如果你使用的是其他基于 ESP32 的开发板（如 Heltec V3 Lora、TTGo 或 T-Beam），请选择一个支持数字信号、带上拉或下拉电阻的 GPIO 引脚，并确保它未被其他组件占用。然后，按照指南使用你选择的引脚，无需使用说明中的特定引脚号。

在电路中加入电容是良好的实践，可以隔离电路的不同部分。

需要注意，连接的顺序可能会有所不同。请根据你的组件上的标签和提供的布线图进行连接。细心对照这些细节可以确保连接无误，避免潜在问题或损坏组件。

完成布线后，请仔细检查你的连接是否与建议的布局一致，再继续下一步。

## Meshtastic 设置

本指南中的设置仅适用于基于 ESP32（比如 ESP32、ESP32-S3、ESP32-C3）的 Meshtastic 设备。如果你使用的是基于 nRF52 的 Meshtastic 设备，则需要进行特殊的配置设置。关于 nRF52 的详细设置说明，社区会在后续文章中为大家提供详细的指导，敬请期待！

1. 打开 Meshtastic 应用（本指南以 iOS 为例）。  
2. 进入设置页面。  
3. 在模块配置部分，找到「外部通知」选项。  
4. 启用以下设置：启用通知、接收消息时提醒、使用 PWM 蜂鸣器。  
5. 向下滚动，找到主 GPIO 设置，启用 激活，并将 输出引脚 GPIO 设置为 GPIO 15。  
6. 返回设置页面，进入铃声设置，选择你喜欢的铃声旋律。

{% note info 编者注 %}

Meshtastic 蜂鸣器铃声旋律使用 RTTTL（铃声传输文本语言）铃声格式定义。`device.buzzer_gpio` 指定设备中外部电路连接的 GPIO 引脚。对于支持 PWM 蜂鸣器的设备，可以通过将 `use_pwm` 属性设置为 `TRUE`，使用蜂鸣器进行通知。在这种情况下，将忽略普通蜂鸣器引脚设置，而改用 `device.buzzer_gpio`。

如果启用 PWM 模式，设备会使用 RTTTL 铃声作为通知音。你可以在 [这里](https://www.laub-home.de/wiki/RTTTL_Songs) 找到 RTTTL 铃声的示例，并通过客户端应用程序将其上传到设备。

**注意：** 基于 ESP32 的开发板中，GPIO 34 到 39 是输入专用引脚（GPIs），不支持内部上拉或下拉电阻，且无法用作输出。因此，这些引脚无法用作输出引脚。

以下是《星球大战》主题曲的 RTTTL 铃声：

```text
StarWars:d=4,o=5,b=45:32p,32f#,32f#,32f#,8b.,8f#.6,32e6,32d#6,32c#6,8b.6,16f#.6,32e6,32d#6,32c#6,8b.6,16f#.6,32e6,32d#6,32e6,8c#.6,32f#,32f#,32f#,8b.,8f#.6,32e6,32d#6,32c#6,8b.6,16f#.6,32e6,32d#6,32c#6,8b.6,16f#.6,32e6,32d#6,32e6,8c#6
```

以下是《欢乐颂》的 RTTTL 铃声：

```text
OdeToJoy:d=4,o=5,b=120:16e,16e,16f,16g,8g,16f,16e,16d,8c,8c,16d,16e,8e,16d,16d,16e,16f,8f,16e,16d,16c,8c,8d,8g,8e,16e,16f,16g,8g,16f,16e,16d,8c,8c
```

以下是《超级马里奥兄弟》主题曲的 RTTTL 铃声：

```text
SuperMario:d=4,o=5,b=200:16e6,16e6,16e6,8c6,16e6,8g6,16g,8c6,16g,16e,16a,16b,8a#,16a,16g,16e6,16g6,8a6,16f6,16g6,16e6,8c6,16d6,8b,16c6
```


以下是《诺基亚》手机 RTTTL 铃声：

```text
NokiaTune:d=4,o=5,b=100:16e6,16d6,16f#6,16g#6,16a6,16b6,16c#7,16d7,8b6,8a6,16g#6,16f#6,8e6,8d6,16e6,16b5,16a5,16d6,16e6
```


以下是《生日快乐》的 RTTTL 铃声：

```text
HappyBirthday:d=4,o=5,b=100:8g,8g,8a,4g,4c6,4b,8g,8g,8a,4g,4d6,4c6,8g,8g,8g6,4e6,4c6,4b,4a,8f6,8f6,8e6,4c6,4d6,4c6
```

{% endnote %}  

以下是一个示例 RTTTL 铃声：

```
Halloween:d=4,o=5,b=180:8d6,8g,8g,8d6,8g,8g,8d6,8g,8d#6,8g,
8d6,8g,8g,8d6,8g,8g,8d6,8g,8d#6,8g,8c#6,8f#,8f#,8c#6,8f#,8f#,
8c#6,8f#,8d6,8f#,8c#6,8f#,8f#,8c#6,8f#,8f#,8c#6,8f#,8d6,8f#
```

## 结论

为你的 DIY ESP32 Meshtastic 节点添加蜂鸣器是一个简单有趣的过程。通过仔细遵循本指南中的硬件清单和逐步操作说明，你可以轻松地将蜂鸣器集成到现有系统中。指南提供了清晰的硬件组装步骤，包括蜂鸣器和引脚连接，确保实现流畅的安装过程。