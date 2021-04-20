---
description: 定义和指向其他相关资料的链接。
seo-description: 定义和指向其他相关资料的链接。
seo-title: 术语表
solution: Audience Manager
title: 术语表
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: Reference
exl-id: 9e2ee3d3-01b2-4038-abda-fedf0f16f163
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 100%

---

# 术语表{#glossary}

定义和指向其他相关资料的链接。

## A-B {#a-b}

**算法建模**

使用 [!UICONTROL Algorithmic Modeling] 扩展范围，以包含除已确定的核心用户之外的其他用户。该功能可帮助您通过自动数据分析发现新的独特受众。在 **[!UICONTROL Audience Data > Models]** 中管理 [!UICONTROL Algorithmic Models]。

请参阅[了解算法模型](../features/algorithmic-models/algo-models-overview.md)。

**BAAAM**

[!UICONTROL Bulk Management Tools]。[!DNL Audience Manager] 中的 [!UICONTROL Bulk Management Tools] 是一系列基于 Microsoft Excel 的工具，通过这些工具，您可以一次创建、修改或删除多个对象。您可以处理数据源、派生的信号、目标、文件夹、区段和特征。该功能使用带有宏的 Microsoft Excel 电子表格，这些宏可对 [!DNL Audience Manager] API 进行经过验证的安全调用。

请参阅[批量管理工具](../reference/bulk-management-tools/bulk-management-intro.md)。

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]。[!UICONTROL CDF] 文件是批量下载的 [!DNL Audience Manager] 收集数据，通过该文件，您可以处理超出用户界面所定限制的 [!DNL Audience Manager] 数据。[!UICONTROL CDF] 文件包含的数据与 [!DNL Audience Manager] 事件调用 (`/event`) 发送到我们服务器的数据相同。其中包括用户 ID、特征 ID、区段 ID 和通过事件调用捕获的所有其他参数。

请参阅[客户数据信息源](../features/cdf-files.md)。

**CRM ID**

CRM ID 是客户在其 CRM 系统中用于识别用户的 ID。在 Audience Manager 中，我们使用是 DPUUID，而不是 CRM ID。

有关 DPUUID 的说明，请参阅 [Audience Manager 中的 ID 索引](../reference/ids-in-aam.md)。



**客户可寻址受众**

在[可寻址受众](/help/using/features/addressable-audiences.md)中，此量度表示设备满足以下条件：
* 在回顾时间范围内已实现基于规则的特征或已载入的特征
   **且**
* ID 已与选定目标同步，不论同步次数是多少。



**客户属性**

