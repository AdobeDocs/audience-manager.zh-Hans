---
description: 简要概述Audience Manager如何与其他数据提供商和系统交换信息。
seo-description: 简要概述Audience Manager如何与其他数据提供商和系统交换信息。
seo-title: 数据集成方法
solution: Audience Manager
title: 数据集成方法
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: 第三方集成
exl-id: 26225461-c35c-4db1-9517-99e82ce163b9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 1%

---

# 数据集成方法 {#data-integration-methods}

简要概述Audience Manager如何与其他数据提供商和系统交换信息。

## 支持的数据集成方法：实时和[!DNL Server-to-Server] {#supported-methods}

选择正确的集成方法取决于业务需求和数据合作伙伴的技术能力的组合。 Audience Manager可通过以下任一方法与其他数据提供商交换访客信息：

* **实时：** 用户访问您的网站时立即传输数据。此方法也称为&#x200B;*`synchronous`*&#x200B;集成。
* **批处理([!DNL Server-to-Server]):** 在访客离开页面后，按照设定的计划在服务器之间传输数据。此方法也称为&#x200B;*`out-of-band`*&#x200B;或&#x200B;*`asynchronous`*&#x200B;集成。

## 先决条件：创建特征分类 {#prereqs}

在集成过程开始之前，请记住在[!DNL Audience Manager] UI中[创建特征](../features/traits/create-onboarded-rule-based-traits.md)和[文件夹结构](../features/traits/trait-storage.md#create-trait-storage-folder)。 分类将包含您在逻辑层次结构中组织的所有[!UICONTROL traits]。

## 集成用例{#integration-use-cases}

Audience Manager数据集成方法的用例摘要以及每种方法的优缺点。

### 实时[!DNL Server-to-Server]集成

<!-- c_int_types_use_cases.xml -->

实时[!DNL server-to-server]数据集成可在Audience Manager服务器和另一个定位系统之间快速同步用户数据。 在大多数情况下，数据交换会在几秒或几分钟内进行，具体取决于定位系统的刷新率。 但请注意，目标系统会确定此刷新间隔，而不是Audience Manager。 此外，刷新率可在不同系统之间改变。 实时[!UICONTROL server-to-server]集成是数据交换的首选集成类型。 Audience Manager在定位合作伙伴能够支持时使用此方法。

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>优势: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">允许您在页面上、视频播放器等中不再看到区段，就能确定用户是否符合区段的条件。 </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> 减少页面中的HTTP调用数。 更少的调用有助于保留用户体验。 </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">帮助进行时间敏感型定位，以便您能够快速对符合条件的用户执行操作。 </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">在移动到DSP进行站外定位时很有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺点：</td>
  <td class="stentry"> 当您需要根据某个用户是否符合该区段的资格条件，在同一页面或下一页面上定位用户时，现场定位的用法就变得不那么有用了。</td>
 </tr>
</table>

### [!DNL Server-to-Server] 批量集成

[!DNL server-to-server]批量集成捆绑数据，并以设定的间隔而不是近乎实时的方式将其发送到其他系统。 数据传输间隔从24小时开始。 某些数据提供程序仅支持此集成类型。 但是，我们看到了从批量集成向实时集成方法的一般趋势。

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>优势: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">允许您在页面上、视频播放器等中不再看到区段，就能确定用户是否符合区段的条件。 </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">对于非时间敏感型定位非常有用。 </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> 缺点：</td>
  <td class="stentry"> 同步间隔可以延迟针对最新数据的定位。</td>
 </tr>
</table>

### 实时调用

当用户访问您的网站或在页面上执行操作时，实时调用会立即与Audience Manager交换数据。 通过此方法，定位系统可以获得最新的区段鉴别数据，并可在内容或广告投放决策期间考虑该信息。 此外，此过程还适用于发布者广告服务器，在该服务器中，我们会将符合条件的区段更新为第一方Cookie，该Cookie将作为键值对读入广告调用中。 目前，Audience Manager使用实时调用与[!DNL Adobe Target]和其他内容管理系统集成。

<table> 
 <tr>
  <td> <p>优势: </p></td>
  <td> <p> 允许您根据最近的区段鉴别来定位下一页面、内容区域或广告展示。 </p></td> 
 </tr> 
 <tr>
  <td> <p>缺点： </p></td>
  <td> <p>从页面添加对Audience Manager的调用。</p></td>
 </tr> 
</table>


### 与定位系统同步的像素

像素同步将区段映射到页面上的像素。 当用户符合某个特定段的条件时，该像素会触发并传输数据。 像素同步是一种基本且不可靠的数据传输机制。 顶级数据提供商和系统很少使用它。

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
    <li id="li_CD91F3DC92F2429293787D61506E5E04">数据传输不可靠。 5%至20%的损失是正常的。 </li>
   </ul></td>
 </tr> 
</table>

## 如何选择数据提交方法{#data-delivery-choices}

描述通过同步（实时）或异步（服务器到服务器）方法发送数据的技术和业务原因。

<!-- c_int_delivery_choices.xml -->

### 选择数据提交类型

* **技术注意事项：** 数据交付取决于数据合作伙伴的技术能力。Audience Manager可以从浏览器实时发送/接收数据，或通过离线的服务器到服务器通信流程进行批量更新。
* **业务注意事项：** 选择一种或另一种交付方法的业务原因取决于目标合作伙伴的技术能力以及您希望如何使用此数据。通常，当您需要立即对用户数据采取操作时，同步数据传输非常有用。 当不需要立即执行操作，并且您有时间构建更深入的用户配置文件以供日后使用时，异步数据传输可能会非常有用。

## 实时数据传输进程{#real-time-data-transfer-process}

有关Audience Manager如何与第三方供应商执行同步数据交换的一般概述。

### 实时数据传输

<!-- c_int_overview_sync.xml -->

当用户访问您的网站或对您的网站采取操作时，实时数据传输会发送和接收区段ID。 通常，当您需要在库存中导航或立即划分用户区段时，同步数据传输非常有用。

### 实时数据集成步骤

实时数据集成过程的工作方式如下：

1. 用户访问包含Audience Manager代码的客户网站。
1. Audience Manager加载一个Iframe并对[!UICONTROL Data Collection Server]([!DNL DCS])进行调用。
1. [!DNL DCS]会（实时）调用第三方服务器以检查供应商是否具有有关用户的任何区段信息。
1. 第三方返回有关该用户的区段信息以进行Audience Manager。
1. Audience Manager摄取区段信息，并将其用于定位。

![](assets/rt_reduce70.png)

## 批量数据传输流程 {#batch-data-transfer-process}

有关Audience Manager如何与第三方供应商同步（实时）交换数据的一般概述。

### 批量数据集成

<!-- c_int_overview_async.xml -->

批量([!DNL server-to-server])数据集成过程遵循实时数据传输过程中列出的大多数步骤。 但是，用户信息不会立即返回区段ID，而是会定期保存到我们的服务器并与第三方数据提供商进行同步。 在以下情况下，异步数据传输过程非常有用：

* 无需立即进行数据传输。
* 收集数据以构建大量分段用户池。
* 您希望减少来自浏览器的数据差异和`HTTP`调用。

### 批量数据集成步骤

1. 用户访问客户网站。
1. Audience Manager和第三方数据提供商为访客分配一个唯一ID（通常使用Cookie）。
1. Audience Manager调用第三方数据提供程序以匹配访客ID。
1. 在Audience Manager与第三方数据提供商之间交换访客区段数据的计划请求（通常以每日间隔为单位）。

![](assets/s2s_70.png)

有关描述Audience Manager处理入站和出站[!DNL Server-to-Server]([!UICONTROL S2S])文件传输时的时间范围的信息，请参阅[报告和文件传输时间范围准则](../reference/reporting-file-transfer-timeframe.md)。
