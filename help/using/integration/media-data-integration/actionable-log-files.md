---
description: 可操作的日志文件允许您从广告服务器日志文件捕获媒体信号以在Audience manager中创建特征。 无需附加像素，即可从广告服务器捕获印象、点击和转换作为特征。
keywords: 可操作日志， alf, ALF
seo-description: 可操作的日志文件允许您从广告服务器日志文件捕获媒体信号以在Audience manager中创建特征。 捕获广告服务器的印象、点击和转换作为特征，无需附加像素。
seo-title: 可操作的日志文件
solution: Audience Manager
title: 可操作的日志文件
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
translation-type: tm+mt
source-git-commit: b258c7dbdcf359394fbdcad6511c4113f8d88d91

---


# 可操作的日志文件 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 允许您从广告服务器日志文件中捕获媒体数据，并使用这些数据在Audience manager中创建特征。 Capture impressions, clicks, and conversions from ad servers as traits without having to append [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）在本文档中指示代码元素和选项。 请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 简化从广告服务器捕获印象、点击和转化的方式。 使用此信息进行用户细分，无需手动为媒体添加像素即可将营销活动属性发送到 [!DNL Audience Manager]。

## 快速入门 {#getting-started}

要开始使用， [!UICONTROL Actionable Log Files]您需要将日志数据导入到 [!DNL Audience Manager]。 以下链接将帮助您快速入门：

* 有关 [!UICONTROL Google DCM] 日志，请参 [阅将DCM数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) , *并联* 系您的 [!DNL Audience Manager] 顾问。
* 有关其他广告服务器日志，请参 [阅数据和元数据文件](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) , *并联系您的*[!DNL Audience Manager] 顾问。

