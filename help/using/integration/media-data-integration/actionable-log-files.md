---
description: 可操作日志文件允许您从Google DCM日志文件捕获媒体数据，并使用数据在Audience Manager中创建特征。从广告服务器捕捉展示次数、点击次数和转化次数作为特质，而不必使用像素调用。
keywords: 可操作的日志
seo-description: 可操作日志文件允许您从Google DCM日志文件捕获媒体数据，并使用数据在Audience Manager中创建特征。从广告服务器捕捉展示次数、点击次数和转化次数作为特质，而不必使用像素调用。
seo-title: 可操作的日志文件
solution: Audience Manager
title: 可操作的日志文件
uuid: 4c47615f-ed47-41ba-8649-1d7 de4 f55 d62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 可操作的日志文件 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 允许您从 [!DNL Google DCM] 日志文件捕获媒体数据，并使用数据在Audience Manager中创建特征。从广告服务器捕捉展示次数、点击次数和转化次数作为特质，而不必使用像素调用。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中提供了代码元素和选项。请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 简化您从广告服务器捕获印象、点击和转化率的方式。Use this information for user segmentation without having to manually pixel media to send campaign attributes to [!DNL Audience Manager].

## 快速入门 {#getting-started}

To get started with [!UICONTROL Actionable Log Files], and to use our [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md), you need to import DCM log data into [!DNL Audience Manager]. See [Import DCM Data Files Into Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *and* contact your [!DNL Audience Manager] consultant.

If you are already importing [!UICONTROL DCM] log data into [!DNL Audience Manager], ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to enable [!UICONTROL Actionable Log Files] for you.

>[!NOTE] {重要性=“high”}
>
>[!UICONTROL Actionable Log Files] 只能使用 [!DNL Google DCM] 日志文件。

## Working with Actionable Log Files {#working-with-actionable-log-files}

With [!UICONTROL Actionable Log Files], the information from [!DNL DCM] logs is captured in [!DNL Audience Manager] the same way that you would capture data from real-time website interactions. [!DNL Audience Manager] 连接到您的 [!DNL Google Cloud] 存储，解析 [!DNL DCM] 日志中的信息，并将日志数据作为可操作信号发送到 [我们的数据收集服务器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要设置基于规则的特征来捕获可操作的信号。See how to set up rule-based traits either in the [Audience Manager UI](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) or using our [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Scroll down to the [Actionable Signals](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) section for a list of all the keys you can use in rule-based traits.

For an average-sized [!DNL DCM] log file of 2 million lines, any traits created from actionable signals are realized within approximately one hour after we process the logs.

>[!IMPORTANT] {重要性=“high”}
>
>We recommend implementing [!UICONTROL Actionable Log Files] *instead of*  [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md). 我们考虑使用两种选项，因为这会导致特征的频率计数增加。

## Actionable Signals {#actionable-signals}

Signals are the [smallest data units](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] 允许您在印象事件、点击事件、转化事件中捕获广告商、业务单位、创意和活动价值，以 [!DNL DCM] 来自日志的信号。

请记住，为了将此信息用于受众创建和细分，您需要自己设置基于规则的特征。The table lists the actionable signals from [!DNL DCM] log files:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 信号 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
   <th colname="col3" class="entry"> 示例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ event</code> </p> </td> 
   <td colname="col2"> <p>指示DCM中的事件类型。 </p> <p>可接受的值为： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_ event= imp</code> 以获取印象。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_ event= click</code> for click. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_ event= conv</code> 进行转换。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp，单击，conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversion</code> </p> </td> 
   <td colname="col2"> <p>仅可用于转换事件。 </p> <p>表示DCM中转换活动的数字ID。此字段映射到DCM中的活动ID。 </p> <p> <p>提示：您可以从DCM捕获多个或特定的转化活动。Create traits using <code> d_conversion = activity ID</code> for each conversion activity from DCM. </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ conversionType</code> </p> </td> 
   <td colname="col2"> <p>仅可用于转换事件。 </p> <p>此字段映射到DCM中的转换ID。指示用户从DCM转换之前的活动。 </p> <p>可接受的值为： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 用于点击后转换。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 用于印象后转化。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 以实现无与伦比的转化率。转换不能与之前的活动相匹配。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ adsrc</code> </p> </td> 
   <td colname="col2"> <p>广告商 ID. 此字段映射到DCM中的Advertiser Group ID。 </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ bu</code> </p> </td> 
   <td colname="col2"> <p>业务单位ID。此字段映射到DCM中的广告商ID。 </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ campaign</code> </p> </td> 
   <td colname="col2"> <p>DCM提供的系列活动ID。 </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ creative</code> </p> </td> 
   <td colname="col2"> <p>DCM提供的Creative ID。 </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ src</code> </p> </td> 
   <td colname="col2"> <p>用于捕获DCM数据的数据源的ID。See <a href="../../features/manage-datasources.md#create-data-source"> How to Create a Data Source</a>. </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

The signals described in the table are captured in [!DNL Audience Manager] like a real-time `HTTP` call. The example call below contains information on a conversion event from [!DNL DCM]. Calls do not necessarily have to include *all* the signals in the example call.

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {重要性=“high”}
>
>The event timestamp provided in the [!DNL DCM] logs will be honored and passed to the [!UICONTROL Data Collection Servers].
>
>* If a timestamp isn't available for a data row in the [!DNL DCM] log file, we use the time of the `HTTP` call as the event timestamp.
>* If the data row in the [!DNL DCM] log file contains a malformed timestamp, we ignore the entire row.


## 用例 {#use-cases}

One benefit of implementing [!UICONTROL Actionable Log Files] is the option to apply [recency and frequency](../../features/segments/recency-and-frequency.md) controls to any [rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) that contain actionable signals. 例如，这允许您在媒体营销活动中为用户显示显示特定创意的次数。其他使用案例包括：

### 重新定位用户

重新定位查看了Creative123但不会单击或转换的用户，并将其显示为456。执行此操作:

1. 创建特征以捕获查看创意的用户。Let's say you name the trait [!DNL Creative Trait 123]. 使用特征规则：

   `d_creative == 123 AND d_event == imp`

1. 创建特征以捕获单击或转换的用户。Let's say you name this one [!DNL Click and Converter]. 使用特征规则：

   `d_event == click OR d_event=conv`

1. 创建一个细分，以便与查看Creative123但没有单击或转换的用户进行填充。Name it [!DNL Retarget Users] and use the segment rule:

   `Creative Trait 123 AND NOT Click and Converter`

1. Map the segment [!DNL Retarget Users] to a destination and target users in the destination with creative 456.

### 在受众优化报告或受众实验室中使用DCM Floomight活动

[Floodlight标签](https://support.google.com/dcm/partner/answer/4293719?hl=en) 使广告商能够跟踪用户转化率。With [!UICONTROL Actionable Log Files], you can track the [!DNL DCM] conversions in the [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md) or in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. 创建特征并使用以下特征规则从广告服务器日志捕获转换：

   `d_event == conv AND d_conversion == 123`

   When creating the trait in the Audience Manager [!UICONTROL UI], select [!UICONTROL Conversion] as the [!UICONTROL Event Type].

2. Once you have created the trait, the conversion will begin to be reported against in the [!UICONTROL Audience Optimization Reports] and in [!UICONTROL Audience Lab].

>[!MORE_ LIKE_ This]
>
>* [将DCM数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [受众优化报告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

