---
description: 在Audience Manager中，特征资格或特征实现会受到不同的对待，具体视特征类型而定。 有关特质资格的详细信息，请参阅下表。
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: 在Audience Manager中，特征资格或特征实现会受到不同的对待，具体视特征类型而定。 有关特质资格的详细信息，请参阅下表。
seo-title: 特征鉴定参考
solution: Audience Manager
title: 特征鉴定参考
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 2f8662aba70254e550bc15417463c3c06492a9d5

---


# 特征鉴定参考 {#trait-qualification-reference}

在Audience Manager中，特征资格或特征实现会受到不同的对待，具体视特征类型而定。 有关特质资格的详细信息，请参阅下表。

## 按特征类型确定特征 {#trait-type}

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
   <td colname="col2"> <p>特征资格实时发生，因为用户在其浏览器中有资格获得特征。 在UI中创建基于规则的特征大约4小时后，您的用 <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> 户将开始确定该特征</a> 。 </p> <p>基于规则的特征允许您使用最近 <a href="../../features/segments/recency-and-frequency.md"> 和频率控制</a> ，以控制广告频率上限和其他用例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已载入的特征 </p> </td> 
   <td colname="col2"> <p>特征资格在处理入站文件后发生，即将入站文件导入Audience Manager <a href="../../faq/faq-inbound-data-ingestion.md"></a> ，即在特征资格发生时。 在创建已载入的特征后，您应等待大约4小时，然后再上传入站文件以进行处理。  </p> <p> 对于已载入的特征，用户配置文件的最大资格数为1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法特征 </p> </td> 
   <td colname="col2"> <p>对于算法特征，用户配置文件的最大资格数为1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>文件夹特征 </p> </td> 
   <td colname="col2"> <p>文件夹特征总结了它包含的特征的特征资格。 </p> <p>读取 <a href="../../features/traits/about-folder-traits.md"> 文件夹特征：关于</a> ，了解更多信息。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>活动受众特征和数据源已同步特征 </p> </td> 
   <td colname="col2"> <p>活动 <span class="wintitle"> 的Audience</span> （受众）特征包含Audience Manager帐户中管理的所 <span class="wintitle"> 有设备</span> 。 </p> <p><span class="wintitle"> 数据源同步的特征</span> ，跟踪与数据源关联的所有用户。 </p> <p>阅读有关活动受 <a href="../../features/traits/client-activity-synced-audience-traits.md"> 众特征和数据源已同步特征的更多信息</a>。 </p> </td>
  </tr>
 </tbody>
</table>

## 独特特质实现与总特质群体 {#unique-trait-realizations}

![](assets/utr-ttp1.png)

在不 **[!UICONTROL Unique Trait Realizations]** 同的时间范围内，将特征添加到其配置文件的访客数。

表 **[!UICONTROL Total Trait Population]** 示在其个人资料中具有此特征的访客数。

用这种方式来考虑数字。 在上图中，从“特征详细 [信息](../../features/traits/trait-details-page.md) ”视图中，181表示昨天访问您的属性的活动设备的数量。 1, [!UICONTROL Total Trait Population] 595表示当前符合此特征条件的用户数。 该 [!UICONTROL Total Trait Population] 数字用于显示可用于细分／定位的用户总数。 通常，用户在120天内将保留特征的一部分。

因为我们运行了两个不同的计算作业来计算两个种群， [!UICONTROL Total Trait Population] 所以总是滞后于24 [!UICONTROL Unique Trait Realizations] 小时。 在上图中，您可以看到2月11 [!UICONTROL Unique Trait Realizations] 日的175 [!UICONTROL Total Trait Population] 和6。 175个配置文件将在次 [!UICONTROL Total Trait Population] 日添加到中。

为了进一步推动Point Home，如果您目前体验到10,000名访客的激增，他们会在明天的游客中出现 [!UICONTROL Unique Trait Realizations]，但只会在24小时后的游客中出现 [!UICONTROL Total Trait Population]。

## 特征资格限制 {#trait-qualification-limit}

我们对每个用户配置文件强制实施150,000个特征资格限制，无论该配置文件是经过身份验证的配置文件( [DPUUID](../../reference/ids-in-aam.md))还是设备ID( [UUID](../../reference/ids-in-aam.md))。 请注意，虽然DPUUID对于特定实例是唯一的， [!DNL Audience Manager]但UUID是跨平台共享 [!DNL Audience Manager] 的。 因 [!UICONTROL UUID]此，我们在保存特质资格时实行公平政策。 算法确保配置文件的每 [!UICONTROL UUID] 个实例都有相同的共享 [!DNL Audience Manager]。
