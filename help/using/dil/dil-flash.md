---
description: 收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。
seo-description: 收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。
seo-title: Flash DIL
solution: Audience Manager
title: FlashDIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---


# Flash DIL{#flash-dil}

收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是一 [!DNL ActionScript] 个代码库，可让您在Audience Manager中处理视频播放数据。[!DNL Flash DIL] 通过捕获Adobe库传 [!UICONTROL AppMeasurement] 递到Analytics的SWF内容。[!DNL Flash DIL] 将该数据发送到单独 [!UICONTROL DIL] 的JavaScript数据收集模块，该模块将该信息传递给Audience Manager。分析数据([!UICONTROL Props]、[!UICONTROL eVars]、事件等) 从[!DNL FLA]文件捕获的信号在Audience Manager中可用作特征或未使用信号。

## FlashDIL数据收集{#requirements}的要求

一般实施和代码相关要求。

<!-- 

c_flash_dil_intro.xml

 -->

**实施要求**

[!UICONTROL Flash] 数据收集需要：

* [!UICONTROL DIL]类库(`dil.swc`)。 从您的合作伙伴解决方案联系人处获取[!UICONTROL DIL]类库。

* 页面上的JavaScript [!UICONTROL DIL]数据收集代码。
* [DIL](../dil/dil-flash.md#flash-dil-actionscript) ActionScript库，加载到要从中收集数据的Flash对象中。
* Adobe[!DNL AppMeasurement] [!DNL AS]库（版本3.5.2或更高版本）加载了要从中收集数据的[!DNL Flash]对象。

**将AllowScriptAccess设置为 `Always` 或`sameDomain`**

加载SWF文件的HTML代码中的`AllowScriptAccess`控制从SWF文件执行出站URL访问的能力。 配置[!UICONTROL Flash DIL]Flash集成时，请确保将`AllowScriptAccess`参数设置为`always`或`sameDomain`。 [!UICONTROL Flash DIL] 如果设置为，则数 `AllowScriptAccess` 据收集将无 `never`效。请参阅[控制对脚本的访问或主机网页](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS代 [!UICONTROL DIL] 码放置**

尝试将JS [!UICONTROL DIL]数据收集模块放在页面上，以便它在[!DNL FLA]文件之前加载。 当[!DNL FLA]文件首先加载时，在[!UICONTROL DIL]数据收集准备就绪之前，您可能会错过[!UICONTROL Flash DIL]发送到该模块的初始数据信号。 但是，一旦实例化，[!UICONTROL DIL]数据收集模块将捕获由[!UICONTROL Flash DIL]传入的所有后续SWF文件数据。

## 由FlashDIL{#data-collected}收集的数据

[!UICONTROL Flash DIL] 从Adobe库捕获页面视图、链接跟踪、媒体跟踪和其他媒体视图 [!UICONTROL AppMeasurement] 事件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**页面视图事件**

除非`s.trackVars`另有规定，[!UICONTROL Flash DIL]将从Adobe AppMeasurement收集以下数据：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**链接跟踪事件**

除非`s.linkTrackVars`另有规定，[!UICONTROL Flash DIL]将从Adobe[!UICONTROL AppMeasurement]收集以下数据：

* `pe` （调用的跟踪链接类型）
* `pev1` (链接 URL)
* `pev2`（链接文本）

**媒体跟踪事件**

除非`s.Media.trackVars`另有规定，[!UICONTROL Flash DIL]将收集“页面视图”事件部分中枚举的所有数据。

**其他数据点**

默认情况下，会收集来自这些参数的数据：

* `mediaName` （媒体／视频元素名称）
* `mediaAdName` (广告名称)
* `mediaAdParentName` （广告嵌套在下的主媒体内容的名称）
* `mediaAdParentPod` （播放广告的主要内容中的窗格或广告中断）
* `mediaAdParentPodPos` (播放广告的窗格中的数字位置。一个窗格中可以播放多个广告。

## FlashDILAudience Manager{#flash-dil-data}中的数据

[!UICONTROL Flash DIL]模块将Adobe AppMeasurement数据转换为Audience Manager特征和未使用信号。

<!-- 

c_flash_dil_in_aam.xml

 -->

分析[!UICONTROL Props]、[!UICONTROL eVars]和事件的工作方式与Audience Manager中的特征类似。 特征是键值对，用于构建区段。 例如，在`c30=foo`等Analytics属性中，`c30`是键（常数）,`foo`是值（变量）。

**将Audience Manager特征与分析变量匹配**

要使用[!UICONTROL Flash DIL]传递的Analytics数据，您应创建键值前缀为`c_`的Audience Manager特征。

有关示例，请参阅表：

| 分析数据元素 | 分析示例 | 作为Audience Manager特征 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/分析数据作为未使用信号**

Audience Manager接受Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件，即使没有相应的特征。 在这种情况下，数据不可用于特征创建，而是显示在[未使用的信号报告](../reporting/dynamic-reports/unused-signals.md)中。 要充分利用这些信息，请创建与[!UICONTROL Flash DIL]库传入的AnalyticsAudience Manager匹配的特征。

## FlashDILActionScript库{#flash-dil-actionscript}

[!DNL Flash]对象的代码，用于将Analytics数据发送到Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 对于每个[!DNL Flash]对象，代码仅支持一个合作伙伴实例(`d.partner`)。
   >
   >
* 需要Adobe[!UICONTROL AppMeasurement] [!DNL AS]库版本3.5.2或更高版本。


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [特征](../features/traits/trait-details-page.md)
>* [信号、特征和区段](../reference/signal-trait-segment.md)
>* [键值对说明](../reference/key-value-pairs-explained.md)
>* [关键变量的前缀要求](../features/traits/trait-variable-prefixes.md)

