---
description: 目标生成器允许您创建基于Cookie或DNL URL的目标。 您无法使用目标生成器创建服务器到服务器(S2S)目标，但可以管理其区段映射。 请联系您的顾问以设置S2S目标。 目标生成器位于“受众数据”>“目标”中。
seo-description: 目标生成器允许您创建基于Cookie或DNL URL的目标。 您无法使用目标生成器创建服务器到服务器(S2S)目标，但可以管理其区段映射。 请联系您的顾问以设置S2S目标。 目标生成器位于“受众数据”>“目标”中。
seo-title: 目标生成器
solution: Audience Manager
title: 目标生成器
feature: 目标基础知识
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# 目标生成器 {#destination-builder}

[!UICONTROL Destination Builder] 允许您创建基于Cookie的或目 [!DNL URL] 标。您无法使用[!UICONTROL Destination Builder]创建服务器到服务器([!DNL S2S])目标，但可以管理其区段映射。 请联系您的顾问以设置[!DNL S2S]目标。 [!UICONTROL Destination Builder] 位于 **[!UICONTROL Audience Data > Destinations]**&#x200B;中。

## 目标生成器设置{#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包括以下部分和设置：

| [!UICONTROL Destination Builder] 区域 | 用途 |
|--- |--- |
| 基本信息 | 用于命名目标并描述该目标，并选择目标类型（[!DNL URL]或[!DNL cookie]）和平台（所有、[!DNL Android]、浏览器或[!DNL iOS]）。 |
| 配置 | 包括以下控件：<br/><ul><li>将键值数据传递到[!DNL URL]目标。 您可以将数据作为单个或序列化的键值对发送。 有关详细信息，请参阅[目标序列化](../../features/destinations/key-value-pairs.md#destination-serialized)和[标准和序列键值对](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目标的元素，如Cookie名称、域、大小、过期间隔、数据格式等。</li></ul> |
| 区段映射 | 允许您: <br/><ul><li>搜索、添加和管理与所有目标类型关联的区段。 </li><li>在单个区段上设置交付优先级（仅适用于基于[!DNL cookie]的区段）。</li></ul> |

## 数据提交方法{#data-delivery-methods}

将信息通过[!DNL URL]字符串传递到目标，通过写入浏览器[!DNL cookie]或通过离线服务器到服务器数据传输发送到目标。

* [!DNL URL] 当用户在页面上执行操作时，基于cookie的目标会同步传输数据。
* 服务器到服务器数据传输是异步的，并且在用户离开页面后很长时间内，可能会发生。 您选择的交付类型取决于您的业务需求以及特定数据合作伙伴希望或能够接收数据的方式。

有关详细信息，请参阅[如何选择目标类型](../../features/destinations/destinations.md)。
