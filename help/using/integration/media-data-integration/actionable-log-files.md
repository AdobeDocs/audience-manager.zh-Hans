---
description: 可操作的日志文件允许您从广告服务器日志文件捕获媒体信号以创建Audience Manager特征。 无需附加像素，即可捕获广告服务器的印象、点击和转换。
keywords: actionable logs, alf, ALF
seo-description: 可操作的日志文件允许您从广告服务器日志文件捕获媒体信号以创建Audience Manager特征。 无需附加像素，即可捕获广告服务器的印象、点击和转换。
seo-title: 可操作的日志文件
solution: Audience Manager
title: 可操作的日志文件
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
translation-type: tm+mt
source-git-commit: a4d86fb0324a03002123f8713eb9786b5b74c38e
workflow-type: tm+mt
source-wordcount: '1605'
ht-degree: 3%

---


# 可操作的日志文件 {#actionable-log-files}

[!UICONTROL Actionable Log Files] 允许您从广告服务器日志文件中捕获媒体数据，并使用该数据创建Audience Manager中的特征。将广告服务器中的展示次数、点击次数和转换次数捕获为特征，无需附加[像素](../../integration/media-data-integration/impression-data-pixels.md)。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）在此文档中指示代码元素和选项。 请参阅[代码和文本元素的样式约定](../../reference/code-style-elements.md)，以了解更多信息。

## 用途 {#purpose}

[!UICONTROL Actionable Log Files] 简化从广告服务器捕获印象、点击和转化的方式。无需手动将活动属性发送到[!DNL Audience Manager]像素媒体，即可将此信息用于用户细分。

## 快速入门 {#getting-started}

要开始使用[!UICONTROL Actionable Log Files]，您需要将日志数据导入[!DNL Audience Manager]。 以下链接将帮助您入门：

