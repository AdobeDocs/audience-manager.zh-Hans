---
description: Destination Builder允许您创建基于Cookie或DNL URL的目标。 不能使用目标生成器创建服务器到服务器(S2S)目标，但可以管理其段映射。 请与顾问联系以设置S2S目标。 目标生成器位于“受众数据”>“目标”中。
seo-description: Destination Builder允许您创建基于Cookie或DNL URL的目标。 不能使用目标生成器创建服务器到服务器(S2S)目标，但可以管理其段映射。 请与顾问联系以设置S2S目标。 目标生成器位于“受众数据”>“目标”中。
seo-title: 目标生成器
solution: Audience Manager
title: 目标生成器
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# 目标生成器 {#destination-builder}

[!UICONTROL Destination Builder] 允许您创建基于cookie或目 [!DNL URL] 标。 不能使用创建服务器到服务器([!DNL S2S])目标， [!UICONTROL Destination Builder]但可以管理其段映射。 请与顾问联系以设置目 [!DNL S2S] 标。 [!UICONTROL Destination Builder] 位于 **[!UICONTROL Audience Data > Destinations]**。

## 目标生成器设置 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包括以下部分和设置：

| [!UICONTROL Destination Builder] 区域 | 用途 |
|--- |--- |
| 基本信息 | 用于命名目标、描述它并选择目标类型([!DNL URL] 或 [!DNL cookie])和平台(全部、 [!DNL Android]浏览器或) [!DNL iOS]。 |
| 配置 | 包括以下控件： <br/><ul><li>将键值数据传递到目 [!DNL URL] 标。 您可以以单个或序列化键值对的形式发送数据。 有关详细信息，请 [参阅目标序](../../features/destinations/key-value-pairs.md#destination-serialized) 列 [化以及标准和序列键值对](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目标的元素，如Cookie名称、域、大小、过期间隔、数据格式等。</li></ul> |
| 区段映射 | 允许您: <br/><ul><li>搜索、添加和管理与所有目标类型关联的区段。 </li><li>为各个区段设置投放优先级(仅 [!DNL cookie]针对基于区段)。</li></ul> |

## 数据投放方法 {#data-delivery-methods}

通过字符串、写入到浏览器或通过离线的服务器 [!DNL URL] 到服务器数据传输， [!DNL cookie]将信息传递到目标。

* [!DNL URL] 当用户在页面上执行操作时，基于cookie的目标会同步传输数据。
* 服务器到服务器数据传输是异步的，在用户离开页面后很长时间可能会发生。 您选择的投放类型取决于您的业务需求以及特定数据合作伙伴希望或可以接收数据的方式。

有关 [详细信息，请参阅如何选择目标](../../features/destinations/destinations.md) 类型。