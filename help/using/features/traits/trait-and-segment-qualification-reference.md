---
description: 特征限定或特征实现在Audience Manager中会有不同的处理方式，具体取决于特征类型。 有关特质资格的详细信息，请参阅下表。
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: 特征限定或特征实现在Audience Manager中会有不同的处理方式，具体取决于特征类型。 有关特质资格的详细信息，请参阅下表。
seo-title: 特征鉴定参考
solution: Audience Manager
title: 特征鉴定参考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# 特征和区段资格参考 {#trait-qualification-reference}

特征限定或特征实现在Audience Manager中会有不同的处理方式，具体取决于特征类型。 有关特 [征类型资格的详细信息](#trait-type) ，请参阅按特征类型确定特征。

此外，请参 [阅实时细分填充和总细分填充](#real-time-segment) ，了解细分资格的详细信息。



## 按特征类型确定特征 {#trait-type}

| 特征类型 | 资格标准 |
|---|---|
| 基于规则的特征 | 特征资格会实时发生，因为用户在其浏览器中有资格获得某个特征。 在UI中创建基于规则的特征大约4小时后，您的用 [户将开始该特征](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 的资格。 基于规则的特征允许您使用 [最近频率和频率控](../segments/recency-and-frequency.md) 制来进行广告频率限制和其他用例。 |
| 载入的特征 | 处理入站文件后即会发生特征限定，即将入站文 [件导入Audience Manager](../../faq/faq-inbound-data-ingestion.md) ，即特征限定发生时。 在创建已载入的特征后，您应等待大约4小时，才能上传入站文件进行处理。 对于已载入的特征，用户用户档案的最大资格数为1。 |
| 算法特征 | 对于算法特征，用户用户档案的最大资格数为1。 |
| 文件夹特征 | 文件夹特征会总结它包含的特征的特征资格。 读取 [文件夹特征： 关于](about-folder-traits.md) ，了解更多信息。 |
| 活动受众特征和数据源同步特征 | 特 [!UICONTROL Active Audience] 征包含Audience Manager帐户中管理的所有设备。 [!UICONTROL Data Source Synced Traits] 跟踪与数据源关联的所有用户。 阅读有关活动 [受众特征和数据源同步特征的更多信息](client-activity-synced-audience-traits.md)。 |

## 独特性认识与总特性群体 {#unique-trait-realizations}

![特征实现](assets/trait-graph.png)

根据您希望图表显示的结果类型（按或筛选）, [!UICONTROL Device ID] 度量具 [!UICONTROL Cross-Device ID]有不同的含义：

按以下方式筛选结果时 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 是已在不同时间范围内将特征添加到其访客的匿名设备用户档案数。
* [!UICONTROL Total Trait Population] 是匿名设备访客在其用户档案上具有此特征的数量。

按以下方式筛选结果时 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 是已验证的访客在不同时间范围内将特征添加到其用户档案的数量。
* [!UICONTROL Total Trait Population] 是已验证的访客在其用户档案上具有此特征的数量。

用这个方式来想数字。 在上图中，从“特 [征详细信息](../../features/traits/trait-details-page.md) ”视图中，90,173表示昨天访问您的属性的活动设备数。 55, [!UICONTROL Total Trait Population] 757表示当前符合此特征条件的用户数。 该 [!UICONTROL Total Trait Population] 数字用于显示可用于细分／定位的用户总数。 通常，用户在120天内将保留特征的一部分。

由于我们运行了两个不同的计算作业来计算这两个种群， [!UICONTROL Total Trait Population] 因此它们总是落后 [!UICONTROL Unique Trait Realizations] 于24小时。 在上图中，你可以看到2月5日 [!UICONTROL Unique Trait Realizations] 的90, [!UICONTROL Total Trait Population] 400和90,300。 第二天又增加了 [!UICONTROL Total Trait Population] 90,400用户档案。

为了进一步把车开回原点，如果你现在经历了1万访客的激增，它们会出现在明天的中，但 [!UICONTROL Unique Trait Realizations]是24小时后才会出现 [!UICONTROL Total Trait Population]。

特征实现的任何更改都反映在细分群体中。

## 实时细分人口与总细分人口 {#real-time-segment}

![特征实现](assets/segment-graph.png)

在 [!UICONTROL Real-time Segment Population] 所选时间间隔内，计算符合选定区段条件并已到达您的属性的设备数。

计 [!UICONTROL Total Segment Population] 算选定时间范围内符合选定区段条件的设备数。 报 [!UICONTROL 1 Day] 表表示最新的细分人口计数。

用这个方式来想数字。 在上图的“区段详细 [信息](../../features/segments/segment-summary-view.md) ”视图中，9,993表示昨天访问您的属性并符合区段条件的活动设备数。 699, [!UICONTROL Total Segment Population] 532台设备是目前符合这一部门条件的设备总数。 该 [!UICONTROL Total Segment Population] 数字用于显示可用于分段／定位的设备总数。

由于我们运行了两个不同的计算作业来计算这两个种群， [!UICONTROL Total Segment Population] 因此它们总是落后 [!UICONTROL Real-time Segment Population] 于24小时。 在上图中，您可以看到2月2日 [!UICONTROL Real-time Segment Population] 的8116 [!UICONTROL Total Segment Population] 和742000。 第二天又增加了8, [!UICONTROL Total Segment Population] 116用户档案。

为了进一步把车开回原点，如果你现在经历了1万访客的激增，它们会出现在明天的中，但 [!UICONTROL Real-time Segment Population]是24小时后才会出现 [!UICONTROL Total Segment Population]。

## 特征资格限制 {#trait-qualification-limit}

我们对每个用户用户档案强制实施150,000个特征资格限制，无论该用户档案是经过身份验证的([DPUUID](../../reference/ids-in-aam.md))还是设备ID([UUID](../../reference/ids-in-aam.md))。 请注意，虽然DPUUID对特定实例是唯一的， [!DNL Audience Manager]但UUID是跨平台共享 [!DNL Audience Manager] 的。 因 [!UICONTROL UUID]此，我们在保存特质资格时实行公平政策。 算法确保每个实例都可 [!UICONTROL UUID] 以使用用户档案的相等份额 [!DNL Audience Manager]。

