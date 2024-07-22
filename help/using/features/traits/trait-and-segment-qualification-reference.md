---
description: 特征鉴定或特征实现在Audience Manager中的处理方式有所不同，具体取决于特征类型。 有关特征资格的详细信息，请参阅下表。
keywords: 特征资格、特征实现、唯一特征实现、UTR、总特征人口、TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: 特征鉴定参考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# 特征和区段资格参考 {#trait-qualification-reference}

特征鉴定或特征实现在Audience Manager中的处理方式有所不同，具体取决于特征类型。 有关特征类型资格的详细信息，请参阅[按特征类型列出的特征资格](#trait-type)。

此外，有关区段鉴别的详细信息，请参阅[实时区段填充和总区段填充](#real-time-segment)。



## 按特征类型列出的特征资格 {#trait-type}

| 特征类型 | 资格标准 |
|---|---|
| 基于规则的特征 | 特征资格鉴定是实时进行的，因为用户在其浏览器中符合某个特征的资格。 在您[在UI中创建特征](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)后，您的用户大约需要4小时才能开始符合基于规则的特征的资格。 基于规则的特征允许您使用[回访间隔和频度](../segments/recency-and-frequency.md)控件进行广告频度上限和其他用例。 |
| 已载入的特征 | 特征鉴定会在处理集客文件后进行，即集客文件是[导入到Audience Manager](../../faq/faq-inbound-data-ingestion.md)中，此时将进行特征鉴定。 您应在创建已载入特征后等待约4小时，然后再上传入站文件以进行处理。 对于已载入的特征，用户配置文件的最大资格数为1。 |
| 算法特征 | 对于算法特征，用户配置文件的最大资格数为1。 |
| 文件夹特征 | 文件夹特征可总结其包含的特征的特质资格。 有关详细信息，请阅读[文件夹特征：关于](about-folder-traits.md)。 |
| 活动受众特征和数据Source同步特征 | [!UICONTROL Active Audience]特征包含Audience Manager帐户中管理的所有设备。 [!UICONTROL Data Source Synced Traits]跟踪与数据源关联的所有用户。 了解有关[活动受众特征和Source同步特征的数据](client-activity-synced-audience-traits.md)的更多信息。 |

## 独特特征实现和特征人口总数 {#unique-trait-realizations}

![唯一特征实现](assets/trait-graph.png)

根据您希望图形显示的结果类型（按[!UICONTROL Device ID]或[!UICONTROL Cross-Device ID]筛选），量度具有不同的含义：

按[!UICONTROL Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations]是您的匿名设备访客在不同时间范围内将特征添加到其个人资料的数量。
* [!UICONTROL Total Trait Population]是您的匿名设备访客在其个人资料中拥有此特征的人数。

按[!UICONTROL Cross-Device ID]筛选结果时：

* [!UICONTROL Unique Trait Realizations]是经过身份验证的访客在不同的时间范围内将特征添加到其配置文件中的数量。
* [!UICONTROL Total Trait Population]是您的已验证访客在其个人资料中拥有此特征的数量。

以这种方式考虑数字。 在上图中，从[特征详细信息](../../features/traits/trait-details-page.md)视图，90,173表示昨天访问您资产的活动设备数。 55,757的[!UICONTROL Total Trait Population]表示当前符合此特征资格的用户数。 [!UICONTROL Total Trait Population]数字用于显示可用于分段/定位的用户总数。 通常，用户将在特征中保留120天。

由于我们运行两个不同的计算作业来计算这两个群体，因此[!UICONTROL Total Trait Population]始终比[!UICONTROL Unique Trait Realizations]晚24小时。 在上图中，您可以看到大约90,400 [!UICONTROL Unique Trait Realizations]和2月5日的大约90,300的[!UICONTROL Total Trait Population]。 90,400个配置文件将在第二天添加到[!UICONTROL Total Trait Population]。

为了进一步将焦点引回到主页，如果您现在体验10,000位访客的峰值，他们将在明天的[!UICONTROL Unique Trait Realizations]中显示，但仅在24小时后的[!UICONTROL Total Trait Population]中显示。

特征实现的任何更改都会反映在区段人口中。

## 实时区段人口和总区段人口 {#real-time-segment}

![唯一特征实现](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population]计算在所选时间间隔内符合所选区段资格并已到达属性的设备数。

[!UICONTROL Total Segment Population]计算选定时间范围内符合选定区段条件的设备数量。 [!UICONTROL 1 Day]报表表示最新的区段人口计数。

以这种方式考虑数字。 在上图中，从[区段详细信息](../../features/segments/segment-summary-view.md)视图中，9,993表示昨天访问您的资产并符合区段资格条件的活动设备数。 699,532的[!UICONTROL Total Segment Population]表示当前符合此区段条件的设备总数。 [!UICONTROL Total Segment Population]数字用于显示可用于分段/定位的设备总数。

由于我们运行两个不同的计算作业来计算这两个群体，因此[!UICONTROL Total Segment Population]始终比[!UICONTROL Real-time Segment Population]晚24小时。 在上图中，您可以看到2月2日有8,116 [!UICONTROL Real-time Segment Population]和742,000的[!UICONTROL Total Segment Population]。 8,116个配置文件将在第二天添加到[!UICONTROL Total Segment Population]。

为了进一步将焦点引回到主页，如果您现在体验10,000位访客的峰值，他们将在明天的[!UICONTROL Real-time Segment Population]中显示，但仅在24小时后的[!UICONTROL Total Segment Population]中显示。

## 特征资格限制 {#trait-qualification-limit}

我们为每个用户配置文件强制实施150,000个特征资格限制，无论它是经过身份验证的配置文件([DPUUID](../../reference/ids-in-aam.md))还是设备ID ([UUID](../../reference/ids-in-aam.md))。 请注意，虽然DPUUID对于[!DNL Audience Manager]的特定实例是唯一的，但UUID在[!DNL Audience Manager]平台之间共享。 对于[!UICONTROL UUID]，我们在存储特征资格时强制实施公平原则。 算法可确保[!DNL Audience Manager]的每个实例均可以共享[!UICONTROL UUID]配置文件。