请参阅 [!DNL Experience Cloud Core Services] 产品文档中的[客户属性](https://docs.adobe.com/content/help/zh-Hans/core-services/interface/customer-attributes/attributes.html)。



**客户匹配率**

客户可寻址受众 ÷ 客户总受众，以 % 表示。请参阅[可寻址受众](/help/using/features/addressable-audiences.md)。



**客户总受众**

在[可寻址受众](/help/using/features/addressable-audiences.md)中，此量度表示在回顾时间范围内，已实现您的资产中某个基于规则的特征或某个从离线文件载入的特征的设备的数量。



**demdex.net**

demdex.net 是由 [!DNL Adobe] 控制的旧版域。它反映了 [!DNL Audience Manager] 在收购前的原始名称 ([!DNL Demdex])。[!DNL Adobe] 于 2011 年收购 [!DNL Demdex] 公司并将其更名为 [!DNL Audience Manager]。对 `demdex.net` 域发起的所有 HTTP 调用都会发送到 [!DNL Adobe]。

请参阅[了解 Demdex 域调用](../reference/demdex-calls.md)。



**DAID**

[!UICONTROL Device Advertising IDs] 是用于标识移动设备的唯一设备标识符。此类 ID 由设备制造商而非 Adobe 分配。[!DNL Audience Manager] 中同时支持 iOS 和 Android 设备 ID。

请参阅 [Audience Manager 中的 ID 索引](../reference/ids-in-aam.md)。



**目标**

在 [!DNL Audience Manager] 中，目标是指要与其共享数据的任何其他系统（广告服务器、DSP、广告网络等）。在我们的 UI 中，[!UICONTROL Destination Builder] 提供了用于创建和管理这些数据传输流程的工具。[!DNL Audience Manager] 目标功能位于 **[!UICONTROL Audience Data > Destinations]** 中。



**DIL**

[!UICONTROL Data Integration Library] 是 [!DNL Audience Manager] 用于收集用户交互数据的 API 库。请参阅[数据集成库 (DIL) API](../dil/dil-overview.md)。



**DPM**

[!UICONTROL Data Provider Match]。DPM 可告知 [!DNL Adobe] 内部系统，来自 [!DNL Audience Manager] 或 ID 服务的调用正在传递客户数据以进行同步或正在请求 ID。请参阅[了解 Demdex 域调用](../reference/demdex-calls.md)。

## E-F {#e-f}

**Experience Cloud ID (ECID)**

以前称为 [!DNL Marketing Cloud] ID（MID 或 MCID）。[!DNL Experience Cloud] ID 是 ID 服务的核心。它是网站访客的唯一永久标识符。请参阅 Cookie 和 [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/intro/cookies.html)。



**文件夹特征**

对文件夹分类系统内的特征进行自动分组。层级结构中的每个文件夹都会自动创建一个可用于定义区段的特征。

请参阅[文件夹特征：关于](../features/traits/about-folder-traits.md)。



**频度上限**

广告商希望向最终用户显示指定创意内容的次数限制。您可以在 [!UICONTROL Segment Builder] 中配置各种频度上限表达式。

请参阅[回访间隔和频度](../features/segments/recency-and-frequency.md)。

## G-H {#g-h}

**GAID**

Google Advertising ID，即 Google 为运行 Android 操作系统的硬件设备分配的唯一设备 ID。请参阅 [Audience Manager 中的 ID 索引](../reference/ids-in-aam.md)。



**GUID**

全局唯一标识符的缩写。在 [!DNL Audience Manager] 中，我们不使用术语 GUID。在我们的用例中，GUID 是 [!DNL Audience Manager] UUID。请参阅 [Audience Manager 中的 ID 索引](../reference/ids-in-aam.md)。

## I-J {#i-j}

**IDFA**

广告商的标识符，即 Apple 为其产品分配的唯一设备 ID。请参阅 [Audience Manager 中的 ID 索引](../reference/ids-in-aam.md)。



**入站**

将受众数据从其他来源发送到 [!DNL Audience Manager] 的过程。请参阅[发送受众数据](/help/using/integration/sending-audience-data/send-audience-data.md)。



**集成代码**

使用 [!DNL Audience Manager] UI 或 API 时，您可以选择在创建特征、区段或数据源时添加集成代码。在以下用例中，集成代码的用途各不相同：

* [!UICONTROL Traits]：集成代码是指供内部业务流程使用的 ID、SKU 或其他值的字段。可选。
* [!UICONTROL Segments]：集成代码是指用户定义的 ID 或其他特定于公司的信息的字段。可选。
* [!UICONTROL Data Sources]：当您要创建跨设备数据源、使用 Adobe Experience Platform Identity Service 或使用 [!UICONTROL Profile Merge Rules] 时，需要集成代码。有关更多信息，请参阅[创建数据源](../features/manage-datasources.md#create-data-source)。

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

请参阅[算法建模](../reference/aam-glossary.md#a-b)。

## M-N {#m-n}

**MCID**、**MID**

请参阅 [Experience Cloud ID](../reference/aam-glossary.md#e-f)。

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]。[!UICONTROL PCS] 是在 Apache Cassandra 上运行的大型数据库。它可以存储通过服务器到服务器传输和 [!DNL DCS] 接收的有关活动用户的数据。[!UICONTROL PCS] 数据包含设备 ID、经过验证的配置文件 ID 以及与这些 ID 关联的特征。

请参阅[数据收集组件](../reference/system-components/components-data-collection.md)。



**配置文件链接**

请参阅[定义的配置文件合并规则选项](../features/profile-merge-rules/merge-rule-definitions.md)。



**配置文件合并规则**

通过 [!UICONTROL Profile Merge Rules]，您可以控制 [!DNL Audience Manager] 用于分段的数据类型。

请参阅[定义的配置文件合并规则选项](../features/profile-merge-rules/merge-rule-definitions.md)。

## Q-R {#q-r}

**实现**

网站上的访客通过执行某个操作而符合某个特征的过程。您可以使用[访客配置文件查看器](../features/visitor-profile-viewer.md)工具获取有关特定用户特征实现的信息。

## S-T {#s-t}

**区段**

区段（或受众）是指一组共享通用属性的用户。

请参阅[区段：目的、构成和规则](../features/segments/segments-purpose.md)。



**区段可寻址受众**

在[可寻址受众](/help/using/features/addressable-audiences.md)中，此量度表示在报表回顾期间属于该区段且在您的网站上具有活动的 ID 同步的用户数量。通过在 [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) 中获得的特征，区段可以同时包含您自己的第一方数据以及第二方数据和第三方数据。



**总区段人口**

在[可寻址受众](/help/using/features/addressable-audiences.md)中，此量度表示在报表回顾期间属于区段成员的设备总数。



**区段匹配率**

区段可寻址受众 ÷ 总区段人口，以 % 表示。请参阅[可寻址受众](/help/using/features/addressable-audiences.md)。



**信号**

信号是 [!DNL Audience Manager] 中的最小数据单元，以键值对表示。

请参阅[信号、特征和区段](../reference/signal-trait-segment.md)。



**特征**

特征由一个或多个信号组合而成。请参阅[信号、特征和区段](../reference/signal-trait-segment.md)。



**特征人口**

请参阅[区段生成器中的特征和区段人口数据](../features/segments/segment-builder-data.md)。

**TTL（存留期）**

TTL 定义符合条件的访客在一个特征中保留的天数。TTL 是针对特征而非区段设置的。如果访客在 TTL 间隔结束前看不到符合条件的特征，则会从区段中移除。有关更多信息，请参阅[区段和特征存留期说明](/help/using/features/traits/segment-ttl-explained.md)。



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] 独特用户 ID。请参阅 [Audience Manager 中的 ID 索引](../reference/ids-in-aam.md)。



**访客 ID**

[!DNL Experience Cloud] ID 服务（以前称为访客 ID）提供了一个通用的永久性 ID，用于在 [!DNL Experience Cloud] 的所有解决方案中标识您的访客。

请参阅 [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html) 文档。

## W-X-Y-Z {#w-z}
