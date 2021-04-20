---
description: 有关配置文件合并规则和设备图的常见问题解答。
keywords: 组织 ID
seo-description: 有关配置文件合并规则和设备图的常见问题解答。
seo-title: 配置文件合并规则和设备图常见问题解答
solution: Audience Manager
title: 配置文件合并规则和设备图常见问题解答
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge
exl-id: 03ad79b7-a111-437e-82c5-c7406bd33c39
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1552'
ht-degree: 86%

---

# 配置文件合并规则和设备图常见问题解答{#profile-merge-rules-and-device-graph-faq}

有关配置文件合并规则和设备图的常见问题解答。

<!-- profile-merge-faq.xml -->

## 设备图基础知识 {#device-graph-basics}

**什么是设备图？**

设备图是用于定义匿名设备组的一组 ID 映射。设备图可根据从每个设备收集到的信号中所包含的通用元素将这些设备与个人或家庭相关联。这些信号可帮助识别个人或家庭所用的设备。

 

**什么是外部设备图？**

外部设备图是指在 [!DNL Audience Manager] 中除使用您自己的跨设备数据源之外还使用其他数据源创建的设备图。例如，如果创建[配置文件合并规则](../features/profile-merge-rules/merge-rules-start.md)，并选择 [!UICONTROL Co-op Device Graph] 或第三方设备图选项，则表明您正在使用外部设备图。请参阅[设备选项](../features/profile-merge-rules/merge-rule-definitions.md#device-options)。

 

**在 [!UICONTROL Profile Merge Rule] 中使用外部设备图的常见用例有哪些？**

在 [!UICONTROL Profile Merge Rule] 中使用设备图的主要目的在于评估属于单个人员或家庭的多台设备并确定其是否符合特定区段的资格。区段本身也可能具有多种用途，例如，通过 DSP 提供的广告定位潜在受众，或通过网站个性化平台为客户提供个性化的网站访问体验。请参阅[外部设备图用例](../features/profile-merge-rules/external-graph-use-cases.md)。

 

**Audience Manager 是否在全球范围内提供外部设备图支持？**

不是。外部设备图仅在美国和加拿大可用。

 

**[!DNL Audience Manager] 多久更新一次外部设备图数据？**

每周一次。

 

## 设备图和配置文件合并规则 {#device-graph-profile-merge-rules}

**[!DNL Audience Manager] 如何使用设备图？**

在 [!DNL Audience Manager] 中，当您[创建配置文件合并规则](../features/profile-merge-rules/merge-rules-start.md)时，设备图显示为配置选项。通过 [!UICONTROL Profile Merge Rules]，这些设备图可帮助 [!DNL Audience Manager] 执行以下操作：

* 将多个设备配置文件合并到一起。这会创建一个特征超集。
* 评估特征超集是否符合区段资格条件（而不是单独评估每个设备配置文件）。
* 将符合条件的设备添加到可用区段。

 

**我可以创建多少个 [!UICONTROL Profile Merge Rules]？**

目前，最多可创建 4 个 [!UICONTROL Profile Merge Rules]。第四个配置文件合并规则 ([!UICONTROL All Cross-Device Profiles]) 仅适用于购买 [!UICONTROL People-Based Destinations] 加载项的客户。

 

**在 [!UICONTROL Profile Merge Rule] 中使用设备图时，[!DNL Audience Manager] 可以合并和读取多少个设备配置文件？**

当使用 [!UICONTROL Profile Merge Rule] 确定某个设备符合某个区段的资格条件时，Audience Manager 可合并和读取当前设备配置文件以及最多 99 个通过您选定的设备图选项关联的其他设备配置文件。

 

**在 [!UICONTROL Profile Merge Rule] 中使用设备图时，哪些设备符合区段资格条件？**

[!DNL Audience Manager] 合并和读取的设备便是符合区段资格条件的设备。

 

**对于已通过使用设备图的 [!UICONTROL Profile Merge Rule] 鉴定资格条件的区段，[!DNL Audience Manager] 可以将这些区段发送至何处？**

[!DNL Audience Manager] 能够以批量文件或实时方式将区段发送到目标。

 

## 区段、设备图和配置文件合并规则 {#segments-device-graphs-rules}

**当设备不再符合某个区段的资格条件时，[!DNL Audience Manager] 如何通过使用设备图的 [!UICONTROL Profile Merge Rule] 取消设备分段？**

在通过使用设备图的 [!UICONTROL Profile Merge Rule] 评估区段时，Audience Manager 最多可合并 100 个设备。如果发出了取消分段信号，则将从目标中的相应区段移除当前设备和最多其他 99 个设备。有关取消分段的更多信息，请参阅[配置文件合并规则和设备取消分段流程](../features/profile-merge-rules/merge-rule-unsegment.md)。

 

**如果目标可以取消设备分段，是否能通过使用设备图的 [!UICONTROL Profile Merge Rules] 从区段中移除设备？**

是。请参阅上面的说明。

 

**如果我通过使用设备图的 [!UICONTROL Profile Merge Rule] 构建一个区段，并且该区段同时使用实时数据和已载入数据，那么我的区段是否能随着已载入数据的更改而更新？**

是。

 

**区段预估大小是否包含根据由使用设备图选项的 [!UICONTROL Profile Merge Rule] 提供的连接而确定为符合区段资格条件的设备？**

否。有关 [!UICONTROL Estimated Real-Time Population] 和 [!UICONTROL Estimated Total Population] 的定义，请参阅[区段生成器中的特征和区段人口数据](https://docs.adobe.com/content/help/zh-Hans/audience-manager/user-guide/features/segments/segment-builder-data.html)。

 

**[!UICONTROL Addressable Audiences] 是否包含根据由使用设备图选项的 [!UICONTROL Profile Merge Rule] 提供的连接而确定为符合区段资格条件的设备？**

是。

 

**如果某个区段结合使用 [!UICONTROL Profile Merge Rule] 和 [!UICONTROL No Cross-Device Profile]，且用于鉴定设备是否符合该区段资格条件的特征仅存储在跨设备配置文件中，那么该区段总人口是否为 0？**

是。将配置文件合并规则设为 [!UICONTROL No Cross-Device Profile] 后，Audience Manager 在评估区段时不会计算存储在跨设备配置文件中的特征数量。

 

## 特征频度、设备图和配置文件合并规则 {#trait-freq-device-rules}

**[!DNL Audience Manager] 如何通过使用设备图的 [!UICONTROL Profile Merge Rule] 计算特征频度？**

特征频度是指在多个设备中符合某个特定特征的总次数。为便于您理解，请查看以下用例。

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">设备 A 和设备 B 通过设备图相连。 </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">您有一个使用设备图选项的<span class="wintitle">配置文件合并规则</span>。 </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">单个区段（区段 1）仅包含一个特征（特征 1），其中特征 1 的频度为 8。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Audience Manager</span> 读取并合并设备 A 和设备 B 的设备配置文件。从中，我们可以看到以下信息： </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">设备 A 已三次符合特征 1。特征 1 的频度为 3。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">设备 B 已五次符合特征 1。特征 1 的频度为 5。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Audience Manager</span> 汇总特征 1 的频度，并使用 8 (3 + 5 = 8) 来确定区段资格条件。设备 A 和设备 B 符合区段 1 的资格条件，因为其频度为 8。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## 报表、设备图和配置文件合并规则 {#reports-device-graphs-rules}

**能否查看可通过使用设备图的 [!UICONTROL Profile Merge Rule] 访问的设备数量？**

能。报表将返回 [!UICONTROL Profile Merge Rule] 级别的数据。报表数据每日进行更新。数据基于您在帐户中看到的设备数，而非通过设备图链接的设备数。请参阅[配置文件合并规则的报表量度](../features/profile-merge-rules/profile-link-metrics.md)。

 

**是否可以通过使用设备图的 [!UICONTROL Profile Merge Rules] *实时*查看符合某个特定区段资格条件的设备数量？**

是。实时人口量度可使用通过设备图链接的所有设备的配置文件来捕获当前设备（实时查看到的设备）满足的区段资格条件。

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
   <td colname="col2"> <p>假设： </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">区段 1 基于以下特征和资格条件逻辑：区段 1 = 特征 A、特征 B 和 特征 C。 </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">有 3 个设备配置文件：设备 1（当前设备）、设备 2（设备图）、设备 3（设备图）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p>每个可用特征都与一个设备关联： </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">设备 1：特征 A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">设备 2：特征 B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">设备 3：特征 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>根据以上元素，区段 1 的总人口为 1。 </p> <p>在这种情况下，<span class="wintitle">配置文件合并规则</span>将使用所有设备及其特征来确定区段资格条件。这意味着虽然设备 1、2、3 均符合区段 1 的资格条件，但如上所述，实时区段人口仅包含设备 1。原因如下： </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">设备 1 是当前与 Audience Manager <span class="wintitle">数据收集服务器</span> (<span class="wintitle">DCS</span>) 实时交互的设备。 </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">而设备 2 和 3 是通过设备图与设备 1 相关联的，它们并未随设备 1 一起同 DCS 交互。 </li> 
     </ul> </p> <p>因此，实时区段人口量度不包含设备 2 和 3。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**是否可以通过使用设备图的 [!UICONTROL Profile Merge Rule] 查看符合某个特定区段资格条件的设备总数？**

是。总区段人口量度包含根据设备图中的连接确定符合区段资格条件的其他设备。

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
   <td colname="col2"> <p>假设： </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">区段 1 基于以下特征和资格条件逻辑：区段 1 = 特征 A、特征 B 和 特征 C。 </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">有 3 个设备配置文件：设备 1（当前设备）、设备 2（设备图）、设备 3（设备图）。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>关联</b> </p> </td> 
   <td colname="col2"> <p>每个可用特征都与一个设备关联： </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">设备 1：特征 A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">设备 2：特征 B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">设备 3：特征 C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>根据以上元素，区段 1 的总人口为三 (3)。 </p> <p>在这种情况下，<span class="wintitle">配置文件合并规则</span>将使用所有设备及其特征来确定区段资格条件。这意味着设备 1、2、3 均符合区段 1 的资格条件，并且所有这三个设备都计入总人口。 </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**如果某个区段具有使用设备图的 [!UICONTROL Profile Merge Rule]，那么符合该区段资格条件的设备是否会包含在 [!UICONTROL Interactive]、[!UICONTROL Overlap] 及 [!UICONTROL Audience Optimization] 报表中？**

否。

**2020年3月16日之后，为什么我看到区段出口到Adobe Campaign的区段数量为零？**

在2019年末，我们发布了一系列用户档案合并规则增强功能，以提高使用跨设备ID生成的批处理文件的准确性。 从2020年3月16日（星期一）开始，您的Audience Manager实例将严格遵守这些增强功能。 通常，使用跨设备ID映射到目标的区段将停止在某些用户档案合并规则配置中生成导出。

要确保使用跨设备ID(如Adobe Campaign)在Audience Manager实例与目标之间实现正确集成，请确保满足以下要求：

1. 查看映射到您的用户档案声明ID目标的区段使用的Adobe Campaign合并规则。 用户档案合并规则必须使用[!UICONTROL Last Authenticated Profile]选项，因此所有经过身份验证的用户档案都可以包含在导出中。 如果您的用户档案合并规则使用其他选项，请将其切换到[!UICONTROL Last Authenticated Profile]。
2. 在“Adobe Campaign合并规则”设置中选择用户档案声明ID数据源。

>[!NOTE]
>
> 我们已将用户档案合并规则限制提高1，以便您可以为映射到Adobe Campaign声明ID目标的区段创建专用的用户档案合并规则，而不更改其他用例的用户档案合并规则。

>[!MORELIKETHIS]
>
>* [配置文件链接](../features/profile-merge-rules/profile-link-use-case.md)

