---
description: 收集从FLA文件发送到Analytics的数据并在Audience Manager中处理该信息。
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: FlashDIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# FlashDIL{#flash-dil}

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此点之后不会开发[!DNL DIL]。 建议客户评估[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)。

收集从FLA文件发送到Analytics的数据并在Audience Manager中处理该信息。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL]是一个[!DNL ActionScript]代码库，允许您在Audience Manager中处理视频播放数据。 [!DNL Flash DIL]的工作方式是捕获Adobe[!UICONTROL AppMeasurement]SWF传递到Analytics的内容。 [!DNL Flash DIL]将该数据发送到单独的[!UICONTROL DIL] JavaScript数据收集模块，该模块会将该信息传递给Audience Manager。 Analytics数据（[!UICONTROL Props]、[!UICONTROL eVars]、事件等） 从[!DNL FLA]文件中捕获的信号，在Audience Manager中可以作为特征或未使用的信号。

## FlashDIL数据收集的要求 {#requirements}

常规实施和代码相关要求。

<!-- 

c_flash_dil_intro.xml

 -->

**实施要求**

[!UICONTROL Flash]数据收集需要：

* [!UICONTROL DIL]类库(`dil.swc`)。 从合作伙伴解决方案联系人处获取[!UICONTROL DIL]类库。

* 页面上的JavaScript [!UICONTROL DIL]数据收集代码。
* [DILActionScript库](../dil/dil-flash.md#flash-dil-actionscript)已加载到要从中收集数据的Flash对象中。
* Adobe[!DNL AppMeasurement] [!DNL AS]库（版本3.5.2或更高版本）加载了要从中收集数据的[!DNL Flash]对象。

**将AllowScriptAccess设置为`Always`或`sameDomain`**

加载SWF文件的HTML代码中的`AllowScriptAccess`控制从SWF文件内执行出站URL访问的能力。 配置[!UICONTROL Flash DIL]数据集成时，请确保Flash`AllowScriptAccess`参数设置为`always`或`sameDomain`。 如果`AllowScriptAccess`设置为`never`，则[!UICONTROL Flash DIL]数据收集将不起作用。 请参阅[控制对脚本或主机网页的访问](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)。

**JS [!UICONTROL DIL]代码位置**

尝试将JS [!UICONTROL DIL]数据收集模块放在页面上，使其在[!DNL FLA]文件之前加载。 当[!DNL FLA]文件首次加载时，在[!UICONTROL DIL]数据收集准备就绪之前，您可能会丢失[!UICONTROL Flash DIL]发送到该模块的初始数据信号。 但是，一旦实例化，[!UICONTROL DIL]数据收集模块将捕获[!UICONTROL Flash DIL]传入的所有后续SWF文件数据。

## 按FlashDIL收集的数据 {#data-collected}

[!UICONTROL Flash DIL]从Adobe[!UICONTROL AppMeasurement]库中捕获页面查看、链接跟踪、媒体跟踪和其他媒体查看事件。

<!-- 

r_flash_dil_data_collected.xml

 -->

**页面查看事件**

除非`s.trackVars`另有指定，[!UICONTROL Flash DIL]否则从Adobe AppMeasurement中收集以下数据：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**链接跟踪事件**

除非`s.linkTrackVars`另有指定，[!UICONTROL Flash DIL]将从Adobe[!UICONTROL AppMeasurement]收集以下数据：

* `pe` （调用的跟踪链接类型）
* `pev1` （链接URL）
* `pev2`（链接文本）

**媒体跟踪事件**

除非`s.Media.trackVars`另有指定，[!UICONTROL Flash DIL]将收集页面查看事件部分中枚举的所有数据。

**其他数据点**

默认情况下，将从这些参数中收集数据：

* `mediaName` （媒体/视频元素名称）
* `mediaAdName` （广告名称）
* `mediaAdParentName` （广告嵌套在其下的主媒体内容的名称）
* `mediaAdParentPod` （广告播放所在的主要内容中的面板或广告时间）
* `mediaAdParentPodPos` (广告在面板中播放时的数字位置。 一个面板中可以播放多个广告。

## 在Audience Manager中FlashDIL数据 {#flash-dil-data}

[!UICONTROL Flash DIL]模块可将Adobe AppMeasurement数据转换为Audience Manager特征和未使用的信号。

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件的工作方式与Audience Manager中的特征类似。 特征是键值对，用于构建区段。 例如，在像`c30=foo`这样的Analytics prop中，`c30`是键（常量），`foo`是值（变量）。

**将Audience Manager特征与Analytics变量匹配**

要使用[!UICONTROL Flash DIL]传递的Analytics数据，您应该创建键值以`c_`为前缀的Audience Manager特征。

有关示例，请参阅表：

| Analytics数据元素 | Analytics示例 | 作为Audience Manager特征 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/分析数据作为未使用的信号**

即使没有相应的特征，Audience Manager也接受Analytics [!UICONTROL Props]、[!UICONTROL eVars]和事件。 在这种情况下，数据无法用于特征创建，而是显示在[未使用的信号报表](../reporting/dynamic-reports/unused-signals.md)中。 要充分利用此信息，请创建与[!UICONTROL Flash DIL]库传入的Analytics数据匹配的Audience Manager特征。

## FlashDILActionScript库 {#flash-dil-actionscript}

用于将Analytics数据发送到Audience Manager的[!DNL Flash]对象的代码。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 对于每个[!DNL Flash]对象，代码仅支持一个合作伙伴实例(`d.partner`)。
>
>* 需要Adobe[!UICONTROL AppMeasurement] [!DNL AS]库3.5.2或更高版本。

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
