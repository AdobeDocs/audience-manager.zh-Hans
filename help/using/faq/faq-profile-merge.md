---
description: 常见配置文件合并规则和设备图形问题的解答。
keywords: 组织 ID
seo-description: 常见配置文件合并规则和设备图形问题的解答。
seo-title: 配置文件合并规则和设备图常见问题解答
solution: Audience Manager
title: 配置文件合并规则和设备图常见问题解答
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: ddec078f406b5386b10247b42f1b8bde6b0253e4

---


# 配置文件合并规则和设备图常见问题解答{#profile-merge-rules-and-device-graph-faq}

常见配置文件合并规则和设备图形问题的解答。

<!-- profile-merge-faq.xml -->

## 设备图形基础知识 {#device-graph-basics}

**什么是设备图？**

设备图是一组ID映射，它定义了匿名设备组。 它基于从每个设备收集的信号中的公共元素将这些设备与个人或家庭相关联。 这些信号有助于识别个人或家庭级别的设备。

 

**什么是外部设备图？**

外部设备图表是指中的任何设备图 [!DNL Audience Manager] 表，该图表并非仅由您自己的跨设备数据源创建。 例如，当您创建配置文 [件合并规则](../features/profile-merge-rules/merge-rules-start.md) ，并选择设备图 [!UICONTROL Co-op Device Graph] 形选项或第三方设备图形选项时，您将使用外部设备图形。 请参阅 [设备选项](../features/profile-merge-rules/merge-rule-definitions.md#device-options)。

 

**在中使用外部设备图的一些常见用例是什么[!UICONTROL Profile Merge Rule]?**

在设备图中使用设备图的主要目的 [!UICONTROL Profile Merge Rule] 是评估和确定属于单个人或家庭的特定区段的多个设备。 该细分本身可能具有多种用途，例如，通过DSP提供的广告定位潜在客户的受众或通过现场个性化平台个性化客户的现场体验。 See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Audience manager是否为外部设备图形提供全局支持？**

不会。外部设备图形仅在美国和加拿大可用。

 

**更新外部设[!DNL Audience Manager]备图形数据的频率是多久？**

每周一次。

 

## 设备图形和配置文件合并规则 {#device-graph-profile-merge-rules}

**如何使[!DNL Audience Manager]用设备图表？**

在中， [!DNL Audience Manager]当您创建配置文件合并规则时，设备图 [形将显示为配置选项](../features/profile-merge-rules/merge-rules-start.md)。 通过您的 [!UICONTROL Profile Merge Rules]设备图形，这些设备图有助于 [!DNL Audience Manager]:

* 将多个设备配置文件合并在一起。 这会创建一个特征超集。
* 评估特征超集以获得区段资格（而不是单独评估每个设备配置文件）。
* 将合格设备添加到可用区段。

 

**我可以[!UICONTROL Profile Merge Rules]创建多少？**

当前，最多可创建4个 [!UICONTROL Profile Merge Rules]。 第四个配置文件合并规[!UICONTROL All Cross-Device Profiles]则()仅适用于购买该加载项 [!UICONTROL People-Based Destinations] 的客户。

 

**在中使用设备图[!DNL Audience Manager]形时，合并和读取多少个设备配置文件[!UICONTROL Profile Merge Rule]?**

当使用某个设备对区段进行资格鉴定时， [!UICONTROL Profile Merge Rule]Audience manager会合并和读取当前设备配置文件以及最多99个由所选设备图形选项链接的其他设备配置文件。

 

**在中使用设备图时，哪些设备符合段条件[!UICONTROL Profile Merge Rule]?**

设备合 [!DNL Audience Manager] 并和读取是符合区段条件的相同设备。

 

**在哪里[!DNL Audience Manager]可以发送已通过使用设备图形[!UICONTROL Profile Merge Rule]的区段？**

[!DNL Audience Manager] 可以以批处理文件或实时将区段发送到目标。

 

## 区段、设备图形和配置文件合并规则 {#segments-device-graphs-rules}

**当设[!DNL Audience Manager]备不再符合使用设备图形的区段的条件时，如何取消[!UICONTROL Profile Merge Rule]分段设备？**

当使用设备图来评估区段时，Audience manager将合并多达100 [!UICONTROL Profile Merge Rule] 台设备。 如果发出未分段信号，将从目的地的分段中移除当前设备和多达99个附加设备。 有关取消分段的详细信息，请参 [阅配置文件合并规则和设备取消分段进程](../features/profile-merge-rules/merge-rule-unsegment.md)。

 

**如果目标可以取消设备分段，使用设备图表的设备是否会[!UICONTROL Profile Merge Rules]从分段中删除设备？**

能。请参阅上述说明。

 

**如果我使用设备图形构建一个区段，而该区段同时使用实时数据和已载入数据，那么我的区段是否会随着已载入数据的更改而更新？[!UICONTROL Profile Merge Rule]**

能。

 

**区段大小估计是否包括基于使用设备图选项的连接符合[!UICONTROL Profile Merge Rule]区段条件的设备？**

不会。请参阅区段生成器中 [!UICONTROL Estimated Real-Time Population] 的特 [!UICONTROL Estimated Total Population] 征 [和区段填充数据的定义](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)。

 

**是否[!UICONTROL Addressable Audiences]包括基于使用设备图形选项的设备所提供的连接[!UICONTROL Profile Merge Rule]而符合区段条件的设备？**

能。

 

**如果区段使用[!UICONTROL Profile Merge Rule]的[!UICONTROL No Cross-Device Profile]是带有，且符合该区段设备条件的特征仅存储在跨设备配置文件中，那么该区段的总人口是否为0?**

能。在将“配置文件合并规则”设置为时，Audience manager不会在区段评估中计算跨设备配置文件上存储的特征 [!UICONTROL No Cross-Device Profile]。

 

## 特征频率、设备图形和配置文件合并规则 {#trait-freq-device-rules}

**如何使用[!DNL Audience Manager]设备图形计算特[!UICONTROL Profile Merge Rule]征频率？**

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
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">您有一个使 <span class="wintitle"> 用设备图形选项</span> 的配置文件合并规则。 </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">由单个特征（特征1）组成的单个段（段1），其中特征1的频率为8。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager可读取和合并设备A和设备B的设备配置文件。</span> 从中，我们看到： </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">设备A已三次符合特征1。 特征1的频率为3。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">设备B已5次符合特征1。 特征1的频率为5。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager总结了特征1的频率，并使用8(3 + 5 = 8)来确定区段资格。</span> 设备A和设备B符合区段1的要求，因为其频率为8。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## 报告、设备图形和配置文件合并规则 {#reports-device-graphs-rules}

**我是否可以看到使用设备图表的[!UICONTROL Profile Merge Rule]设备可以访问的数量？**

能。报告返回级别的 [!UICONTROL Profile Merge Rule] 数据。 报告数据每天更新。 数据基于您帐户中看到的设备，而非通过设备图表链接的设备。 请参 [阅配置文件合并规则的报告指标](../features/profile-merge-rules/profile-link-metrics.md)。

 

**我是否可以实时查看使用设备图&#x200B;*表的特定区段*[!UICONTROL Profile Merge Rules]的合格设备数？**

能。实时人口量度使用来自通过设备图形链接的所有设备的配置文件来捕获当前设备（实时查看的设备）的细分资格。

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
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">区段1基于以下特征和资格逻辑构建：区段1 =特征A、特征B和特征C。 </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3个设备配置文件：设备1（当前设备）、设备2（设备图）、设备3（设备图）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p>每个可用特征都与设备关联： </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">设备1:特征A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">设备2:特征B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">设备3:特征C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于以前的元素，区段1的总人口为1。 </p> <p>在这种情况下，配置文 <span class="wintitle"> 件合并规则会使用所有设备</span> ，以及其特征来决定细分资格。 这意味着设备1、2和3符合区段1的资格，但如上所述，实时区段群中只包括设备1。 这是因为： </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">设备1是当前与Audience Manager Data Collection Server <span class="wintitle"> (</span> DCS<span class="wintitle"></span>)实时交互的设备。 </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">设备2和3通过设备图形与设备1关联，但它们与设备1不同时与DCS交互。 </li> 
     </ul> </p> <p>因此，设备2和3不包括在实时细分人口指标中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**我是否可以使用设备图来查看符合特定区段条件[!UICONTROL Profile Merge Rule]的设备总数？**

能。总段填充度量包括基于设备图形的连接而符合区段条件的附加设备。

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
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">区段1基于以下特征和资格逻辑构建：区段1 =特征A、特征B和特征C。 </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3个设备配置文件：设备1（当前设备）、设备2（设备图）、设备3（设备图）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>协会</b> </p> </td> 
   <td colname="col2"> <p>每个可用特征都与设备关联： </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">设备1:特征A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">设备2:特征B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">设备3:特征C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于以前的要素，第1部分的总人口为三(3)。 </p> <p>在这种情况下，配置文 <span class="wintitle"> 件合并规则会使用所有设备</span> ，以及其特征来决定细分资格。 这意味着设备1、2和3符合第1部分的条件，并且这三者均计入总人口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**是否有资格使用报表、报[!UICONTROL Profile Merge Rule]表和报表中包含的设备图表作为区[!UICONTROL Interactive]段的[!UICONTROL Overlap]设备[!UICONTROL Audience Optimization]?**

不会。

>[!MORE_LIKE_THIS]
>
>* [配置文件链接](../features/profile-merge-rules/profile-link-use-case.md)