* 有关[!UICONTROL Google Campaign Manager]日志，请参阅[将Google活动管理器数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *和*，与您的[!DNL Audience Manager]顾问联系。
* 有关[!UICONTROL Google Ad Manager]（以前称为Google DFP）日志，请参阅[将Google Ad Manager数据文件导入Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *和*，与您的[!DNL Audience Manager]顾问联系。
* 有关其他广告服务器日志，请参阅[数据和元数据文件](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *和*&#x200B;与您的[!DNL Audience Manager]顾问联系。

如果已将日志数据导入[!DNL Audience Manager]，请咨询[!DNL Audience Manager]顾问或[客户关怀](https://helpx.adobe.com/cn/contact/enterprise-support.ec.html)，为您启用[!UICONTROL Actionable Log Files]。

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## 使用可操作的日志文件{#working-with-actionable-log-files}

对于[!UICONTROL Actionable Log Files]，广告服务器日志中的信息以[!DNL Audience Manager]的方式捕获，与从实时网站交互中捕获数据的方式相同。 [!DNL Audience Manager] 连接到广告服务器日志存储，解析日志中的信息，并将日志数据作为可操作信号发送到我们的数据收 [集服务器](../../reference/system-components/components-data-collection.md#dcs-pcs)。

您仍需要设置基于规则的特征来捕获可操作信号。 了解如何在[Audience Manager用户界面](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)中或使用我们的[批量管理工具](../../reference/bulk-management-tools/bulk-create.md)设置基于规则的特征。 向下滚动到[可操作信号](../../integration/media-data-integration/actionable-log-files.md#actionable-signals)部分，列表可在基于规则的特征中使用的所有密钥。

>[!IMPORTANT]
>
>我们建议实施[!UICONTROL Actionable Log Files] *，而不是* [像素调用](../../integration/media-data-integration/impression-data-pixels.md)。 我们不鼓励使用这两种选项，因为这会导致特征频率计数的增加。

## 可操作信号{#actionable-signals}

信号是[!DNL Audience Manager]中[最小数据单元](../../reference/signal-trait-segment.md)。 [!UICONTROL Actionable Log Files] 允许您从广告服务器日志中捕获广告商、业务部门、创意和活动值，单击事件和转换事件作为信号。

请记住，要使用此信息进行受众创建和细分，您需要自己设置基于规则的特征。

### Google活动管理器日志{#dcm-logs-signals}中的可操作信号

下表列表了[!DNL Google Campaign Manager]日志文件中的可操作信号：

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
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>表示Google活动管理器中转换活动的数字ID。 此字段映射到Google活动管理器中的活动ID。 </p> <p> <p>提示：您可以从Google活动管理器中捕获多个或特定的转化活动。 使用<code> d_conversion = activity ID</code>为Google活动管理器中的每个转换活动创建特征。 </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>仅适用于转化事件。 </p> <p>此字段映射到Google活动管理器中的转换ID。 指示用户从Google活动管理器转换之前的活动。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> 进行点击后转换。 </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> 获得印象后转换。 </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> 用于不匹配的转换。转换无法与以前的活动匹配。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">UTC印象、单击或转换事件的日期和时间。 1970-01-01 00:00:00 UTC以微秒表示。</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>广告商数据源的集成代码。 请注意，这与Audience Manager数据源无关。</p> <p>此字段映射到Google活动管理器中的广告商组ID。 </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>业务单位ID。 此字段映射到Google活动管理器中的广告商ID。 </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Google活动管理器提供的活动ID。</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Google活动管理器提供的创意ID。 </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> 销售额以美元计，为-6的幂。 乘以1.000.000，以1美元金额。</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件类型。 Audience Manager从Google活动管理器日志文件名中读取事件类型，并将其转换为可操作的信号。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按钮。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 转换。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获Google活动管理器数据的数据源的ID。 请参阅<a href="../../features/manage-datasources.md#create-data-source">如何创建数据源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号在[!DNL Audience Manager]中捕获，如实时`HTTP`调用。 以下示例调用包含有关[!DNL Google Campaign Manager]转换事件的信息。 调用不一定必须在示例调用中包含&#x200B;*all*&#x200B;信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

对于平均大小为200万行的[!DNL Google Campaign Manager]日志文件，根据可操作信号创建的任何特征在我们处理日志后大约一小时内即可实现。

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Google Campaign Manager]日志中提供的事件时间戳将被接受并传递给[!UICONTROL Data Collection Servers]。
>
>* 如果[!DNL Google Campaign Manager]日志文件中的数据行没有时间戳，我们将`HTTP`调用的时间用作事件时间戳。
>* 如果[!DNL Google Campaign Manager]日志文件中的数据行包含格式错误的时间戳，我们将忽略整行。


<br> 

### 来自[!DNL Google Ad Manager]日志{#ad-manager-logs-signals}的可操作信号

下表列表了[!DNL Google Ad Manager]日志文件中的可操作信号：


| 日志文件中的标题名称 | 信号 | 描述 |
---------|----------|---------
| `LineItemId` | `d_lineitem` | 已交付广告管理器行项目的数字ID |
| `OrderId` | `d_orderid` | 包含已交付行项目和创意的广告管理器订单的数字ID。 |
| `CreativeId` | `d_creative` | 已交付广告管理器创意的数字ID。 |
| `-` | `d_event` | 指示事件类型。 Audience Manager从广告管理器日志文件名中读取事件类型并将其转换为可操作的信号。 接受的值为：<br> <ul><li>d_事件= imp表示印象。</li><li>d_事件=单击鼠标。</li><li>d_事件= conv表示转换和活动。</li></ul> |
| `-` | `d_src` | 用于捕获Ad Manager数据的数据源的ID。 请参阅[如何创建数据源](/help/using/features/manage-datasources.md)。 |

表中描述的信号以Audience Manager形式捕获，如实时HTTP调用。 以下示例调用包含有关Google Ad Manager中转换事件的信息。 调用不一定必须包括示例调用中的所有信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>[!DNL Google Ad Manager]日志中提供的事件时间戳将被接受并传递给[!UICONTROL Data Collection Servers]。
>
>* 如果[!DNL Google Ad Manager]日志文件中的数据行没有时间戳，我们将`HTTP`调用的时间用作事件时间戳。
>* 如果[!DNL Google Ad Manager]日志文件中的数据行包含格式错误的时间戳，我们将忽略整行。


<br> 

### 通用广告服务器日志{#generic-logs-signals}中的可操作信号

首先，必须将广告服务器日志存入我们的AmazonS3存储桶中。 要实现此目的，请阅读[Audience Optimization报告和可操作日志文件的](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *和*，与您的[!DNL Audience Manager]顾问联系。 下表列表了来自通用日志文件的可操作信号：

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
   <td colname="col3"> <p> UTC印象、单击或转换事件的日期和时间。 使用<code>yyyy-MM-dd HH:mm:ss</code>格式。 </p></td> 
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
   <td colname="col3"> <p>业务单位ID。  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>日志文件中的活动ID。</p> </td> 
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
   <td colname="col3"> 购买或其他转换金额。 数据类型：浮动。 </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>指示事件类型。 Audience Manager从日志文件名中读取事件类型并将其转换为可操作的信号。 请参阅<a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">日志文件命名约定</a>。 </p> <p>接受的值为： </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> 展示次数。 </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> 按钮。 </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> 转换。 </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>用于捕获日志数据的数据源的ID。 请参阅<a href="../../features/manage-datasources.md#create-data-source">如何创建数据源</a>。 </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

表中描述的信号在[!DNL Audience Manager]中捕获，如实时`HTTP`调用。 调用不一定必须在示例调用中包含&#x200B;*all*&#x200B;信号。

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## 在Audience Manager用户界面{#actionable-signals-in-ui}中处理可操作信号

您可以在[信号搜索](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md)接口中视图传入的可操作信号。

转到&#x200B;**受众数据**(1)>**信号**(2)>**搜索**(3)并选择&#x200B;**可操作日志文件**(4)过滤器。

![UI中的可操作信号](/help/using/integration/assets/alf-in-signals.png)

要使用可操作信号创建基于规则的特征，请选择&#x200B;**可操作日志文件**(1)，选择要用作特征规则(2)的可操作信号，然后按&#x200B;**从所选信号创建特征**(3)。

![根据信号创建特征](/help/using/integration/assets/alf-create-trait.png)


## 用例 {#use-cases}

实施[!UICONTROL Actionable Log Files]的一个好处是将[最近和频率](../../features/segments/recency-and-frequency.md)控制应用到任何包含可操作信号的基于规则的特征](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)。 [例如，这允许您在媒体活动中以频率限制用户在特定创意中的显示次数。 请阅读[即时跨设备抑制](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)以了解如何执行此操作。 其他使用案例包括：

### 重新定位用户

重新定位查看了创意123但未单击或转换的用户，并向他们展示创意456。 执行此操作:

1. 创建特征以捕获看到创意的用户。 假设您命名特征[!DNL Creative Trait 123]。 使用特征规则：

   `d_creative == 123 AND d_event == imp`

2. 创建特征以捕获单击或转换的用户。 假设您将此名称命名为[!DNL Click and Converter]。 使用特征规则：

   `d_event == click OR d_event=conv`

3. 创建一个区段，以填充查看了creative 123但未单击或转换的用户。 将其命名为[!DNL Retarget Users]并使用段规则：

   `Creative Trait 123 AND NOT Click and Converter`

4. 使用创意456将区段[!DNL Retarget Users]映射到目标和目标中的目标用户。

### 在“活动报告”或“受众实验室”中使用GoogleAudience Optimization管理器Floodlight活动

[可标记泛](https://support.google.com/dcm/partner/answer/4293719?hl=en) 光灯的广告商跟踪用户转化率。使用[!UICONTROL Actionable Log Files]，您可以在[Audience Optimization报告](../../reporting/audience-optimization-reports/audience-optimization-reports.md)或[受众实验室](../../features/audience-lab/audience-lab.md)中跟踪[!DNL Google Campaign Manager]转换：

1. 创建特征，并使用以下特征规则从广告服务器日志捕获转换：

   `d_event == conv AND d_conversion == 123`

   在Audience Manager[!UICONTROL UI]中创建特征时，选择[!UICONTROL Conversion]作为[!UICONTROL Event Type]。

2. 创建特征后，将开始在[!UICONTROL Audience Optimization Reports]和[!UICONTROL Audience Lab]中报告转换。

>[!MORELIKETHIS]
>
>* [将Google活动管理器数据文件导入Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization 报表](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

