---
description: Destination Builder允许您创建基于Cookie或DNL的URL目标。 不能使用Destination builder创建服务器到服务器(S2S)目标，但可以管理其区段映射。 请与顾问联系以设置S2S目标。 目标生成器位于“受众数据”>“目标”中。
seo-description: Destination Builder允许您创建基于Cookie或DNL的URL目标。 不能使用Destination builder创建服务器到服务器(S2S)目标，但可以管理其区段映射。 请与顾问联系以设置S2S目标。 目标生成器位于“受众数据”>“目标”中。
seo-title: 目标生成器
solution: Audience Manager
title: 目标生成器
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# 目标生成器 {#destination-builder}

[!UICONTROL Destination Builder] 允许您创建基于Cookie或目标的 [!DNL URL] 内容。 您不能使用创建服务器到服务器([!DNL S2S])目标 [!UICONTROL Destination Builder]，但可以管理其段映射。 请联系您的顾问以设置目 [!DNL S2S] 标。 [!UICONTROL Destination Builder] 位于 **[!UICONTROL Audience Data > Destinations]**。

## 目标生成器设置 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包括以下部分和设置：

| [!UICONTROL Destination Builder] 区域 | 用途 |
|--- |--- |
| 基本信息 | 用于命名目标、描述它并选择目标类型([!DNL URL] 或 [!DNL cookie])和平台(all、 [!DNL Android]、browser或 [!DNL iOS])。 |
| 配置 | 包括以下控件： <br/><ul><li>将关键值数据传递到目 [!DNL URL] 标。 您可以以单个或序列化键值对的形式发送数据。 有关详细信息，请参 [阅目标序列化](../../features/destinations/key-value-pairs.md#destination-serialized) 、 [标准和序列键值对](../../features/destinations/key-value-pairs.md)。 </li><li>Cookie目标的元素，如Cookie名称、域、大小、过期间隔、数据格式等。</li></ul> |
| 区段映射 | 允许您: <br/><ul><li>搜索、添加和管理与所有目标类型关联的区段。 </li><li>为各个细分设置交付优先级(仅 [!DNL cookie]针对基于细分)。</li></ul> |

## 数据交付方法 {#data-delivery-methods}

通过字符串传递信息、写入浏览器或通过离线服务器到服务器 [!DNL URL] 的数据传输， [!DNL cookie]将信息发送到目标。

* [!DNL URL] 当用户在页面上执行操作时，基于cookie的目标同步传输数据。
* 服务器到服务器的数据传输是异步的，并且可能在用户离开页面后很久才进行。 您选择的交付类型取决于您的业务要求以及特定数据合作伙伴希望或能够接收数据的方式。

有关 [详细信息，请参阅如何选择目标类型](../../features/destinations/destinations.md) 。