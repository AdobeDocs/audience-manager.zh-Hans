---
description: 常见用户档案合并规则和设备图形问题的解答。
keywords: Organization ID
seo-description: 常见用户档案合并规则和设备图形问题的解答。
seo-title: 用户档案合并规则和设备图常见问题解答
solution: Audience Manager
title: 用户档案合并规则和设备图常见问题解答
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: 56a9626b1fa77926bdc31ef72b058d2aa9b58f43
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 2%

---


# 用户档案合并规则和设备图常见问题解答{#profile-merge-rules-and-device-graph-faq}

常见用户档案合并规则和设备图形问题的解答。

<!-- profile-merge-faq.xml -->

## 设备图形基础知识 {#device-graph-basics}

**什么是设备图？**

设备图是一组定义匿名设备组的ID映射。 它根据从每个设备收集的信号中的公共元素将这些设备与个人或家庭相关联。 这些信号有助于在个人或家庭层面识别设备。

 

**什么是外部设备图？**

外部设备图表是指并非只 [!DNL Audience Manager] 从您自己的跨设备数据源创建的任何设备图表。 例如，当您创建 [用户档案合并规](../features/profile-merge-rules/merge-rules-start.md) 则并选择 [!UICONTROL Co-op Device Graph] 或第三方设备图形选项时，您正在使用外部设备图形。 请参阅 [设备选项](../features/profile-merge-rules/merge-rule-definitions.md#device-options)。

 

**在中使用外部设备图的一些常见用例是什么[!UICONTROL Profile Merge Rule]?**

在某个特定区段中使用设备图的 [!UICONTROL Profile Merge Rule] 主要目的是评估属于单个人或家庭的多个设备并确定其资格。 该细分本身可能具有多种用途，例如，通过DSP提供的广告定位受众潜在客户，或通过现场个性化平台个性化客户的现场体验。 See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**受众管理器是否为外部设备图形提供全局支持？**

不会。外部设备图形仅在美国和加拿大可用。

 

**更新外部设[!DNL Audience Manager]备图形数据的频率？**

每周一次。

 

## 设备图形和用户档案合并规则 {#device-graph-profile-merge-rules}

**如何使[!DNL Audience Manager]用设备图形？**

在中 [!DNL Audience Manager]，当您创建用户档案合并规则时，设备 [图形显示为配置选项](../features/profile-merge-rules/merge-rules-start.md)。 通过您的 [!UICONTROL Profile Merge Rules]设备图形，这些设备图表可帮 [!DNL Audience Manager]助：

* 将多个设备用户档案合并在一起。 这会创建一个特征超集。
* 评估特征超集以进行区段鉴定(而不是单独评估每个设备用户档案)。
* 将合格设备添加到可用区段。

 

**我可以[!UICONTROL Profile Merge Rules]创建多少？**

目前，最多可创建4个 [!UICONTROL Profile Merge Rules]。 第四个用户档案合并规[!UICONTROL All Cross-Device Profiles]则()仅适用于购买该加载项 [!UICONTROL People-Based Destinations] 的客户。

 

**使用设备图[!DNL Audience Manager]形时，合并和读取多少设备用户档案[!UICONTROL Profile Merge Rule]?**

当使用受众管理器对某个区段的设备进行 [!UICONTROL Profile Merge Rule]资格验证时，管理器会合并和读取当前设备用户档案以及最多99个由您选定的设备图形选项链接的其他设备用户档案。

 

**在中使用设备图形时，哪些设备符合段条件[!UICONTROL Profile Merge Rule]?**

设备合 [!DNL Audience Manager] 并和读取操作与符合区段条件的设备相同。

 

**哪里可[!DNL Audience Manager]以发送使用设备图形[!UICONTROL Profile Merge Rule]的符合条件的区段？**

[!DNL Audience Manager] 可以以批处理文件或实时将区段发送到目标。

 

## 区段、设备图形和用户档案合并规则 {#segments-device-graphs-rules}

**当设[!DNL Audience Manager]备不再符合使用设备图形的区段的条件时，如何[!UICONTROL Profile Merge Rule]取消分段？**

受众管理器在使用设备图表评估区段时， [!UICONTROL Profile Merge Rule] 可合并多达100台设备。 如果发出未分段信号，则当前设备和最多99个附加设备将从目标的分段中移除。 有关未分段的详细信息，请参阅 [用户档案合并规则和设备未分段流程](../features/profile-merge-rules/merge-rule-unsegment.md)。

 

**如果目标设备可以取消分段，使用设备图表的设备是否[!UICONTROL Profile Merge Rules]会从分段中删除设备？**

能。请参阅上面的说明。

 

**如果我使用设备图[!UICONTROL Profile Merge Rule]形构建一个区段，并且该区段同时使用实时数据和已载入数据，那么我的区段是否会随着已载入数据的变化而更新？**

能。

 

**区段大小估计是否包括基于使用设备图选项的连接符[!UICONTROL Profile Merge Rule]合区段条件的设备？**

不会。请参阅区段生成器中 [!UICONTROL Estimated Real-Time Population] 的特 [!UICONTROL Estimated Total Population] 征和 [区段填充数据以及数据的定义](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)。

 

**是[!UICONTROL Addressable Audiences]否包含基于使用设备图选项的设备提供的连接[!UICONTROL Profile Merge Rule]符合段条件的设备？**

能。

 

**如果区段使用[!UICONTROL Profile Merge Rule]带[!UICONTROL No Cross-Device Profile]号，且符合该区段设备条件的特征仅存储在跨设备用户档案中，那么该区段的总人口是否为0?**

能。受众管理器在将用户档案合并规则设置为时，不会在区段评估中计算跨设备用户档案上存储的特征 [!UICONTROL No Cross-Device Profile]。

 

## 特征频率、设备图形和用户档案合并规则 {#trait-freq-device-rules}

**如何[!DNL Audience Manager]使用设备图[!UICONTROL Profile Merge Rule]表计算特征频率？**

特征频率由跨多个设备的特定特征的资格数量之和定义。 为了帮助您理解这一点，请查看以下用例。

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">设备A和设备B通过设备图形链接。 </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">您有一个 <span class="wintitle"> 用户档案合并规则</span> ，它使用设备图形选项。 </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">由单个特征（特征1）组成的单个段（区段1），其中特征1的频率为8。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> 受众管理器</span> 读取和合并设备A和设备B的设备用户档案。 从中，我们看到： </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">设备A已对特征1进行了三次限定。 特征1的频率为3。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">设备B已5次符合特征1。 特征1的频率为5。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> 受众管理</span> 器总和特征1的频率，并使用8(3 + 5 = 8)来确定区段资格。 设备A和设备B有资格使用段1，因为它的频率为8。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## 报表、设备图形和用户档案合并规则 {#reports-device-graphs-rules}

**我是否可以看到使用设备图表的[!UICONTROL Profile Merge Rule]设备可以访问的数量？**

能。报表返回级别的 [!UICONTROL Profile Merge Rule] 数据。 报告数据每天更新。 数据基于您帐户中看到的设备，而非通过设备图表链接的设备。 请参 [阅用户档案合并规则的报告指标](../features/profile-merge-rules/profile-link-metrics.md)。

 

**能否使用设备图形实时查看符合特定&#x200B;*区段条件*[!UICONTROL Profile Merge Rules]的设备数量？**

能。实时人口量度使用来自通过设备图形链接的所有设备的用户档案来捕获当前设备（实时查看的设备）的细分资格。

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p>假设我们有： </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">第1部分基于以下特征和资格逻辑： 区段1 =特征A、特征B和特征C。 </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3个设备用户档案: 设备1（当前设备）、设备2（设备图）、设备3（设备图）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p>每个可用特征都与设备关联： </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">设备1: 特征A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">设备2: 特质B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">设备3: 特质C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>根据以前的要素，第1部分的总人口为1。 </p> <p>在这种情况下，用户档案合 <span class="wintitle"> 并规则使用</span> 所有设备及其特征来决定细分资格。 这意味着设备1、2和3符合区段1的资格，但如上所述，只有设备1包含在实时区段群中。 这是因为： </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">设备1是与受众管理器收集服 <span class="wintitle"> 务器</span> (<span class="wintitle"> DCS</span>)实时交互的当前设备。 </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">设备2和3通过设备图与设备1关联，但它们与DCS不同时与设备1交互。 </li> 
     </ul> </p> <p>因此，设备2和3不包括在实时细分人口指标中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**我能否通过使用设备图来查看符合特定区段[!UICONTROL Profile Merge Rule]条件的设备总数？**

能。总段填充度量包括基于设备图形的连接符合区段条件的附加设备。

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例元素 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p>假设我们有： </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">第1部分基于以下特征和资格逻辑： 区段1 =特征A、特征B和特征C。 </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3个设备用户档案: 设备1（当前设备）、设备2（设备图）、设备3（设备图）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>协会</b> </p> </td> 
   <td colname="col2"> <p>每个可用特征都与设备关联： </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">设备1: 特征A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">设备2: 特质B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">设备3: 特质C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于以前的要素，第1部分的总人口为三(3)。 </p> <p>在这种情况下，用户档案合 <span class="wintitle"> 并规则使用</span> 所有设备及其特征来决定细分资格。 这意味着设备1、2和3符合第1部分的资格，并且所有这三种设备都包括在总人口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**是否有资格在报表、报告和报[!UICONTROL Profile Merge Rule]告中包含使用设备图[!UICONTROL Interactive]表的[!UICONTROL Overlap]区段[!UICONTROL Audience Optimization]设备？**

不会。

**我的细分对Adobe Campaign的出口为何在2020年3月16日之后显示为0?**

在2019年末，我们发布了一系列用户档案合并规则增强功能，以提高使用跨设备ID生成的批处理文件的准确性。 从2020年3月16日星期一开始，您的受众管理器实例将严格遵循这些增强功能。 通常，使用跨设备ID映射到目标的区段将停止在某些用户档案合并规则配置中生成导出。

要确保使用跨设备ID(如受众)在Adobe Campaign管理器实例与目标之间正确集成，请确保满足以下要求：

1. 查看映射到您的用户档案声明ID目标的Adobe Campaign段使用的合并规则。 用户档案合并规则必须使用该选 [!UICONTROL Last Authenticated Profile] 项，因此所有经过身份验证的用户档案都可以包含在导出中。 如果您的用户档案合并规则使用其他选项，请将其切换为 [!UICONTROL Last Authenticated Profile]。
2. 在“Adobe Campaign合并规则”设置中选择用户档案声明ID数据源。

>[!NOTE]
>
> 我们已将用户档案合并规则限制为1，以便您为映射到Adobe Campaign声明ID目标的段创建专用的用户档案合并规则，而不更改其他用例的用户档案合并规则。

>[!MORELIKETHIS]
>
>* [配置文件链接](../features/profile-merge-rules/profile-link-use-case.md)

