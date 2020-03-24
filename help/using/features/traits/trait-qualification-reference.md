---
description: 在Audience Manager中，特征资格或特征实现会受到不同的对待，具体视特征类型而定。 有关特质资格的详细信息，请参阅下表。
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: 在Audience Manager中，特征资格或特征实现会受到不同的对待，具体视特征类型而定。 有关特质资格的详细信息，请参阅下表。
seo-title: 特征鉴定参考
solution: Audience Manager
title: 特征鉴定参考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 40ac91af26ed4a95492dde872288dc2e9059cdf9

---


# 特征鉴定参考 {#trait-qualification-reference}

在Audience Manager中，特征资格或特征实现会受到不同的对待，具体视特征类型而定。 有关特质资格的详细信息，请参阅下表。

## 按特征类型确定特征 {#trait-type}

| 特征类型 | 资格标准 |
|---|---|
| 基于规则的特征 | 特征资格实时发生，因为用户在其浏览器中有资格获得特征。 在UI中创建基于规则的特征大约4小时后，您的用 [户将开始符合](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 该特征。 基于规则的特征允许您使用 [最近期和频率控制](../segments/recency-and-frequency.md) ，进行广告频率限制和其他使用案例。 |
| 已载入的特征 | 特征资格在处理入站文件后发生，即将入站文件导 [入Audience Manager](../../faq/faq-inbound-data-ingestion.md) ，即特征资格发生时。 在创建已载入的特征后，您应等待大约4小时，然后再上传入站文件以进行处理。 对于已载入的特征，用户配置文件的最大资格数为1。 |
| 算法特征 | 对于算法特征，用户配置文件的最大资格数为1。 |
| 文件夹特征 | 文件夹特征总结了它包含的特征的特征资格。 读取文 [件夹特征：关于](about-folder-traits.md) ，了解更多信息。 |
| 活动受众特征和数据源已同步特征 | 特 [!UICONTROL Active Audience] 征包含Audience Manager帐户中管理的所有设备。 [!UICONTROL Data Source Synced Traits] 跟踪与数据源关联的所有用户。 阅读有关活动受 [众特征和数据源已同步特征的更多信息](client-activity-synced-audience-traits.md)。 |

## 独特特质实现与总特质群体 {#unique-trait-realizations}

![特征实现](assets/trait-graph.png)

在不 [!UICONTROL Unique Trait Realizations] 同的时间范围内，将特征添加到其配置文件的访客数。

表 [!UICONTROL Total Trait Population] 示在其个人资料中具有此特征的访客数。

用这种方式来考虑数字。 在上图中，从“特征详细 [信息](../../features/traits/trait-details-page.md) ”视图中，90,173表示昨天访问您的属性的活动设备的数量。 55, [!UICONTROL Total Trait Population] 757表示当前符合此特征条件的用户数。 该 [!UICONTROL Total Trait Population] 数字用于显示可用于细分／定位的用户总数。 通常，用户在120天内将保留特征的一部分。

因为我们运行了两个不同的计算作业来计算两个种群， [!UICONTROL Total Trait Population] 所以总是滞后于24 [!UICONTROL Unique Trait Realizations] 小时。 在上图中，你可以看到2月5日的 [!UICONTROL Unique Trait Realizations] 90,400 [!UICONTROL Total Trait Population] 和90,300。 90,400个配置文件将在次 [!UICONTROL Total Trait Population] 日添加到中。

为了进一步推动Point Home，如果您目前体验到10,000名访客的激增，他们会在明天的游客中出现 [!UICONTROL Unique Trait Realizations]，但只会在24小时后的游客中出现 [!UICONTROL Total Trait Population]。

特征实现的任何更改都反映在区段总体中。

## 实时细分人口和总细分人口 {#real-time-segment}

![特征实现](assets/segment-graph.png)

在选 [!UICONTROL Real-time Segment Population] 定的时间间隔内，计算符合选定区段条件并已到达您的属性的设备数。

计 [!UICONTROL Total Segment Population] 数在选定时间范围内符合选定区段条件的设备数。 报 [!UICONTROL 1 Day] 告表示最新的区段人口计数。

用这种方式来考虑数字。 在上图中，从“区段详细信 [息](../../features/segments/segment-summary-view.md) ”视图中，9,993表示昨天访问您的属性并符合区段条件的活动设备的数量。 699, [!UICONTROL Total Segment Population] 532台设备是目前符合这一部门条件的设备总数。 该 [!UICONTROL Total Segment Population] 数字用于显示可用于分段／定位的设备总数。

因为我们运行了两个不同的计算作业来计算两个种群， [!UICONTROL Total Segment Population] 所以总是滞后于24 [!UICONTROL Real-time Segment Population] 小时。 在上图中，您可以看到2月2日的8116 [!UICONTROL Real-time Segment Population] 和 [!UICONTROL Total Segment Population] 74.2万的数字。 8,116个配置文件将在次 [!UICONTROL Total Segment Population] 日添加到中。

为了进一步推动Point Home，如果您目前体验到10,000名访客的激增，他们会在明天的游客中出现 [!UICONTROL Real-time Segment Population]，但只会在24小时后的游客中出现 [!UICONTROL Total Segment Population]。

## 特征资格限制 {#trait-qualification-limit}

我们对每个用户配置文件强制实施150,000个特征资格限制，无论该配置文件是经过身份验证的配置文件([DPUUID](../../reference/ids-in-aam.md))还是设备ID([UUID](../../reference/ids-in-aam.md))。 请注意，虽然DPUUID对于特定实例是唯一的， [!DNL Audience Manager]但UUID是跨平台共享 [!DNL Audience Manager] 的。 因 [!UICONTROL UUID]此，我们在保存特质资格时实行公平政策。 算法确保配置文件的每 [!UICONTROL UUID] 个实例都有相同的共享 [!DNL Audience Manager]。
