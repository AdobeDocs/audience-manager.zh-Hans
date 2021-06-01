---
description: 特征鉴别或特征实现在Audience Manager中的处理方式不同，具体取决于特征类型。 有关特征资格的详细信息，请参阅下表。
keywords: 特征鉴别、特征实现、独特特征实现、UTR、总特征人口、TTP
seo-description: 特征鉴别或特征实现在Audience Manager中的处理方式不同，具体取决于特征类型。 有关特征资格的详细信息，请参阅下表。
seo-title: 特征鉴定参考
solution: Audience Manager
title: 特征鉴定参考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: 特征
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# 特征和区段资格参考 {#trait-qualification-reference}

特征鉴别或特征实现在Audience Manager中的处理方式不同，具体取决于特征类型。 请参阅[按特征类型划分的特征资格条件](#trait-type) ，以了解有关特征类型资格条件的详细信息。

此外，请参阅[实时区段人口和总区段人口](#real-time-segment) ，以了解有关区段资格的详细信息。



## 按特征类型划分的特征资格条件{#trait-type}

| 特征类型 | 资格标准 |
|---|---|
| 基于规则的特征 | 随着用户在浏览器中符合某个特征的资格条件，特征鉴别会实时进行。 在您在UI中创建特征](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)大约4小时后，您的用户将开始符合基于规则的特征条件。 [基于规则的特征允许您使用[回访间隔和频率](../segments/recency-and-frequency.md)控件来设置广告频度上限和其他用例。 |
| 已载入的特征 | 处理入站文件后会进行特征鉴别，即入站文件是[导入到Audience Manager](../../faq/faq-inbound-data-ingestion.md)中，此时正是进行特征鉴别时。 创建已载入的特征后，您应当等待大约4小时，然后再上传入站文件以进行处理。 对于已载入的特征，用户配置文件的资格数上限为1。 |
| 算法特征 | 对于算法特征，用户配置文件的资格数上限为1。 |
| 文件夹特征 | 文件夹特征汇总了包含的特征的特征资格条件。 阅读[文件夹特征：关于](about-folder-traits.md)以了解更多信息。 |
| 活动受众特征和数据源同步特征 | [!UICONTROL Active Audience]特征包含您的Audience Manager帐户中管理的所有设备。 [!UICONTROL Data Source Synced Traits] 跟踪与数据源关联的所有用户。阅读有关[活动受众特征和数据源同步特征](client-activity-synced-audience-traits.md)的更多信息。 |

## 独特特征实现和总特征人口{#unique-trait-realizations}

![特征实现](assets/trait-graph.png)

根据您希望图表显示的结果类型（按[!UICONTROL Device ID]或[!UICONTROL Cross-Device ID]过滤），这些量度具有不同的含义：

按[!UICONTROL Device ID]过滤结果时：

* [!UICONTROL Unique Trait Realizations] 是在不同时间范围内将特征添加到其配置文件的匿名设备访客数量。
* [!UICONTROL Total Trait Population] 是您的匿名设备访客在其配置文件中具有此特征的数量。

按[!UICONTROL Cross-Device ID]过滤结果时：

* [!UICONTROL Unique Trait Realizations] 是在不同时间范围内，经过身份验证的将特征添加到其配置文件的访客数量。
* [!UICONTROL Total Trait Population] 是已通过身份验证的访客在其配置文件中具有此特征的数量。

用这种方式来想想数字。 在上图中，从[特征详细信息](../../features/traits/trait-details-page.md)视图中，90,173表示昨天访问您属性的活动设备数。 55,757中的[!UICONTROL Total Trait Population]表示当前符合此特征条件的用户数量。 [!UICONTROL Total Trait Population]图用于显示可用于分段/定位的用户总数。 通常，用户将在120天内保持特征的一部分。

由于我们运行两个不同的计算作业来计算这两个群体，因此[!UICONTROL Total Trait Population]始终比[!UICONTROL Unique Trait Realizations]滞后24小时。 在上图中，您可以看到2月5日的大约90,400 [!UICONTROL Unique Trait Realizations]和[!UICONTROL Total Trait Population]，大约90,300。 次日，将90,400个用户档案添加到[!UICONTROL Total Trait Population]。

为了进一步引导客户关注焦点，如果您当前遇到10,000位访客的激增，他们将显示在明天的[!UICONTROL Unique Trait Realizations]中，但仅在24小时后显示在[!UICONTROL Total Trait Population]中。

特征实现的任何更改都反映在区段人口中。

## 实时区段人口和总区段人口{#real-time-segment}

![特征实现](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population]会计算在选定时间间隔内符合选定区段资格条件且已到达您属性的设备数量。

[!UICONTROL Total Segment Population]计算在选定时间范围内符合选定区段资格条件的设备数量。 [!UICONTROL 1 Day]报表表示最新的区段人口计数。

用这种方式来想想数字。 在上图中，从[区段详细信息](../../features/segments/segment-summary-view.md)视图中，9,993表示昨天访问了您的资产并符合区段资格条件的活动设备数量。 699,532的[!UICONTROL Total Segment Population]表示当前符合此区段资格条件的设备总数。 [!UICONTROL Total Segment Population]图用于显示可用于分段/定位的设备总数。

由于我们运行两个不同的计算作业来计算这两个群体，因此[!UICONTROL Total Segment Population]始终比[!UICONTROL Real-time Segment Population]滞后24小时。 在上图中，您可以看到2月2日的8,116 [!UICONTROL Real-time Segment Population]和[!UICONTROL Total Segment Population]为742,000。 次日，将8,116个用户档案添加到[!UICONTROL Total Segment Population]中。

为了进一步引导客户关注焦点，如果您当前遇到10,000位访客的激增，他们将显示在明天的[!UICONTROL Real-time Segment Population]中，但仅在24小时后显示在[!UICONTROL Total Segment Population]中。

## 特征资格限制{#trait-qualification-limit}

无论是经过身份验证的配置文件([DPUUID](../../reference/ids-in-aam.md))还是设备ID([UUID](../../reference/ids-in-aam.md))，我们都对每个用户配置文件强制限制为150,000个特征资格条件。 请注意，尽管DPUUID对于特定的[!DNL Audience Manager]实例是唯一的，但UUID会在[!DNL Audience Manager]平台之间共享。 对于[!UICONTROL UUID]s，我们在存储特征资格时实施公平性策略。 算法可确保[!UICONTROL UUID]配置文件的每个实例都有相同的共享。[!DNL Audience Manager]
