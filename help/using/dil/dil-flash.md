---
description: 收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。
seo-description: 收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833CFD-768e-4b16-95c5-debd8411 df38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是 [!DNL ActionScript] 一个代码库，可让您在Audience Manager中处理视频播放数据。[!DNL Flash DIL] 方法是捕获Adobe [!UICONTROL AppMeasurement] 库传入Analytics的SWF内容。[!DNL Flash DIL] 将这些数据发送到单独 [!UICONTROL DIL] 的JavaScript数据收集模块，该模块将该信息传递给Audience Manager。Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals.

## Requirements for Flash DIL Data Collection {#requirements}

一般实施和代码相关要求。

<!-- 

c_flash_dil_intro.xml

 -->

**实施要求**

[!UICONTROL Flash] 数据收集需要：

* [!UICONTROL DIL] 类库( `dil.swc`)。Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact.

* JavaScript [!UICONTROL DIL] data collection code on the page.
* [加载到Flash对象中的DIL ActionScript库](../dil/dil-flash.md#flash-dil-actionscript) ，您希望从中收集数据。
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**设置allowScriptAccess`Always``sameDomain`**

The `AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. When you configure a [!UICONTROL Flash DIL] data integration, make sure the Flash `AllowScriptAccess` parameter is set to `always` or `sameDomain`. [!UICONTROL Flash DIL] 如果设置为，则数据收集将 `AllowScriptAccess` 不起作用 `never`。See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS[!UICONTROL DIL]代码置入**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. [!DNL FLA] 当文件第一次加载时 [!UICONTROL DIL] ，在数据收集就绪之前，您可能会错过 [!UICONTROL Flash DIL] 发送到该模块的初始数据信号。However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL].

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] 从Adobe [!UICONTROL AppMeasurement] 库捕获页面查看、链接跟踪、媒体跟踪和其他媒体查看事件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**页面查看事件**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**链接跟踪事件**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (称为跟踪链接类型)
* `pev1` (链接 URL)
* `pev2`(链接文本)

**媒体跟踪事件**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**其他数据点**

默认情况下会收集这些参数中的数据：

* `mediaName` (媒体/视频元素名称)
* `mediaAdName` (广告名称)
* `mediaAdParentName` (广告嵌套在下方的主要媒体内容的名称)
* `mediaAdParentPod` (广告播放的主要内容内的窗格或广告中断)
* `mediaAdParentPodPos` (广告播放的窗格中的数字位置。多个广告可在窗格内播放。

>[!MORE_ LIKE_ This]
>
>* [AppMeasurement Flash、Flex和OSMF实施指南](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

[!UICONTROL Flash DIL] 该模块将Adobe AppMeasurement数据转换为Audience Manager特征和未使用的信号。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. 特征是关键值对，用于构建区段。For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**将Audience Manager特征与Analytics变量匹配**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

有关示例，请参见表：

| Analytics数据元素 | 分析示例 | Audience Manager特征 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics数据作为未使用信号**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library.

>[!MORE_ LIKE_ This]
>
>* [特征](../features/traits/trait-details-page.md)
>* [信号、特征和区段](../reference/signal-trait-segment.md)
>* [键值对解释](../reference/key-value-pairs-explained.md)
>* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)


## Flash DIL ActionScript Library {#flash-dil-actionscript}

[!DNL Flash] 对象的代码，用于将Analytics数据发送到Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only.
   >
   >
* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

