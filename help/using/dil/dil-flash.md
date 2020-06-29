---
description: 收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。
seo-description: 收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
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

[!UICONTROL Flash DIL] 是一个 [!DNL ActionScript] 代码库，它允许您在Audience Manager中处理视频播放数据。 [!DNL Flash DIL] 通过捕获Adobe库传递到Analytics [!UICONTROL AppMeasurement] 的SWF内容来工作。 [!DNL Flash DIL] 将该数据发送到单独的 [!UICONTROL DIL] JavaScript数据收集模块，该模块将该信息传递给Audience Manager。 Analytics数 [!UICONTROL Props]据( [!UICONTROL eVars]、事件等) 从文件捕获 [!DNL FLA] 的信号在Audience Manager中可作为特征或未使用的信号。

## Flash DIL数据收集要求 {#requirements}

一般实施和代码相关要求。

<!-- 

c_flash_dil_intro.xml

 -->

**实施要求**

[!UICONTROL Flash] 数据收集需要：

* 类 [!UICONTROL DIL] 库( `dil.swc`)。 从您的合 [!UICONTROL DIL] 作伙伴解决方案联系人处获取类库。

* 页面上 [!UICONTROL DIL] 的JavaScript数据收集代码。
* [DIL ActionScript库](../dil/dil-flash.md#flash-dil-actionscript) ，加载到要从中收集数据的Flash对象中。
* Adobe [!DNL AppMeasurement] 库( [!DNL AS] 版本3.5.2或更高版本)加载了要从 [!DNL Flash] 中收集数据的对象。

**将AllowScriptAccess设置为`Always`或`sameDomain`**

加 `AllowScriptAccess` 载SWF文件的HTML代码控制从SWF文件执行出站URL访问的能力。 配置数据集 [!UICONTROL Flash DIL] 成时，请确保Flash `AllowScriptAccess` 参数设置为 `always` 或 `sameDomain`。 [!UICONTROL Flash DIL] 如果设置为，则数 `AllowScriptAccess` 据收集将不 `never`工作 请参 [阅控制对脚本的访问或主机网页](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS代[!UICONTROL DIL]码放置**

尝试将JS数据 [!UICONTROL DIL] 收集模块放在页面上，以便在文件之前加 [!DNL FLA] 载。 当文件 [!DNL FLA] 首先加载时，在 [!UICONTROL DIL] 数据收集准备就绪之前，您可能会错过发送到该模 [!UICONTROL Flash DIL] 块的初始数据信号。 但是，一旦实例化， [!UICONTROL DIL] 数据收集模块将捕获传入的所有后续SWF文件数 [!UICONTROL Flash DIL]据。

## Flash DIL收集的数据 {#data-collected}

[!UICONTROL Flash DIL] 从Adobe库中捕获页面视图、链接跟踪、媒体跟踪和其他媒体视图 [!UICONTROL AppMeasurement] 事件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**页面视图事件**

除非另有规 `s.trackVars`定， [!UICONTROL Flash DIL] 否则从Adobe AppMeasurement收集以下数据：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**链接跟踪事件**

除非另有规 `s.linkTrackVars`定， [!UICONTROL Flash DIL] 否则从Adobe收集以下数据 [!UICONTROL AppMeasurement]:

* `pe` （调用的跟踪链接类型）
* `pev1` (链接 URL)
* `pev2`（链接文本）

**媒体跟踪事件**

除非另有指定，否则 `s.Media.trackVars`将收 [!UICONTROL Flash DIL] 集在“页面视图”事件部分中枚举的所有数据。

**其他数据点**

默认情况下，会收集来自这些参数的数据：

* `mediaName` （媒体／视频元素名称）
* `mediaAdName` (广告名称)
* `mediaAdParentName` （广告嵌套在下的主媒体内容的名称）
* `mediaAdParentPod` （播放广告的主要内容中的窗格或广告中断）
* `mediaAdParentPodPos` (播放广告的窗格中的数字位置。 一个窗格中可以播放多个广告。

## Audience Manager中的Flash DIL数据 {#flash-dil-data}

该模 [!UICONTROL Flash DIL] 块将Adobe AppMeasurement数据转换为Audience Manager特征和未使用信号。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]、 [!UICONTROL eVars]事件和Audience Manager的工作方式与相似。 特征是键值对，用于构建区段。 例如，在类似Analytics的 `c30=foo`prop `c30` 中，是键（常数） `foo` 和值（变量）。

**将Audience Manager特征与Analytics变量匹配**

要使用通过传递的Analytics [!UICONTROL Flash DIL]数据，您应创建键值前缀为的Audience Manager特征 `c_`。

有关示例，请参阅表：

| Analytics数据元素 | Analytics示例 | 作为Audience Manager特征 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics数据作为未使用信号**

Audience Manager接受 [!UICONTROL Props]Analytics [!UICONTROL eVars]、和事件，即使没有相应的特质。 在这种情况下，数据不可用于特征创建，而是显示在“未使用 [的信号”报](../reporting/dynamic-reports/unused-signals.md) 告中。 要充分利用这些信息，请创建与库传入的AnalyticsAudience Manager相匹配的 [!UICONTROL Flash DIL] 特征。

## Flash DIL ActionScript库 {#flash-dil-actionscript}

将Analytics数据 [!DNL Flash] 发送到Audience Manager的对象的代码。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 对于每 [!DNL Flash] 个对象，代码仅支持一个合作伙伴实 `d.partner`例()。
   >
   >
* 需要Adobe [!UICONTROL AppMeasurement] 库 [!DNL AS] 版本3.5.2或更高版本。


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

