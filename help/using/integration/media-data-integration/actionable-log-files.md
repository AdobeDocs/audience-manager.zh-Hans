---
description: 可操作的日志文件允许您从广告服务器日志文件中捕获媒体信号，以在Audience Manager中创建特征。 从广告服务器捕获展示次数、点击次数和转化次数作为特征，而无需附加像素。
keywords: 可操作日志， alf， ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: 可操作的日志文件
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 3%

---

# 可操作的日志文件 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 允许您从广告服务器日志文件中捕获媒体数据，并使用这些数据在Audience Manager中创建特征。 从广告服务器捕获展示次数、点击次数和转化次数作为特征，而无需附加 [像素](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中指示了代码元素和选项。 请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 简化从广告服务器捕获展示次数、点击次数和转化的方式。 将此信息用于用户分段，而无需手动为媒体设置像素以将促销活动属性发送到 [!DNL Audience Manager].

## 入门指南 {#getting-started}

开始使用 [!UICONTROL Actionable Log Files]，您需要将日志数据导入 [!DNL Audience Manager]. 以下链接将帮助您入门：

* 对于 [!UICONTROL Google Campaign Manager] 日志，请参阅 [将Google Campaign Manager数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *和* 联系 [!DNL Audience Manager] 顾问。
* 对于 [!UICONTROL Google Ad Manager] (以前称为Google DFP)日志，请参阅 [将Google Ad Manager数据文件导入Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *和* 联系 [!DNL Audience Manager] 顾问。
* 有关其他广告服务器日志，请参阅 [数据和元数据文件](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *和* 联系 [!DNL Audience Manager] 顾问。

如果您已经将日志数据导入 [!DNL Audience Manager]，询问 [!DNL Audience Manager] 顾问或 [客户关怀](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html) 启用 [!UICONTROL Actionable Log Files] 为你。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 使用可操作的日志文件 {#working-with-actionable-log-files}

使用 [!UICONTROL Actionable Log Files]，广告服务器日志中的信息将在 [!DNL Audience Manager] 与从实时网站交互中捕获数据的方式相同。 [!DNL Audience Manager] 连接到您的广告服务器日志存储，从日志中解析信息，并将日志数据作为可操作信号发送给我们 [数据收集服务器](../../reference/system-components/components-data-collection.md#dcs-pcs).

您仍需要设置基于规则的特征以捕获可操作信号。 了解如何在 [Audience Manager用户界面](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 或使用 [批量管理工具](../../reference/bulk-management-tools/bulk-create.md). 向下滚动到 [可操作信号](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) 部分，以了解可在基于规则的特征中使用的所有键的列表。

>[!IMPORTANT]
>
>我们建议实施 [!UICONTROL Actionable Log Files] *而不是*  [像素调用](../../integration/media-data-integration/impression-data-pixels.md). 我们不鼓励使用这两个选项，因为这会导致特征的频率计数增加。

## 可操作信号 {#actionable-signals}

信号是 [最小数据单位](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] 允许您从广告服务器日志中捕获展示事件、点击事件和转化事件中的广告商、业务部门、创意和促销活动值，作为信号。

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] 以下广告服务器支持：
> <br>
>
> * [Google促销活动管理器](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud、Flashtaking和Sizmek](#generic-logs-signals)


请记住，要将此信息用于受众创建和分段，您需要自行设置基于规则的特征。

### Google Campaign Manager日志中的可操作信号 {#dcm-logs-signals}

表格列出了 [!DNL Google Campaign Manager] 日志文件：

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
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>表示Google促销活动管理器中转化活动的数字ID。 此字段映射到Google Campaign Manager中的活动ID。 </p> <p> <p>提示：您可以从Google Campaign Manager中捕获多个或特定的转化活动。 使用创建特征 <code> d_conversion = activity ID</code> ，用于Google促销活动管理器中的每个转化活动。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>此字段映射到Google Campaign Manager中的转化ID。 指示用户从Google Campaign Manager转换之前的活动。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 进行点击后转化。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 用于帖子展示转化。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 用于不匹配的转化。 无法将转化与之前的活动进行匹配。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">展示、点击或转化事件的UTC日期和时间。 自1970-01-01 00以来以微秒表示:00:00 UTC。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>广告商数据源的集成代码。 请注意，这与Audience Manager数据源无关。</p> <p>此字段映射到Google促销活动管理器中的广告商组ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>业务单位ID。 此字段映射到Google Campaign Manager中的广告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>由Google促销活动管理器提供的促销活动ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>由Google Campaign Manager提供的创作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 销售额以美元计，为–6。 乘以1.000.000，可查看为美元金额。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件类型。 Audience Manager会从Google Campaign Manager日志文件名中读取事件类型，并将其转换为可操作的信号。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以了解展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 的次数。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> （转化）。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获Google Campaign Manager数据的数据源ID。 请参阅 <a href="../../features/manage-datasources.md#create-data-source"> 如何创建数据源</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号在 [!DNL Audience Manager] 就像实时 `HTTP` 呼叫。 以下示例调用包含有关 [!DNL Google Campaign Manager]. 调用不一定必须包含 *全部* 示例调用中的信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

对于 [!DNL Google Campaign Manager] 日志文件包含200万行，根据可操作信号创建的任何特征都将在我们处理日志后大约一小时内实现。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>中提供的事件时间戳 [!DNL Google Campaign Manager] 日志将被接受并传递到 [!UICONTROL Data Collection Servers].
>
>* 如果时间戳不适用于 [!DNL Google Campaign Manager] 日志文件，我们使用 `HTTP` 调用作为事件时间戳。
>* 如果 [!DNL Google Campaign Manager] 日志文件包含格式错误的时间戳，我们将忽略整行。


<br> 

### 可操作信号来自 [!DNL Google Ad Manager] 日志 {#ad-manager-logs-signals}

表格列出了 [!DNL Google Ad Manager] 日志文件：


| 日志文件中的标题名称 | 信号 | 描述 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 已交付的广告管理器行项目的数字ID |
| `OrderId` | `d_orderid` | 包含已交付行项目和创作元素的广告管理器订单的数字ID。 |
| `CreativeId` | `d_creative` | 交付的广告管理器创作元素的数字ID。 |
| `-` | `d_event` | 指示事件类型。 Audience Manager从广告管理器日志文件名中读取事件类型，并将其转换为可操作的信号。 接受的值包括： <br> <ul><li>d_event = imp表示展示次数。</li><li>d_event =单击的次数。</li><li>d_event = conv用于转化和活动。</li></ul> |
| `-` | `d_src` | 用于捕获广告管理器数据的数据源ID。 请参阅 [如何创建数据源](/help/using/features/manage-datasources.md). |

表中描述的信号以Audience Manager形式捕获，如实时HTTP调用。 以下示例调用包含有关Google Ad Manager中转化事件的信息。 调用不一定必须在示例调用中包含所有信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>中提供的事件时间戳 [!DNL Google Ad Manager] 日志将被接受并传递到 [!UICONTROL Data Collection Servers].
>
>
>* 如果时间戳不适用于 [!DNL Google Ad Manager] 日志文件，我们使用 `HTTP` 调用作为事件时间戳。
>* 如果 [!DNL Google Ad Manager] 日志文件包含格式错误的时间戳，我们将忽略整行。


<br> 

### 来自Adobe Advertising Cloud、Flashtalking和Sizmek广告服务器日志的可操作信号 {#generic-logs-signals}

首先，您必须将您的广告服务器日志存入我们的Amazon S3存储段中。 要完成此操作，请阅读 [Audience Optimization报表的数据文件和可操作的日志文件](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *和* 联系 [!DNL Audience Manager] 顾问。 下表列出了广告服务器日志文件中的可操作信号：

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
   <td colname="col3"> <p>指示转化是否匹配。 选项包括： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> 展示次数 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> 单击 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> 未归因或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 展示、点击或转化事件的UTC日期和时间。 使用 <code>yyyy-MM-dd HH:mm:ss</code> 格式。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>广告商数据源的集成代码。 请注意，此字段与 <a href="../../features/datasources-list-and-settings.md">Audience Manager数据源。</a></p></td> 
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
   <td colname="col3"> <p>日志文件中的促销活动ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>日志文件中的创作ID。 </p> </td> 
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
   <td colname="col3"> <p>指示事件类型。 Audience Manager从日志文件名中读取事件类型，并将其转换为可操作信号。 请参阅 <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">日志文件命名约定</a>. </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 以了解展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 的次数。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> （转化）。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获日志数据的数据源ID。 请参阅 <a href="../../features/manage-datasources.md#create-data-source"> 如何创建数据源</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号在 [!DNL Audience Manager] 就像实时 `HTTP` 呼叫。 调用不一定必须包含 *全部* 示例调用中的信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager用户界面中使用可操作信号 {#actionable-signals-in-ui}

您可以在 [信号搜索](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) 界面。

转到 **受众数据** (1)> **信号** (2)> **搜索** （三）选择 **可操作的日志文件** (4)过滤器。

![UI中的可操作信号](/help/using/integration/assets/alf-in-signals.png)

要使用可操作信号创建基于规则的特征，请选择 **可操作的日志文件** (1)选择要用作特征规则的可操作信号(2)，然后按 **根据选定的信号创建特征** (3)。

![从信号创建特征](/help/using/integration/assets/alf-create-trait.png)


## 用例 {#use-cases}

实施的一个好处 [!UICONTROL Actionable Log Files] 是要应用的选项 [回访频度](../../features/segments/recency-and-frequency.md) 控件 [基于规则的特征](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 包含可操作信号。 例如，这允许您在媒体营销活动中设置用户被展示为特定创意内容的次数上限。 读取 [即时跨设备抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) 以了解如何执行此操作。 其他用例包括：

### 重新定位用户

重新定位查看了创意123但未单击或转换的用户，并向他们显示创意456。 执行此操作:

1. 创建特征以捕获查看了该创作元素的用户。 假设您为特征命名 [!DNL Creative Trait 123]. 使用特征规则：

   `d_creative == 123 AND d_event == imp`

2. 创建特征以捕获单击或转换的用户。 假设你给这个命名 [!DNL Click and Converter]. 使用特征规则：

   `d_event == click OR d_event=conv`

3. 创建一个区段，以使用查看了Creative 123但未单击或转换的用户进行填充。 将其命名为 [!DNL Retarget Users] 和使用区段规则：

   `Creative Trait 123 AND NOT Click and Converter`

4. 映射区段 [!DNL Retarget Users] 到目标并定位目标中具有创意456的用户。

### 在Google报表或Audience Lab中使用Audience Optimization Campaign Manager Floodlight活动

[Floodlight标记](https://support.google.com/dcm/partner/answer/4293719?hl=en) 使广告商能够跟踪用户转化。 使用 [!UICONTROL Actionable Log Files]，您可以跟踪 [!DNL Google Campaign Manager] 转化 [Audience Optimization报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md) 或 [Audience Lab](../../features/audience-lab/audience-lab.md):

1. 创建一个特征并使用以下特征规则从广告服务器日志中捕获转化：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager中创建特征时 [!UICONTROL UI]，选择 [!UICONTROL Conversion] 作为 [!UICONTROL Event Type].

2. 创建特征后，将开始在 [!UICONTROL Audience Optimization Reports] 和 [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [将Google Campaign Manager数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization 报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

