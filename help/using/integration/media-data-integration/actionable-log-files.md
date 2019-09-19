---
description: 可操作的日志文件允许您从Google DCM日志文件中捕获媒体数据，并使用这些数据在Audience manager中创建特征。 从广告服务器捕捉展示次数、点击次数和转化次数作为特质，而不必使用像素调用。
keywords: 可操作日志
seo-description: 可操作的日志文件允许您从Google DCM日志文件中捕获媒体数据，并使用这些数据在Audience manager中创建特征。 从广告服务器捕捉展示次数、点击次数和转化次数作为特质，而不必使用像素调用。
seo-title: 可操作的日志文件
solution: Audience Manager
title: 可操作的日志文件
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: dbc96973ed2214d171fe32b7e1314d40c22c2d79

---


# 可操作的日志文件 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 允许您从日志文件中捕获媒 [!DNL Google DCM] 体数据，并使用这些数据在Audience manager中创建特征。 从广告服务器捕捉展示次数、点击次数和转化次数作为特质，而不必使用像素调用。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）在本文档中指示代码元素和选项。 请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 简化从广告服务器捕获印象、点击和转化的方式。 使用此信息进行用户细分，无需手动为媒体添加像素即可将营销活动属性发送到 [!DNL Audience Manager]。

## 快速入门 {#getting-started}

要开始使用 [!UICONTROL Actionable Log Files]受众优化报告 [，您需要将DCM日志数据导入](../../reporting/audience-optimization-reports/audience-optimization-reports.md)[!DNL Audience Manager]。 请参 [阅将DCM数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) , *并与您的顾*[!DNL Audience Manager] 问联系。

