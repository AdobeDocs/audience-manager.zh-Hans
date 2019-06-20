---
description: 定义和链接进一步阅读。
seo-description: 定义和链接进一步阅读。
seo-title: 术语表
solution: Audience Manager
title: 术语表
uuid: 01fc26f5-db9 d-4e90-b4 c1-27c6 a510 acc
translation-type: tm+mt
source-git-commit: d5a8b763d2d0d1ceebe2252ebd283943dcbc1754

---


# 术语表{#glossary}

定义和链接进一步阅读。

## A-B {#a-b}

**算法建模**

[!UICONTROL Algorithmic Modeling] 用作扩展触及范围以外用户的触及范围。该功能可帮助您通过自动数据分析发掘新的独特受众。Manage your [!UICONTROL Algorithmic Models] in **[!UICONTROL Audience Data > Models]**.

See [Understanding Algorithmic Models](../features/algorithmic-models/understanding-models.md#understanding-models).

<br> 

**巴哈马群岛**

[!UICONTROL Bulk Management Tools]。[!UICONTROL Bulk Management Tools] in [!DNL Audience Manager] in是一组基于Microsoft Excel的工具，允许您通过一次操作创建、修改或删除多个对象。您可以使用数据源、派生信号、目标、文件夹、区段和特征。The feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs.

See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]。[!UICONTROL CDF] 文件表示收集到的数据的批量下载， [!DNL Audience Manager] 使您能够在我们的用户界面限制之外处理 [!DNL Audience Manager] 数据。[!UICONTROL CDF] 文件包含一个 [!DNL Audience Manager] 事件调用( `/event`)发送到我们服务器的相同数据。这包括用户ID、特征ID、细分ID以及事件调用捕获的所有其他参数等数据。

See [Customer Data Feeds](../features/cdf-files.md).

<br> 

**CRM ID**

CRM ID是客户在自己的CRM系统中识别用户的ID。我们使用Audience Manager中的术语DPUUID，而不是CRM ID。

See DPUUID in the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**可接触客户的受众**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents devices that:
* 在回顾窗口中已找到基于规则的或已载入的特征
   **AND**
* 无论同步的时间如何，都可以与所选目标同步ID。

<br> 

**客户属性**

See [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**客户匹配率**

客户可寻址受众›客户总受众表示为%。See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**客户总受众**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of devices that have realized either a rule-based trait on your properties or an onboarded trait from your offline files during the look-back window.

<br> 

**demdex.net**

Demdex.net is a legacy domain controlled by [!DNL Adobe]. It reflects [!DNL Audience Manager]&#39;s original, pre-acquisition name ( [!DNL Demdex]). [!DNL Adobe] 2011年收购 [!DNL Demdex] 并更名 [!DNL Audience Manager]为公司。`demdex.net` 对域的所有HTTP调用都是发送到的调用 [!DNL Adobe]。

请参阅[了解 Demdex 域调用](../reference/demdex-calls.md)。

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] 是唯一的设备标识符，用于识别移动设备。这些ID由设备制造商而非Adobe分配。We support iOS and Android device IDs in [!DNL Audience Manager].

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**目标**

In [!DNL Audience Manager], a destination is any other system (ad server, DSP, ad network, etc.) 您希望与之共享数据的数据。[!UICONTROL Destination Builder] 我们的UI中提供了可用于创建和管理这些数据交付流程的工具。[!DNL Audience Manager] 目标功能 **[!UICONTROL Audience Data > Destinations]** 位于中。

<br> 

**DIL**

The [!UICONTROL Data Integration Library] is an API library used by [!DNL Audience Manager] to collect user interaction data. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]。It tells internal [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the ID service is passing in customer data for synchronization or requesting an ID. 请参阅[了解 Demdex 域调用](../reference/demdex-calls.md)。

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Previously named the [!DNL Marketing Cloud] ID (MID or MCID). [!DNL Experience Cloud] ID是ID服务的中心。它是网站访客的唯一永久标识符。See Cookies and the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html).

<br> 

**文件夹特征**

文件夹分类内特征的自动分组。层次结构中的每个文件夹都会自动创建一个可用于定义区段的特征。

See [Folder Traits: About](../features/traits/about-folder-traits.md).

<br> 

**频率上限**

广告商希望向最终用户展示给定创意的次数限制。You can configure various frequency capping expressions in [!UICONTROL Segment Builder].

See [Recency and Frequency](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GID**

Google Advertising ID是Google为运行Android操作系统的硬件设备分配的唯一设备ID。See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

全球唯一标识符的缩写。We don&#39;t use the term GUID in [!DNL Audience Manager]. In our case, the GUID is the [!DNL Audience Manager] UUID.
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

广告商标识符，Apple为其产品分配的唯一设备ID。See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**入站**

The process by which you can send audience data from other sources to [!DNL Audience Manager]. See [Sending Audience Data](/help/using/integration/sending-audience-data/send-audience-data.md).

<br> 

**集成代码**

When working with the [!DNL Audience Manager] UI or API, you have the option of adding an integration code when creating traits, segments, or data sources. 在这些情况下，集成代码提供不同的用途：

* [!UICONTROL Traits]：集成代码是ID、SKU或内部业务流程使用的其他值的字段。可选。
* [!UICONTROL Segments]：集成代码是用户定义ID或其他公司特定信息的字段。可选。
* [!UICONTROL Data Sources]：当您要创建跨设备数据源、使用Experience Cloud ID服务或使用时，需要集成代码 [!UICONTROL Profile Merge Rules]。See [Create a Data Source](../features/manage-datasources.md#create-data-source) for more information.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

See [Algorithmic Modeling](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**， **MID**

See the [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]。The [!UICONTROL PCS] is a large database, running on Apache Cassandra. It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] 数据包括设备ID、经过身份验证的配置文件ID及其关联特征。

See [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**配置文件链接**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**个人资料合并规则**

[!UICONTROL Profile Merge Rules] 可让您控制数据 [!DNL Audience Manager] 的类型用于细分。

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**实现**

网站上访客有资格获得特征的操作。You can use the [Visitor Profile Viewer](../features/visitor-profile-viewer.md) tool to obtain information on trait realization by a specific user.

## S-T {#s-t}

**区段**

区段(或受众)是共享常用属性的一组用户。

See [Segments: Purpose, Composition, and Rules](../features/segments/segments-purpose.md).

<br> 

**细分地址受众**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents the number of users who have belonged to the segment during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via traits acquired in the [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**区段总人口**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of all the devices that were a member of your segment during the report look-back period.

<br> 

**区段匹配率**

区段可寻址受众：表示为%的受众总数。See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**信号**

Signals are the smallest data units in [!DNL Audience Manager] and are expressed as key-value pairs.

See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**特性**

特征是一个或多个信号的组合。See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**特征人口**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL(到实时)**

TTL定义合格访客保留在特征中的天数。TTL设置在特征而不是在区段上。如果访客在TTL间隔结束之前没有看到符合条件的特征，则会退出区段。Read more in [Segment and Trait Time-to-Live Explained](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] 唯一用户ID。See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

[!DNL Experience Cloud] ID服务(以前称为访客ID)提供了一个通用的永久ID，可用于识别所有解决方案中的访客 [!DNL Experience Cloud]。

See the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/reference/marketing-cloud-id-service.html) documentation.

## W-X-Y-Z {#w-z}

