---
title: Heltec T114 （带GPS）便携 Meshtastic 节点方案
date: 2024-12-21 11:28:20
canonical_url: https://ameow.xyz/archives/meshtastic-heltec-t114
description: "基于 Heltec T114（带 GPS）的便携式 Meshtastic 节点方案，采用低功耗设计，支持一周续航，适合随身携带。本文详细介绍了 BOM 清单、选购建议以及注意事项，帮助用户快速搭建经济实用的 LoRa 节点设备。"
author:
  name: "阿猫"
categories:
 - 入门
---

> 本文转载自群友阿猫，原文地址：[阿猫的博客](https://ameow.xyz/archives/meshtastic-heltec-t114) 。感谢阿猫的精彩分享！

## 概要

基于 nRF52840 的方案，使得开发板本身功耗非常低，搭配 2200mAh 的电池，开 GPS 的情况下，续航可达一周，适合随身携带使用。整体成本在 ¥300 左右。

## BOM

| 类型       | 项目                         | 参考价格 | 备注                            | 购买链接                                                     |
| ---------- | ---------------------------- | -------- | ------------------------------- | ------------------------------------------------------------ |
| 开发板     | Heltec T114 470-510-v1       | ¥189     | 注意不要买错频段，选 470-510 的 | [淘宝](http://e.tb.cn/h.T3sL0A98sqsMWmp?tk=5zeC3EdoaM2)      |
| 天线转接线 | IPEX 转 SMA 母头             | ¥3.5     |                                 | [淘宝](http://e.tb.cn/h.T3sJRQFmVT0OZ80?tk=JWJV3EdqDW9)      |
| 电池       | 803160 聚合物锂电池 2200 mAh | ¥16.9    |                                 | [淘宝](http://e.tb.cn/h.Te3l35mkXOLrjuf?tk=tTkC3Edpe7v)      |
| 天线       | gizont GT-7702-1             | ¥20      | 需要备注做 470 MHz 频段         | [淘宝](http://e.tb.cn/h.T3sHhOipJB5bDG7?tk=T2mS3EdsRVe)      |
| GPS 模块   | Heltec                       | ¥53      | 在买开发板时选择 GNSS 模块加购  |                                                              |
| 外壳       | 3D 打印外壳                  | -        |                                 | [Printables](https://www.printables.com/model/982046-h2t-case-for-heltec-t114-with-gps-running-meshtast) |
| 外壳螺丝   | M3x12 螺丝                   | -        |                                 |                                                              |
| 总成本     |                              | ¥274.4   |                                 |                                                              |

## 备注

1. 开发板选择 **470-510** 频段，一定要看清楚不要选错！
2. 天线需要备注 **470 MHz**，不适用于该频率的天线上机有可能烧坏功放！
3. 天线可以根据需要另外选择，只要是 SMA 公头即可。如果使用推荐的外壳，最大支持天线直径 12.7mm。
4. GPS 模块是可选的。