如果您已经将日志数 [!UICONTROL DCM] 据导入 [!DNL Audience Manager]，请咨询顾问或客 [!DNL Audience Manager] 户关怀团队为您启 [用该功能](https://helpx.adobe.com/contact/enterprise-support.ec.html)[!UICONTROL Actionable Log Files] 。

>[!NOTE] {importance="high"}
>
>[!UICONTROL Actionable Log Files] 仅处理日 [!DNL Google DCM] 志文件。

## 使用可操作的日志文件 {#working-with-actionable-log-files}

使用 [!UICONTROL Actionable Log Files]时，从日志中 [!DNL DCM] 捕获信息的方式与从实 [!DNL Audience Manager] 时网站交互中捕获数据的方式相同。 [!DNL Audience Manager] 连接到您的存 [!DNL Google Cloud] 储，从日志中分析信息，并将日志数据作为可操作信号发送到我们的 [!DNL DCM] 数据收集服务器 [](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要设置基于规则的特征来捕获可操作的信号。 了解如何在 [Audience Manager UI中或使用批量管理工具设置基于规](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 则的特征 [](../../reference/bulk-management-tools/bulk-create.md)。 向下滚动到“可 [操作的信号](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) ”部分，以获取可在基于规则的特征中使用的所有键的列表。

对于平均大小为200万行 [!DNL DCM] 的日志文件，通过可操作信号创建的任何特征在我们处理日志后的大约一小时内即可实现。

>[!IMPORTANT] {importance="high"}
>
>我们建议实施 [!UICONTROL Actionable Log Files] 而 *不是像* 素 [调用](../../integration/media-data-integration/impression-data-pixels.md)。 我们不鼓励使用这两个选项，因为这会导致特征的频率计数增加。

## 可操作信号 {#actionable-signals}

信号是中最 [小的数据单元](../../reference/signal-trait-segment.md) 。 [!DNL Audience Manager][!UICONTROL Actionable Log Files] 允许您从日志中捕获广告商、业务单位、创意和营销活动值，单击事件和转化事件作为信 [!DNL DCM] 号。

请记住，要使用此信息来创建和细分受众，您需要自己设置基于规则的特征。 下表列出了日志文件中可操作 [!DNL DCM] 的信号：

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
   <td colname="col1"> <p> <code> d_event</code> </p> </td> 
   <td colname="col2"> <p>指示DCM中的事件类型。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> for impressions. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event =单击</code> ，单击。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> for conversions. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> imp，单击， conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col2"> <p>仅适用于转化事件。 </p> <p>表示DCM中转换活动的数字ID。 此字段映射到DCM中的活动ID。 </p> <p> <p>提示：您可以从DCM捕获多个或特定的转化活动。 使用 <code> d_conversion =活动ID</code> （针对DCM中的每个转换活动）创建特征。 </p> </p> </td> 
   <td colname="col3"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_conversionType</code> </p> </td> 
   <td colname="col2"> <p>仅适用于转化事件。 </p> <p>此字段映射到DCM中的转换ID。 指示用户从DCM转换之前的活动。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> ，用于点击后转换。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> ，用于印象后转化。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 对于不匹配的转化，为0。</code> 转换无法与以前的活动匹配。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p> <code> 0,1,2</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col2"> <p>广告商 ID.</p> <p>广告商数据源的集成代码。 请注意，这与Audience manager数据源无关。</p> <p>此字段从DCM映射到广告商组ID。 </p> </td> 
   <td colname="col3"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col2"> <p>业务单位ID。 此字段从DCM映射到广告商ID。 </p> </td> 
   <td colname="col3"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col2"> <p>DCM提供的系列活动ID。 </p> </td> 
   <td colname="col3"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col2"> <p>由DCM提供的创意ID。 </p> </td> 
   <td colname="col3"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col2"> <p>用于捕获DCM数据的数据源的ID。 请参 <a href="../../features/manage-datasources.md#create-data-source"> 阅如何创建数据源</a>。 </p> </td> 
   <td colname="col3"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号像实 [!DNL Audience Manager] 时呼叫一样被捕 `HTTP` 获。 以下示例调用包含有关来自的转换事件的信息 [!DNL DCM]。 调用不一定必须包括示 *例调用* 中的所有信号。

```
https://sample.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

>[!NOTE] {importance="high"}
>
>日志中提供的事件 [!DNL DCM] 时间戳将被接受并传递到 [!UICONTROL Data Collection Servers]。
>
>* 如果日志文件中的数据行没有时间戳， [!DNL DCM] 我们将调用的时间用作 `HTTP` 事件时间戳。
>* 如果日志文件中的数据 [!DNL DCM] 行包含格式错误的时间戳，我们将忽略整行。


## 用例 {#use-cases}

实施的一个好 [!UICONTROL Actionable Log Files] 处是，将最近和频率控 [制应用于包含可操作信号的](../../features/segments/recency-and-frequency.md) 任何基于规则的特征 [](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 。 例如，这允许您在媒体营销活动中设置用户在特定创意作品中显示次数的上限。 其他使用案例包括：

### 重新定位用户

重新定位查看了创意123但未单击或转换并向他们展示创意456的用户。 执行此操作:

1. 创建特征以捕获看到创意的用户。 假设你命名特质 [!DNL Creative Trait 123]。 使用特征规则：

   `d_creative == 123 AND d_event == imp`

1. 创建特征以捕获单击或转换的用户。 假设你给这个命名 [!DNL Click and Converter]。 使用特征规则：

   `d_event == click OR d_event=conv`

1. 创建一个区段以填充查看了Creative 123但未单击或转换的用户。 将其命 [!DNL Retarget Users] 名并使用区段规则：

   `Creative Trait 123 AND NOT Click and Converter`

1. 使用Creative 456将区 [!DNL Retarget Users] 段映射到目标，并将目标用户映射到目标。

### 在受众优化报告或受众实验室中使用DCM泛光灯活动

[Floodlight标签使广告商](https://support.google.com/dcm/partner/answer/4293719?hl=en) 能够跟踪用户转化率。 通过 [!UICONTROL Actionable Log Files]此项，您可以在“受众优化 [!DNL DCM] 报告”或“受众实 [验室”中跟踪](../../reporting/audience-optimization-reports/audience-optimization-reports.md)[转化率](../../features/audience-lab/audience-lab.md):

1. 创建一个特征并使用以下特征规则从广告服务器日志捕获转换：

   `d_event == conv AND d_conversion == 123`

   在Audience manager中创建特征时， [!UICONTROL UI]选择 [!UICONTROL Conversion] 作为 [!UICONTROL Event Type]。

2. 创建特征后，转换将开始在和中报告 [!UICONTROL Audience Optimization Reports] 对象 [!UICONTROL Audience Lab]。

>[!MORE_LIKE_THIS]
>
>* [将DCM数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [受众优化报告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

