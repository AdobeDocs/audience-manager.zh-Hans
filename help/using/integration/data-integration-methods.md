---
description: Audience Manager如何与其他数据提供商和系统交换信息的高层概述。
seo-description: Audience Manager如何与其他数据提供商和系统交换信息的高层概述。
seo-title: 数据集成方法
solution: Audience Manager
title: 数据集成方法
uuid: 17a4179a-e99 b-49eb-8f45-f2946 afbd27 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 数据集成方法 {#data-integration-methods}

Audience Manager如何与其他数据提供商和系统交换信息的高层概述。

## Supported Data Integration Methods: Real-Time and Server-to-Server {#supported-methods}

选择正确的集成方法取决于业务需求和数据合作伙伴的技术能力。Audience Manager通过以下任一方法与其他数据提供商交换访客信息：

* **实时：** 在用户访问您的网站时立即传输数据。This method is also known as a *`synchronous`* integration.
* **批次(服务器到服务器)：** 在访客离开页面后，在服务器之间以设置的预定传输数据。This method is also known as an *`out-of-band`* or *`asynchronous`* integration.

## Prerequisites: Create a Trait Taxonomy {#prereqs}

Before the integration process begins, remember to [create traits](../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI. 分类将包含组织在逻辑层次结构中的所有特征。

## Integration Use Cases {#integration-use-cases}

Audience Manager数据集成方法的使用案例摘要及其优缺点。

### 实时服务器到服务器集成

<!-- c_int_types_use_cases.xml -->

实时服务器到服务器数据集成可快速同步Audience Manager服务器与其他定位系统之间的用户数据。在大多数情况下，数据交换在数秒或几分钟内进行，具体取决于定位系统的刷新速率。但是请注意，目标系统确定此刷新时间间隔，而非Audience Manager。此外，刷新速率可能因不同系统而异。服务器到服务器的集成是数据交换的首选集成类型。每当定向合作伙伴可以支持时，Audience Manager都会使用此方法。

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>优势: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">允许您为细分资格限定用户，而无需在页面、视频播放器等中再次查看这些区段。 </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 减少页面HTTP调用的数量。调用更少有助于保留用户体验。 </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">帮助您进行时间敏感定位，以便快速对合格用户采取行动。 </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">当移动到DSP进行站外定位时有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺点：</td>
  <td class="stentry"> 当您需要在同一页面上定位用户时或下一页根据相应区段的符合资格的用户进行定位时，对于现场定位更不有用。</td>
 </tr>
</table>

### 服务器到服务器批量集成

服务器到服务器的批集成捆绑数据并以固定时间间隔发送给其他系统，而不是实时发送到其他系统。数据传输时间间隔从24小时开始。一些数据提供程序仅支持此集成类型。但是，我们已经看到了从批量集成到实时集成方法的普遍趋势。

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>优势: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">允许您为细分资格限定用户，而无需在页面、视频播放器等中再次查看这些区段。 </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">适用于不太敏感的定位。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺点：</td>
  <td class="stentry"> 同步间隔可延迟针对最新数据的定位。</td>
 </tr>
</table>

### 实时调用

当用户访问您的网站或在页面上采取行动时，实时调用与Audience Manager交换数据。通过此方法，定位系统获得最更新的细分资格数据，并可在内容或广告交付决策过程中考虑该信息。此外，此过程还可与publisher广告服务器一起使用，在这些服务器中，我们将合格的细分更新到作为关键值对阅读的第一方cookie。Currently, Audience Manager uses real-time calls to integrate with [!DNL Target] and other content management systems.

<table> 
 <tr>
  <td> <p>优势: </p></td>
  <td> <p> 允许您根据最近的区段资格定位下一页、内容区域或广告印象。 </p></td> 
 </tr> 
 <tr>
  <td> <p>缺点： </p></td>
  <td> <p>从页面中添加对Audience Manager的调用。</p></td>
 </tr> 
</table>


### 像素同步到定位系统

像素同步可将区段映射到页面上的像素。当用户符合特定区段的条件时，像素会触发和传输数据。像素同步是一种简单而可靠的数据传输机制。顶级数据提供商和系统很少使用它。

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>优势: </p></td>
  <td class="stentry"> <p> 实时数据传输。 </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>缺点： </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">可以从页面添加大量客户端调用。 </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">不可靠地进行数据传输。5%到20%的损失是正常的。 </li>
   </ul></td>
 </tr> 
</table>

## How to Choose a Data Delivery Method {#data-delivery-choices}

介绍通过同步(实时)或异步(服务器到服务器)方法发送数据的技术和业务原因。

<!-- c_int_delivery_choices.xml -->

### 选择数据交付类型

* **技术注意事项：** 数据交付取决于数据合作伙伴的技术能力。Audience Manager可以通过浏览器实时发送/接收数据，或通过脱机、服务器到服务器通信流程进行批量更新。
* **业务注意事项：** 选择一种交付方法或另一种交付方式的业务原因取决于目标合作伙伴的技术能力以及您希望如何使用此数据。通常，在您需要立即对用户数据采取行动时，同步数据传输很有用。异步数据传输在不需要立即采取操作以及有时间构建更深入的用户配置文件以供以后使用时很有用。

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

Audience Manager如何与第三方供应商进行同步数据交换的一般概述。

### 实时数据传输

<!-- c_int_overview_sync.xml -->

实时数据传输将细分ID作为用户访问或在您的网站上进行操作，以供用户访问或采取行动。通常，当用户在您的库存中导航时需要立即确定或对用户进行分组时，同步数据传输很有用。

### 实时数据集成步骤

实时数据集成流程如下所示：

1. 用户访问包含Audience Manager代码的客户站点。
1. Audience Manager loads an Iframe and makes a call to the [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. 第三方将该用户的区段信息返回Audience Manager。
1. Audience Manager可获取细分信息并使其可用于定位。

![](assets/rt_reduce70.png)

## Batch Data Transfer Process {#batch-data-transfer-process}

Audience Manager如何与第三方供应商同步(实时)交换数据的概况。

### 批量数据集成

<!-- c_int_overview_async.xml -->

批处理(服务器到服务器)数据集成过程遵循实时数据传输过程中概述的大多数步骤。但是，用户信息保存到我们的服务器并定期与第三方数据提供商同步，而不是立即返回区段ID。异步数据传输过程在以下情况下很有用：

* 不需要进行即时数据传输。
* 收集数据以构建大量细分用户。
* You want to reduce data discrepancies and `HTTP` calls from the browser.

### 批量数据集成步骤

1. 用户访问客户站点。
1. Audience Manager和第三方数据提供商为访客分配唯一ID(通常使用cookie)。
1. Audience Manager调用第三方数据提供商以匹配访客ID。
1. 计划的请求通常在每天间隔内，在Audience Manager与您的第三方数据提供商之间交换访客区段数据。

![](assets/s2s_70.png)

For information describing the time frames when Audience Manager processes inbound and outbound Server-to-Server ([!UICONTROL S2S]) file transfers, see [Reporting and File Transfer Time-Frame Guidelines](../reference/reporting-file-transfer-timeframe.md).
