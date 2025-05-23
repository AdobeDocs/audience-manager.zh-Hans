---
description: “可操作的日志文件”允许您从广告服务器日志文件捕获媒体信号，以便在Audience Manager中创建特征。 将广告服务器的展示次数、点击次数和转化次数捕获为特征，而无需追加像素。
keywords: 可操作的日志， alf， ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: 可操作的日志文件
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 2%

---

# 可操作的日志文件 {#actionable-log-files}

[!UICONTROL Actionable Log Files]允许您从广告服务器日志文件中捕获媒体数据，并使用这些数据在Audience Manager中创建特征。 将广告服务器的展示次数、点击次数和转化次数捕获为特征，而无需附加[像素](../../integration/media-data-integration/impression-data-pixels.md)。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中说明了代码元素和选项。 请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files]简化了您从广告服务器捕获展示次数、点击次数和转化次数的方式。 使用此信息对用户进行分段，而不必手动将像素媒体发送到[!DNL Audience Manager]。

## 入门指南 {#getting-started}

若要开始使用[!UICONTROL Actionable Log Files]，您需要将日志数据导入[!DNL Audience Manager]。 以下链接将帮助您入门：

* 有关[!UICONTROL Google Campaign Manager]日志，请参阅[将Google Campaign Manager数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *和*，联系您的[!DNL Audience Manager]顾问。
* 有关[!UICONTROL Google Ad Manager] (以前为Google DFP)日志，请参阅[将Google Ad Manager数据文件导入Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *和*，联系您的[!DNL Audience Manager]顾问。
* 有关其他广告服务器日志，请参阅[数据和元数据文件](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *和*，请联系您的[!DNL Audience Manager]顾问。

如果您已将日志数据导入[!DNL Audience Manager]，请让您的[!DNL Audience Manager]顾问或[客户关怀](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html)为您启用[!UICONTROL Actionable Log Files]。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html) to get started.

-->

## 使用可操作的日志文件 {#working-with-actionable-log-files}

使用[!UICONTROL Actionable Log Files]时，在[!DNL Audience Manager]中捕获广告服务器日志中的信息的方式与从实时网站交互中捕获数据的方式相同。 [!DNL Audience Manager]连接到您的广告服务器日志存储，解析来自日志的信息，并将日志数据作为可操作信号发送到我们的[数据收集服务器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要设置基于规则的特征，以捕获可操作信号。 了解如何在[Audience Manager用户界面](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)中或使用我们的[批量管理工具](../../reference/bulk-management-tools/bulk-create.md)来设置基于规则的特征。 向下滚动到[可操作的信号](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)部分，以查看可在基于规则的特征中使用的所有键的列表。

>[!IMPORTANT]
>
>我们建议实施[!UICONTROL Actionable Log Files] *而不是* [像素调用](../../integration/media-data-integration/impression-data-pixels.md)。 我们建议不要同时使用这两个选项，因为这会导致特征的频率计数增加。

## 可操作信号 {#actionable-signals}

信号是[!DNL Audience Manager]中的[最小数据单元](../../reference/signal-trait-segment.md)。 [!UICONTROL Actionable Log Files]允许您从广告服务器日志中捕获展示事件、点击事件和转化事件中的广告商、业务部门、创意和促销活动值。

>[!IMPORTANT]
>
>以下ad服务器支持[!UICONTROL Actionable Log Files]：
> <br>
>
> * [Google促销活动经理](#dcm-logs-signals)
> * [Google广告管理器](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud、Flashtalking和Sizmek](#generic-logs-signals)

请记住，要将此信息用于受众创建和分段，您需要自己设置基于规则的特征。

### 来自Google Campaign Manager日志的可操作信号 {#dcm-logs-signals}

该表列出了来自[!DNL Google Campaign Manager]日志文件的可操作信号：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日志文件中的标头名称 </th> 
   <th colname="col2" class="entry"> 信号 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
   <th colname="col4" class="entry"> 示例值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>表示Google促销活动管理器中转化活动的数字ID。 此字段映射到Google Campaign Manager中的活动ID。 </p> <p> <p>提示：您可以从Google Campaign Manager捕获多个或特定的转化活动。 使用Google Campaign Manager中每个转化活动的<code> d_conversion = activity ID</code>创建特征。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>此字段映射到Google Campaign Manager中的转化ID。 指示从Google Campaign Manager进行用户转化之前的活动。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> 点击后转化为<code> 1</code>。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code>用于帖子展示转化。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code>表示不匹配的转化。 转化无法与先前的活动匹配。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">展示、点击或转化事件的UTC日期和时间。 表示自1970-01-01 00:00:00 UTC以来的微秒。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>广告商数据源的集成代码。 请注意，这与Audience Manager数据源无关。</p> <p>此字段映射到Google Campaign Manager中的广告商组ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>业务部门ID。 此字段映射到Google Campaign Manager中的广告商ID。 </p> </td> 
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
   <td colname="col3"> <p>Google Campaign Manager提供的创作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 销售额，以美元为单位，以–6的幂为单位。 乘以1.000.000即可得到美元金额。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件类型。 Audience Manager从Google Campaign Manager日志文件名中读取事件类型，并将其转换为可操作信号。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code>的展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> 点击次数<code> d_event = click</code>。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code>进行转换。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获Google Campaign Manager数据的数据源的ID。 请参阅<a href="../../features/manage-datasources.md#create-data-source">如何创建数据Source</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号在[!DNL Audience Manager]中捕获，就像实时`HTTP`调用一样。 下面的示例调用包含有关来自[!DNL Google Campaign Manager]的转化事件的信息。 调用不一定必须在示例调用中包含&#x200B;*所有*&#x200B;信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

对于平均大小为[!DNL Google Campaign Manager]、行数为200万的日志文件，根据可操作信号创建的任何特征将在我们处理日志后大约一小时内实现。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>将接受[!DNL Google Campaign Manager]日志中提供的事件时间戳并将其传递给[!UICONTROL Data Collection Servers]。
>
>* 如果[!DNL Google Campaign Manager]日志文件中的数据行没有时间戳，我们使用`HTTP`调用的时间作为事件时间戳。
>* 如果[!DNL Google Campaign Manager]日志文件中的数据行包含格式错误的时间戳，我们将忽略整行。

<br> 

### 来自[!DNL Google Ad Manager]日志的可操作信号 {#ad-manager-logs-signals}

该表列出了来自[!DNL Google Ad Manager]日志文件的可操作信号：


| 日志文件中的标头名称 | 信号 | 描述 |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | 投放的广告管理器行项目的数值ID |
| `OrderId` | `d_orderid` | 包含投放的行项目和创意的广告经理订单的数值ID。 |
| `CreativeId` | `d_creative` | 投放的广告经理创意的数值ID。 |
| `-` | `d_event` | 指示事件类型。 Audience Manager从Ad Manager日志文件名称中读取事件类型，并将其转换为可操作信号。 接受的值为： <br> <ul><li>d_event =展示次数的imp。</li><li>d_event =单击以查看点击次数。</li><li>d_event =用于转化和活动的conv。</li></ul> |
| `-` | `d_src` | 用于捕获Ad Manager数据的数据源的ID。 请参阅[如何创建数据Source](/help/using/features/manage-datasources.md)。 |

表中描述的信号像实时HTTP调用一样通过Audience Manager捕获。 以下示例调用包含有关来自Google广告管理器的转化事件的信息。 调用不一定必须在示例调用中包含所有信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>将接受[!DNL Google Ad Manager]日志中提供的事件时间戳并将其传递给[!UICONTROL Data Collection Servers]。
>
>
>* 如果[!DNL Google Ad Manager]日志文件中的数据行没有时间戳，我们使用`HTTP`调用的时间作为事件时间戳。
>* 如果[!DNL Google Ad Manager]日志文件中的数据行包含格式错误的时间戳，我们将忽略整行。

<br> 

### 来自Adobe Advertising Cloud、Flashtalking和Sizmek广告服务器日志的可操作信号 {#generic-logs-signals}

首先，您必须将广告服务器日志存储在Amazon S3存储桶中。 要完成此操作，请阅读[Audience Optimization报表的数据文件以及可操作的日志文件](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *和*，联系您的[!DNL Audience Manager]顾问。 该表列出了来自广告服务器日志文件的可操作信号：

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 日志文件中的标头名称 </th> 
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
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code>印象 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code>点击 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code>未归因或未知 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> 展示、点击或转化事件的UTC日期和时间。 使用<code>yyyy-MM-dd HH:mm:ss</code>格式。 </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>广告商数据源的集成代码。 请注意，此字段与<a href="../../features/datasources-list-and-settings.md">Audience Manager数据源无关。</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>业务部门ID。  </p> </td> 
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
   <td colname="col3"> <p>日志文件的创作ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 购买或其他转化金额。 数据类型：浮点数。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件类型。 Audience Manager从日志文件名中读取事件类型，并将其转换为可操作信号。 请参阅<a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">日志文件命名约定</a>。 </p> <p>接受的值包括： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code>的展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> 点击次数<code> d_event = click</code>。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code>进行转换。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获日志数据的数据源的ID。 请参阅<a href="../../features/manage-datasources.md#create-data-source">如何创建数据Source</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号在[!DNL Audience Manager]中捕获，就像实时`HTTP`调用一样。 调用不一定必须在示例调用中包含&#x200B;*所有*&#x200B;信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager用户界面中使用可操作信号 {#actionable-signals-in-ui}

您可以在[信号搜索](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md)界面中查看传入的可操作信号。

转到&#x200B;**受众数据** (1) > **信号** (2) > **搜索** (3)并选择&#x200B;**可操作的日志文件** (4)筛选器。

UI中的![可操作信号](/help/using/integration/assets/alf-in-signals.png)

要使用可操作的信号创建基于规则的特征，请选择&#x200B;**可操作的日志文件** (1)，选择要用作特征规则的可操作信号(2)，然后按&#x200B;**从选定信号创建特征** (3)。

![从信号创建特征](/help/using/integration/assets/alf-create-trait.png)


## 用例 {#use-cases}

实施[!UICONTROL Actionable Log Files]的一个好处是可以选择将[回访间隔和频率](../../features/segments/recency-and-frequency.md)控件应用于包含可操作信号的任何[基于规则的特征](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)。 例如，这可让您在媒体营销活动中频繁限制向某个用户展示特定创意内容的次数。 阅读[即时跨设备抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)以了解如何执行此操作。 其他用例包括：

### 重新定位用户

重新定位看到创意123但未单击或转换的用户，并向他们显示创意456。 执行以下操作：

1. 创建一个特征来捕获看到创意内容的用户。 假设您命名特征[!DNL Creative Trait 123]。 使用特征规则：

   `d_creative == 123 AND d_event == imp`

2. 创建一个特征以捕获单击或转换的用户。 假设您将此命名为[!DNL Click and Converter]。 使用特征规则：

   `d_event == click OR d_event=conv`

3. 创建一个区段以填充看到创意123但未单击或转换的用户。 将其命名为[!DNL Retarget Users]并使用区段规则：

   `Creative Trait 123 AND NOT Click and Converter`

4. 将区段[!DNL Retarget Users]映射到目标，并使用creative 456定位目标中的用户。

### 在Audience Optimization报表或Audience Lab中使用Google Campaign Manager Floodlight活动

[Floodlight标记](https://support.google.com/dcm/partner/answer/4293719?hl=en)使广告商能够跟踪用户转化。 通过[!UICONTROL Actionable Log Files]，您可以在[Audience Optimization报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)或[Audience Lab](../../features/audience-lab/audience-lab.md)中跟踪[!DNL Google Campaign Manager]转化：

1. 创建特征并使用以下特征规则从广告服务器日志中捕获转化：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager[!UICONTROL UI]中创建特征时，选择[!UICONTROL Conversion]作为[!UICONTROL Event Type]。

2. 创建特征后，将开始在[!UICONTROL Audience Optimization Reports]和[!UICONTROL Audience Lab]中报告转化。

>[!MORELIKETHIS]
>
>* [将Google Campaign Manager数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization 报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
