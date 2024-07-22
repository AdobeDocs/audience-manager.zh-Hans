---
description: 目标生成器允许您创建基于Cookie或DNL的URL目标。 无法使用目标生成器创建服务器到服务器(S2S)目标，但可以管理其区段映射。 请与您的顾问联系以设置S2S目标。 目标生成器位于受众数据>目标中。
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: 目标生成器
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# 目标生成器 {#destination-builder}

[!UICONTROL Destination Builder]允许您创建基于Cookie的目标或[!DNL URL]目标。 无法创建具有[!UICONTROL Destination Builder]的服务器到服务器([!DNL S2S])目标，但您可以管理其区段映射。 请与您的顾问联系以设置[!DNL S2S]目标。 [!UICONTROL Destination Builder]位于&#x200B;**[!UICONTROL Audience Data > Destinations]**&#x200B;中。

## 目标生成器设置 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder]包含以下部分和设置：

| [!UICONTROL Destination Builder]节 | 用途 |
|--- |--- |
| 基本信息 | 用于命名目标、描述目标并选择目标类型（[!DNL URL]或[!DNL cookie]）和平台（所有、[!DNL Android]、浏览器或[!DNL iOS]）。 |
| 配置 | 包含<br/>的控件<ul><li>将键值数据传递到[!DNL URL]目标。 您可以按单个或序列化键值对的形式发送数据。 有关详细信息，请参阅[目标序列化](../../features/destinations/key-value-pairs.md#destination-serialized)和[标准和序列键值对](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目标的元素，如Cookie名称、域、大小、过期时间间隔、数据格式等。</li></ul> |
| 区段映射 | 允许您：<br/><ul><li>搜索、添加和管理与所有目标类型关联的区段。 </li><li>在单个区段上设置投放优先级（仅适用于基于[!DNL cookie]的区段）。</li></ul> |

## 数据传输方法 {#data-delivery-methods}

通过将信息通过[!DNL URL]字符串传入、写入浏览器[!DNL cookie]或通过脱机服务器到服务器数据传输发送到目标。

* 当用户在页面上执行操作时，[!DNL URL]和基于Cookie的目标将同步传输数据。
* 服务器到服务器数据传输是异步的，可在用户离开页面后很长时间发生。 您选择的投放类型取决于您的业务要求以及特定数据合作伙伴希望或能够接收数据的方式。

有关详细信息，请参阅[如何选择目标类型](../../features/destinations/destinations.md)。
