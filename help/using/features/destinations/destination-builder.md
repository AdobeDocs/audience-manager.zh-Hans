---
description: 通过目标生成器，可创建基于cookie的或DNL URL目标。您无法使用目标生成器创建服务器到服务器(S2S)目标，但可以管理他们的区段映射。请与您的顾问联系以设置S2S目标。目标生成器位于受众数据>目标中。
seo-description: 通过目标生成器，可创建基于cookie的或DNL URL目标。您无法使用目标生成器创建服务器到服务器(S2S)目标，但可以管理他们的区段映射。请与您的顾问联系以设置S2S目标。目标生成器位于受众数据>目标中。
seo-title: 目标生成器
solution: Audience Manager
title: 目标生成器
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# 目标生成器 {#destination-builder}

[!UICONTROL Destination Builder] 允许您创建基于cookie的或 [!DNL URL] 目标。您不能创建server-to-server([!DNL S2S])目标， [!UICONTROL Destination Builder]但可以管理他们的区段映射。请与您的顾问联系以设置 [!DNL S2S] 目标。[!UICONTROL Destination Builder]**[!UICONTROL Audience Data > Destinations]**&#x200B;所处位置。

## 目标生成器设置 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包括以下部分和设置：

| [!UICONTROL Destination Builder] 区域 | 用途 |
|--- |--- |
| 基本信息 | 用于命名目标、描述目标类型、选择目标类型([!DNL URL] 或 [!DNL cookie])以及平台(全部、 [!DNL Android]浏览器或 [!DNL iOS])。 |
| 配置 | 包括以下控件： <br/><ul><li>将关键值数据传递 [!DNL URL] 到目标。您可以将数据作为单独的或序列化的键值对发送。有关详细信息，请参阅 [目标序列化](../../features/destinations/key-value-pairs.md#destination-serialized) 和 [标准和序列密钥-值对](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目标的元素，如cookie名称、域、大小、到期时间间隔、数据格式等。</li></ul> |
| 细分映射 | 允许您: <br/><ul><li>搜索、添加和管理与所有目标类型关联的区段。 </li><li>在各个区段上设置交付优先级(仅适用于 [!DNL cookie]基于细分的区段)。</li></ul> |

## 数据交付方法 {#data-delivery-methods}

通过将信息通过 [!DNL URL] 字符串传递、写入浏览器 [!DNL cookie]或脱机服务器到服务器数据传输，将信息发送到目标。

* [!DNL URL] 和基于cookie的目标以同步方式传输数据，当用户在页面上采取行动时。
* 服务器到服务器数据传输是异步的，在用户离开页面后可能很长一段时间。您选择的交付类型取决于您的业务需求以及特定数据合作伙伴想要或可以接收数据的方式。

有关更多信息，请参阅 [如何选择目标类型](../../features/destinations/destinations.md) 。