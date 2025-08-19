---
description: 本文档介绍 Audience Manager 如何管理客户数据。
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: GDPR UI， GDPR API， CCPA，隐私，同意，模糊处理，治理
title: 数据管理
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 90%

---

# 数据管理

## 概述 {#overview}

在 Audience Manager 中，数据管理是指客户数据在 Audience Manager 中的生命周期，包括[收集和模糊处理 IP 地址](data-governance.md#collecting-ip-addresses)、[数据保留](data-governance.md#data-retention)和[跨境数据传输](data-governance.md#data-transfers)。

## 收集IP地址和IP地址模糊处理 {#collecting-ip-addresses}

访问客户网站的访客 [!DNL IP] 地址会被传输到 Adobe [!DNL Data Processing Center] ([!DNL DPC])，[!DNL IP] 地址可能存储在那里。根据访客的网络配置，[!DNL IP] 地址不一定能代表访客计算机的 [!DNL IP] 地址。例如，[!DNL IP] 地址可能为网络地址转换 (NAT) 防火墙、[!DNL HTTP] 代理或互联网网关的外部 [!DNL IP] 地址。

**IP 模糊处理方法：**&#x200B;按照“通过设计保护隐私”的原则，Adobe Audience Manager 允许客户在 UI 中启用 [!DNL IP] 模糊处理，范围可以是全球所有地区，也可以是特定国家/地区。启用此设置后，在将 [!DNL IP] 地址摄取到 Audience Manager 后，将立即丢弃 [!DNL IP] 地址的最后一个八位字节（最后一部分）。在进行任何处理操作（包括选择对 [!DNL IP] 地址进行任何地理位置查询或记录）之前，Audience Manager 会先丢弃 [!DNL IP] 地址的这个部分。例如：

* 之前：`255.255.255.255`
* 之后：`255.255.255.0`

>[!NOTE]
>
>请参阅[IP地址模糊处理](../../features/administration/ip-obfuscation.md)，了解如何在Audience Manager用户界面中启用[!DNL IP]地址模糊处理。

观看以下视频，了解 Audience Manager 如何进行 [!DNL IP] 地址模糊处理。

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**地域划分：**&#x200B;如果启用 [!DNL IP] 地址模糊处理，则 [!DNL IP] 地址的其余八位字节仍可用于 Audience Manager 中的地域划分和报表。如果不启用 [!DNL IP] 地址模糊处理，Audience Manager 将使用完整的 [!DNL IP] 地址。您可以使用地域划分功能，不论是否使用 [!DNL IP] 模糊处理，该功能都可以让您通过地理区域来识别 [!DNL IP] 位置，但是在使用模糊处理的情况下，会略微损失一些精确度。若启用 [!DNL IP] 地址模糊处理，城市级别信息的获取很有可能会受到重大影响。而地区和国家级别信息的获取应该只会受到轻微影响。地域划分数据只精确到城市级别或邮政编码级别，而不能精确到个人级别。进一步了解[地理定位](../../features/traits/trait-geotarget-keys.md)以及如何使用地理变量设置特征。

## Audience Manager中的数据保留 {#data-retention}

及时应用适当、安全的数据保留策略是实现数据隐私法规合规的重要环节。Audience Manager 客户能够通过定义所需的 TTL（存留期）为特征和区段设置自定义保留期。有关保留期的更多详细信息，请参阅[数据保留常见问题解答](../../faq/faq-privacy.md)。

## 跨境数据传输 {#data-transfers}

在跨境传输客户个人数据时，Audience Manager 会遵守所有适用法规。有关更多信息，请访问 [Adobe 隐私中心](https://www.adobe.com/cn/privacy/eudatatransfers.html)。
