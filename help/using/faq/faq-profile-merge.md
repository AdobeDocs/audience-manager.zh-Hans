---
description: 常见配置文件合并规则和设备图表问题的答案。
keywords: 组织 ID
seo-description: 常见配置文件合并规则和设备图表问题的答案。
seo-title: 个人资料合并规则和设备图表常见问题解答
solution: Audience Manager
title: 个人资料合并规则和设备图表常见问题解答
uuid: ba7986f1-078f-4162-aef3-b5 c8740 cf4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

常见配置文件合并规则和设备图表问题的答案。

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**什么是设备图？**

设备图是定义匿名设备组的一组ID映射。它根据从每台设备收集的信号中的通用元素将这些设备关联到个人或家用设备。这些信号有助于识别个人或家庭级别的设备。

<br> 

**什么是外部设备图？**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you&#39;re working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**使用外部设备图中的外部设备图表有哪些常见用例[!UICONTROL Profile Merge Rule]？**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. 区段本身可能具有多个用途，例如，定位由DSP提供服务的潜在客户群体和广告，或通过在线个性化平台个性化客户的现场体验。See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**Audience Manager是否提供对外部设备图的全局支持？**

不会。外部设备图仅在美国和加拿大提供。

<br> 

**[!DNL Audience Manager]更新外部设备图表数据的频率是多少？**

一周一次。

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**[!DNL Audience Manager]如何使用设备图？**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* 将多个设备配置文件合并到一起。这会创建一组单一的特征。
* 评估特征集以进行细分资格评估(而非逐个评估每个设备配置文件)。
* 将合格设备添加到可用的细分。

<br> 

**我可以[!UICONTROL Profile Merge Rules]创建多少个？**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**在使用设备图表时，有多少设备配置文件可以[!DNL Audience Manager]合并和读取[!UICONTROL Profile Merge Rule]？**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**在使用设备图表时，哪些设备有资格获得区段[!UICONTROL Profile Merge Rule]？**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>For external device graphs, [!DNL Audience Manager] stores the mapping between devices at the platform level and selects 3 without evaluating their relationship to the devices seen in your instance of [!DNL Audience Manager].

<br> 

**哪些设备**可以使用包含设备图表的一个[!UICONTROL Profile Merge Rule]区段获得区段？**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. 此外，边缘服务器：

* 存储档案数据最多14天。
* 如果超过14天，则删除设备配置文件。注意：此操作只从边缘删除数据。其他系统将保留记录以延长时间间隔。See the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

See also, [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**哪里可以[!DNL Audience Manager]发送使用设备[!UICONTROL Profile Merge Rule]图表的区段？**

[!DNL Audience Manager] 可以在批处理文件中或实时将区段发送到目标。And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**如果设备不再符合使用设备图表的区段，[!DNL Audience Manager]如何对设备[!UICONTROL Profile Merge Rule]进行取消细分？**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. 如果已发放取消细分信号，则将从目标位置的区段中实时查看当前设备和三个其他设备。例如，在六台设备群集中，最多四台设备会对某个区段进行合并、评估和合格。同样，最多四台设备也会进行合并、评估和取消分段。

<br> 

**如果目标可以取消细分设备，是否将使用设备图表从[!UICONTROL Profile Merge Rules]区段中删除设备？**

能。请参阅上述说明。

<br> 

**如果我构建了使用设备[!UICONTROL Profile Merge Rule]图表的区段，并且该区段同时使用实时和已载入的数据，那么在载入的数据发生变化时，我的区段将会更新吗？**

不会。Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). 这假定设备配置文件在边缘服务器中仍处于活动状态，并且已将内置数据提供给这些系统。See also, the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**细分大小估计是否包括基于[!UICONTROL Profile Merge Rule]使用设备图表选项的连接提供的连接的设备？**

不会。See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**[!UICONTROL Addressable Audiences]是否包括符合使用设备图表选项的连接所提供[!UICONTROL Profile Merge Rule]的区段的设备？**

能。

<br> 

**如果某个区段使用[!UICONTROL Profile Merge Rule]的是某个区段，[!UICONTROL No Authenticated Profile]且该区段符合条件的设备符合经认证的配置文件，那么该区段的总人口将为0？**

不会。如今，Audience Manager将映射到已验证配置文件的设备视为符合区段资格的设备。

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**[!DNL Audience Manager]如何使用设备图表[!UICONTROL Profile Merge Rule]计算特征频率？**

特征频率由跨多个设备的特定特征的数量总和来定义。为帮助您理解这一点，请查看下面的使用案例。

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">设备A和设备B由设备图链接。 </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">由单个特征(特征1)组成的单个区段(区段1)，其中特征1为频率1。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 可阅读并合并设备A和设备B的设备配置文件。因此，我们会看到以下内容： </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Device A有三次资格。对于特征，它的频率为3。 </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">设备B有资格获得特征1次。它的特征频率为5。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> 汇总了特征1，使用8(+5=8)确定细分资格。Device A和Device B有资格获得区段1，因为其频率为8。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**我能否查看使用设备图表的设备[!UICONTROL Profile Merge Rule]所能达到的设备数量？**

能。Reports return data at the [!UICONTROL Profile Merge Rule] level. 报告数据每天更新。数据基于帐户中所看到的设备，而非设备图所链接的设备。See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**我是否可以使用设备图表实时查看特定*细分设备*的符合[!UICONTROL Profile Merge Rules]条件的设备？**

能。实时人群指标使用设备图表链接的所有设备上的档案，实时捕获当前设备(实时查看的设备)的细分资格。

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
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">根据这些特征和资质逻辑构建的细分1：区段1=特征A、特征B和特征C。 </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">设备配置文件：设备1(当前设备)、设备2(设备图)、设备3(设备图)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>操作</b> </p> </td> 
   <td colname="col2"> <p>每个可用的特征与设备关联： </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">设备1：特征A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">设备2：特征B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">设备3：特征C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于之前的元素，区段的总人口是1。 </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. 这意味着设备1、和有资格获得区段1，但如上所述，只有设备包含在实时细分人群中。这是因为： </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">设备和设备通过设备图与设备相关联，但它们与DCS同时与DCS交互。 </li> 
     </ul> </p> <p>因此，设备和3不包含在实时细分人口指标中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**我可以看到使用设备图表的特定区段的[!UICONTROL Profile Merge Rule]设备总数吗？**

能。总细分人口指标包括根据设备图表的连接对区段具有资格的其他设备。

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
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">根据这些特征和资质逻辑构建的细分1：区段1=特征A、特征B和特征C。 </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">设备配置文件：设备1(当前设备)、设备2(设备图)、设备3(设备图)。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associations</b> </p> </td> 
   <td colname="col2"> <p>每个可用的特征与设备关联： </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">设备1：特征A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">设备2：特征B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">设备3：特征C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>对于前面的元素，区段的总人口是三(3)个。 </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. 这意味着设备1、和有资格获得区段1，并且全部都包含在总人口中。 </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**是否有符合区段的设备使用[!UICONTROL Profile Merge Rule][!UICONTROL Interactive]包含在报告、[!UICONTROL Overlap]报告和[!UICONTROL Audience Optimization]报告中的设备图表？**

否

>[!MORE_ LIKE_ This]
>
>* [配置文件链接](../features/profile-merge-rules/merge-rules-overview.md)

