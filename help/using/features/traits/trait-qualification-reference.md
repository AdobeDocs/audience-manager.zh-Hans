---
description: Audience Manager中的特征资格或特征实现因特征类型而异。有关特征资格资格的详细信息，请参见下表。
keywords: 特征资格资格；特征实现；独特特征真实性；UTR；特征总数；TTP
seo-description: Audience Manager中的特征资格或特征实现因特征类型而异。有关特征资格资格的详细信息，请参见下表。
seo-title: 特征鉴定参考
solution: Audience Manager
title: 特征鉴定参考
uuid: 07e0a639-2fb2-45d8-bug7-10fb46 b08 ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# 特征鉴定参考 {#trait-qualification-reference}

Audience Manager中的特征资格或特征实现因特征类型而异。有关特征资格资格的详细信息，请参见下表。

## Trait Qualification by Trait Type {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特征类型 </th> 
   <th colname="col2" class="entry"> 资格标准 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>基于规则的特征 </p> </td> 
   <td colname="col2"> <p>特征资格资格实时发生，因为用户可以在浏览器中获得特征。Your users will start qualifying for a rule-based trait approximately 4 hours after you <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> create the trait</a> in the UI. </p> <p>Rule-based traits allow you to use <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> controls for ad frequency capping and other use cases. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>载入的特征 </p> </td> 
   <td colname="col2"> <p>Trait qualification happens after an inbound file is processed, i.e. the inbound file is <a href="../../faq/faq-inbound-data-ingestion.md"> imported into Audience Manager</a> and that is when the trait qualification happens. </p> <p> 对于载入的特征，用户个人资料的最大合格数量为1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法特征 </p> </td> 
   <td colname="col2"> <p>对于算法特征，用户个人资料的最大合格数量为1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件夹特征 </p> </td> 
   <td colname="col2"> <p>文件夹特征总结了其包含特征的特征资格。 </p> <p>Read <a href="../../features/traits/about-folder-traits.md"> Folder Traits: About</a> for more information. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>活动受众特征和数据源同步特征 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 活动受众</span> 特征包含 <span class="wintitle"> Audience Manager</span> 帐户中管理的所有设备。 </p> <p><span class="wintitle"> 数据源同步特征</span> 跟踪与数据源关联的所有用户。 </p> <p>Read more about <a href="../../features/traits/client-activity-synced-audience-traits.md"> Active Audience Traits and Data Source Synced Traits</a>. </p> </td>
  </tr>
 </tbody>
</table>

## Unique Trait Realizations and Total Trait Population {#unique-trait-realizations}

![](assets/utr-ttp1.png)

**[!UICONTROL Unique Trait Realizations]** 在不同时间范围内，将特征添加到访客档案的访客数量。

**[!UICONTROL Total Trait Population]** 这表示具有此特征的访客在其个人资料上的数量。

以这种方式思考数字。In the image above, from the [Trait Details](../../features/traits/trait-details-page.md) view, 181 represents the number of active devices, that visited your properties yesterday. [!UICONTROL Total Trait Population] 1,595表示当前符合此特征的用户数。The [!UICONTROL Total Trait Population] figure is meant to show the total amount of users who could be used for segmentation/targeting. 通常情况下，用户将一直属于特征的一部分，为期120天。

Because we run two different computational jobs to calculate the two populations, the [!UICONTROL Total Trait Population] always lags behind the [!UICONTROL Unique Trait Realizations] by 24 hours. In the graph above, you can see 175 [!UICONTROL Unique Trait Realizations] and a [!UICONTROL Total Trait Population] of 6 for February 11. The 175 profiles are added to the [!UICONTROL Total Trait Population] on the following day.

To further drive the point home, if you experienced a spike of 10,000 visitors right now, they would show up in tomorrow's [!UICONTROL Unique Trait Realizations], but would only show up 24 hours later in the [!UICONTROL Total Trait Population].

## Trait Qualification Limit {#trait-qualification-limit}

We enforce a limit of 150,000 trait qualifications for each user profile, whether it is an authenticated profile ( [DPUUID](../../reference/ids-in-aam.md)) or a device ID ( [UUID](../../reference/ids-in-aam.md)). Note that while the DPUUIDs are unique to a specific instance of [!DNL Audience Manager], UUIDs are shared across the [!DNL Audience Manager] platform. For [!UICONTROL UUID]s, we impose a fairness policy when storing trait qualifications. An algorithm ensures that an equal share of the [!UICONTROL UUID] profile is made available for every instance of [!DNL Audience Manager].