如果您已经将日志数据导入 [!DNL Audience Manager]，请咨询 [!DNL Audience Manager] 顾问或客 [户关怀](https://helpx.adobe.com/contact/enterprise-support.ec.html) ，为您 [!UICONTROL Actionable Log Files] 启用。

>[!IMPORTANT]
>
> 到2019年底，新广告服 [!UICONTROL Actionable Log Files] 务器的可用性将开始扩大。 Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

## 使用可操作的日志文件 {#working-with-actionable-log-files}

使用 [!UICONTROL Actionable Log Files]时，广告服务器日志中的信息捕获 [!DNL Audience Manager] 方式与从实时网站交互中捕获数据相同。 [!DNL Audience Manager] 连接到广告服务器日志存储，解析日志中的信息，并将日志数据作为可操作信号发送到我们的数据收集 [服务器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要设置基于规则的特征来捕获可操作的信号。 了解如何在 [Audience Manager UI中或使用批量管理工具设置基于规](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 则的特征 [](../../reference/bulk-management-tools/bulk-create.md)。 向下滚动到“可 [操作的信号](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) ”部分，以获取可在基于规则的特征中使用的所有键的列表。

>[!IMPORTANT]
>
>我们建议实施 [!UICONTROL Actionable Log Files] 而 *不是像* 素 [调用](../../integration/media-data-integration/impression-data-pixels.md)。 我们不鼓励使用这两个选项，因为这会导致特征的频率计数增加。

## 可操作信号 {#actionable-signals}

信号是中最 [小的数据单元](../../reference/signal-trait-segment.md) 。 [!DNL Audience Manager][!UICONTROL Actionable Log Files] 允许您从广告服务器日志中捕获广告商、业务单位、创意和营销活动值，单击事件和转化事件作为信号。

请记住，要使用此信息来创建和细分受众，您需要自己设置基于规则的特征。

### 来自Google DCM日志的可操作信号 {#dcm-logs-signals}

下表列出了日志文件中可操作 [!DNL DCM] 的信号：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日志文件中的标题名称 </th> 
   <th colname="col2" class="entry"> 信号 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
   <th colname="col4" class="entry"> 示例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>表示DCM中转换活动的数字ID。 此字段映射到DCM中的活动ID。 </p> <p> <p>提示：您可以从DCM捕获多个或特定的转化活动。 使用DCM中的每 <code> d_conversion = activity ID</code> 个转换活动创建特征。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>此字段映射到DCM中的转换ID。 指示用户从DCM转换之前的活动。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 的链接。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 以便进行印象后转化。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 用于不匹配的转换。 转换无法与以前的活动匹配。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">UTC印象、单击或转化事件的日期和时间。 自1970-01-01 00:00:00 UTC以微秒表示。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>广告商数据源的集成代码。 请注意，这与Audience manager数据源无关。</p> <p>此字段从DCM映射到广告商组ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>业务单位ID。 此字段从DCM映射到广告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>DCM提供的系列活动ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>由DCM提供的创意ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 销售额以美元计，为-6的幂。 乘以1.000.000以查看美元金额。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件类型。 Audience manager从DCM日志文件名中读取事件类型，并将其转换为可操作的信号。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按钮。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 转化。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获DCM数据的数据源的ID。 请参 <a href="../../features/manage-datasources.md#create-data-source"> 阅如何创建数据源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号像实 [!DNL Audience Manager] 时呼叫一样被捕 `HTTP` 获。 以下示例调用包含有关来自的转换事件的信息 [!DNL DCM]。 调用不一定必须包括示 *例调用* 中的所有信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

对于平均大小为200万行 [!DNL DCM] 的日志文件，通过可操作信号创建的任何特征在我们处理日志后的大约一小时内即可实现。

>[!NOTE] {importance="high"}
>
>日志中提供的事件 [!DNL DCM] 时间戳将被接受并传递到 [!UICONTROL Data Collection Servers]。
>
>* 如果日志文件中的数据行没有时间戳， [!DNL DCM] 我们将调用的时间用作 `HTTP` 事件时间戳。
>* 如果日志文件中的数据 [!DNL DCM] 行包含格式错误的时间戳，我们将忽略整行。


<br> 

### 通用广告服务器日志中可操作的信号 {#generic-logs-signals}

首先，您必须将广告服务器日志放入我们的Amazon S3存储段。 为此，请阅读“受众优 [化报告的数据文件”和“可操作的日志文件](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) ” *并与您的顾*[!DNL Audience Manager] 问联系。 下表列出了通用日志文件中可操作的信号：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日志文件中的标题名称 </th> 
   <th colname="col2" class="entry"> 信号 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
   <th colname="col4" class="entry"> 示例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>指示转换是否匹配。 选项包括： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> 展示次数 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> 单击 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 未归属或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> UTC印象、单击或转化事件的日期和时间。 使用 <code>yyyy-dd-mm hh:mm:ss format.</code> </p></td> 
   <td colname="col4"> <p> <code>2019-30-08 11:23:00</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>广告商数据源的集成代码。 请注意，此字段与 <a href="../../features/datasources-list-and-settings.md">Audience manager数据源无关。</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>业务单位ID。  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>日志文件中的系列活动ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>日志文件中的Creative ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 购买或其他转化金额。 数据类型：浮动。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件类型。 Audience manager从日志文件名中读取事件类型，并将其转换为可操作的信号。 请参阅 <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">日志文件命名约定</a>。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按钮。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 转化。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获日志数据的数据源的ID。 请参 <a href="../../features/manage-datasources.md#create-data-source"> 阅如何创建数据源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号像实 [!DNL Audience Manager] 时呼叫一样被捕 `HTTP` 获。 调用不一定必须包括示 *例调用* 中的所有信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager UI中处理可操作信号 {#actionable-signals-in-ui}

您可以使用“可操作日志文件”选 [择在“信号搜索](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) ”界面中查看传入 **的可操作信号** 。

![UI中可操作的信号](/help/using/integration/assets/alf-in-signals.png)

要使用可操作信号创建基于规则的特征，请选择可操作的日志文件 **，选择要用作特征规则的可操作信号，然后按** Create Trait from Selected Signals ****。

![从信号创建特征](/help/using/integration/assets/alf-create-trait.png)

## 用例 {#use-cases}

实施的一个好 [!UICONTROL Actionable Log Files] 处是，将最近和频率控 [制应用于包含可操作信号的](../../features/segments/recency-and-frequency.md) 任何基于规则的特征 [](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 。 例如，这允许您在媒体营销活动中设置用户在特定创意作品中显示次数的上限。 阅读 [“即时跨设备抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) ”，了解如何执行此操作。 其他使用案例包括：

### 重新定位用户

重新定位查看了创意123但未单击或转换并向他们展示创意456的用户。 执行此操作:

1. 创建特征以捕获看到创意的用户。 假设你命名特质 [!DNL Creative Trait 123]。 使用特征规则：

   `d_creative == 123 AND d_event == imp`

2. 创建特征以捕获单击或转换的用户。 假设你给这个命名 [!DNL Click and Converter]。 使用特征规则：

   `d_event == click OR d_event=conv`

3. 创建一个区段以填充查看了Creative 123但未单击或转换的用户。 将其命 [!DNL Retarget Users] 名并使用区段规则：

   `Creative Trait 123 AND NOT Click and Converter`

4. 使用Creative 456将区 [!DNL Retarget Users] 段映射到目标，并将目标用户映射到目标。

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

