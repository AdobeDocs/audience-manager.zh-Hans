---
description: 概括介绍Audience Manager如何与其他数据提供商和系统交换信息。
seo-description: 概括介绍Audience Manager如何与其他数据提供商和系统交换信息。
seo-title: 数据集成方法
solution: Audience Manager
title: 数据集成方法
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 1%

---


# 数据集成方法 {#data-integration-methods}

概括介绍Audience Manager如何与其他数据提供商和系统交换信息。

## 支持的数据集成方法： 实时和服务器到服务器 {#supported-methods}

选择正确的集成方法取决于业务需求和数据合作伙伴的技术能力的组合。 Audience Manager通过以下任一方法与其他数据提供者交换访客信息：

* **实时：** 当用户访问您的网站时，立即传输数据。 此方法也称为集 *`synchronous`* 成。
* **批处理（服务器到服务器）:** 在访客离开页面后，在设置计划上的服务器之间传输数据。 此方法也称为或 *`out-of-band`* 集 *`asynchronous`* 成。

## 先决条件： 创建特征分类 {#prereqs}

在集成过程开始之前，请记 [住在UI](../features/traits/create-onboarded-rule-based-traits.md) 中创 [建特征和文](../features/traits/trait-storage.md#create-trait-storage-folder) 件夹 [!DNL Audience Manager] 结构。 分类将包含在逻辑层次结构中组织的所有特征。

## 集成用例 {#integration-use-cases}

Audience Manager数据集成方法的用例总结及各方法的优缺点。

### 实时服务器到服务器集成

<!-- c_int_types_use_cases.xml -->

实时服务器到服务器数据集成可快速同步Audience Manager服务器和另一个定位系统之间的用户数据。 在大多数情况下，数据交换会在几秒或几分钟内完成，具体取决于目标系统的刷新率。 但是，请注意，目标系统决定此刷新间隔，而非Audience Manager。 此外，刷新率可能因不同系统而异。 实时服务器到服务器集成是数据交换的首选集成类型。 Audience Manager在定位合作伙伴可以支持时使用此方法。

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>优势: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">允许您在页面、视频播放器等中确定用户的区段，而不再看到这些区段。 </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 减少页面中的HTTP调用数。 更少的呼叫有助于保留用户体验。 </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">帮助进行时间敏感型定位，以便快速对合格用户采取行动。 </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">当移至DSP进行异地定位时非常有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺点：</td>
  <td class="stentry"> 当您需要根据用户对该区段的资格进行目标，在同一页面或下一页面上对用户进行现场定位时，效果会更差。</td>
 </tr>
</table>

### 服务器到服务器批量集成

服务器到服务器的批量集成捆绑数据，并以设定的时间间隔发送数据到其他系统，而不是以接近实时的时间发送数据。 开始24小时后的数据传输间隔。 某些数据提供者仅支持此集成类型。 但是，我们看到了从批量集成转向实时集成方法的一般趋势。

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>优势: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">允许您在页面、视频播放器等中确定用户的区段，而不再看到这些区段。 </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">对于非时间敏感型定位很有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺点：</td>
  <td class="stentry"> 同步间隔可以延迟针对最新数据的定位。</td>
 </tr>
</table>

### 实时呼叫

当用户访问您的网站或在页面上执行操作时，实时呼叫会立即与Audience Manager交换数据。 通过此方法，定位系统可以获得最新的细分资格数据，并可在内容或广告投放决策时考虑这些信息。 此外，此过程还适用于发布者广告服务器，我们会将符合条件的区段更新为第一方cookie，作为键值对读入广告调用。 目前，Audience Manager使用实时呼叫与其他内容管理 [!DNL Target] 系统相集成。

<table> 
 <tr>
  <td> <p>优势: </p></td>
  <td> <p> 允许您根据最近的细分资格目标下一页、内容区域或广告印象。 </p></td> 
 </tr> 
 <tr>
  <td> <p>缺点： </p></td>
  <td> <p>从页面添加对Audience Manager的调用。</p></td>
 </tr> 
</table>


### 像素与定位系统同步

像素同步将段映射到页面上的像素。 当用户符合特定段的条件时，该像素会触发并传输数据。 像素同步是一种基本且不可靠的数据传输机制。 顶级数据提供商和系统很少使用它。

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">数据传输不可靠。 5%到20%的损失是正常的。 </li>
   </ul></td>
 </tr> 
</table>

## 如何选择数据投放方法 {#data-delivery-choices}

描述通过同步（实时）或异步（服务器到服务器）方法发送数据的技术和业务原因。

<!-- c_int_delivery_choices.xml -->

### 选择数据投放类型

* **技术注意事项：** 数据投放取决于数据合作伙伴的技术能力。 Audience Manager可以通过浏览器实时发送／接收数据，或通过离线、服务器到服务器的通信流程进行批量更新。
* **业务注意事项：** 选择一种或另一种投放方法的业务原因取决于目标合作伙伴的技术能力以及您希望如何使用这些数据。 通常，当您需要立即对用户数据采取操作时，同步数据传输很有用。 当不需要立即执行操作并且有时间构建更深入的用户用户档案供以后使用时，异步数据传输可能会很有用。

## 实时数据传输过程 {#real-time-data-transfer-process}

概述Audience Manager如何与第三方供应商进行同步数据交换。

### 实时数据传输

<!-- c_int_overview_sync.xml -->

实时数据传输以用户访问或在您的网站上采取操作的方式发送和接收区段ID。 通常，当您需要在用户浏览库存时立即确定用户资格或对用户进行细分时，同步数据传输会很有用。

### 实时数据集成步骤

实时数据集成过程的工作方式如下：

1. 用户访问包含Audience Manager代码的客户站点。
1. Audience Manager加载Iframe并调用( [!UICONTROL Data Collection Server] )[!DNL DCS]。
1. 该 [!DNL DCS] 服务器会实时调用第三方服务器，以检查供应商是否具有有关该用户的任何细分信息。
1. 第三方将有关该用户的区段信息返回给Audience Manager。
1. Audience Manager摄取区段信息，并使其可用于定位。

![](assets/rt_reduce70.png)

## 批数据传输流程 {#batch-data-transfer-process}

概述Audience Manager如何与第三方供应商同步（实时）交换数据。

### 批量数据集成

<!-- c_int_overview_async.xml -->

批处理（服务器到服务器）数据集成过程遵循实时数据传输过程中概述的大多数步骤。 但是，用户信息不会立即返回区段ID，而是会定期保存到我们的服务器上并与第三方数据提供程序同步。 在以下情况下，异步数据传输过程很有用：

* 无需立即进行数据传输。
* 收集数据以构建大量分段用户池。
* 您希望减少数据差异 `HTTP` 和来自浏览器的调用。

### 批数据集成步骤

1. 用户访问客户站点。
1. Audience Manager和第三方数据提供者为访客分配唯一ID（通常使用cookie）。
1. Audience Manager调用第三方数据提供程序以匹配访客ID。
1. 在访客与第三方数据提供商之间交换Audience Manager段数据的预定请求（通常在每日间隔内）。

![](assets/s2s_70.png)

有关描述Audience Manager处理入站和出站服务器到服务器()文件传输时的时[!UICONTROL S2S]间帧的信息，请参 [阅报告和文件传输时间帧准则](../reference/reporting-file-transfer-timeframe.md)。
