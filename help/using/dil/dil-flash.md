---
description: 收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止开发电子烟产品。 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 扩展。
><br>
>现有客户可以继续使用其 [!DNL DIL] 实现。 但是，Adobe将不会开发 [!DNL DIL] 超越了这一点。 建议客户评估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 长期数据收集策略。
><br>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而是。

收集从FLA文件发送到Analytics的数据，并在Audience Manager中处理该信息。

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 是 [!DNL ActionScript] 代码库允许您在Audience Manager中处理视频播放数据。 [!DNL Flash DIL] 通过在Adobe中捕获SWF内容来工作 [!UICONTROL AppMeasurement] 库将传递到Analytics。 [!DNL Flash DIL] 将该数据发送到单独的 [!UICONTROL DIL] JavaScript数据收集模块，用于将该信息传递给Audience Manager。 分析数据( [!UICONTROL Props]， [!UICONTROL eVars]、事件等) 从 [!DNL FLA] 文件可在Audience Manager中作为特征或未使用的信号使用。

## FlashDIL数据收集的要求 {#requirements}

常规实施和代码相关要求。

<!-- 

c_flash_dil_intro.xml

 -->

**实施要求**

[!UICONTROL Flash] 数据收集需要：

* 此 [!UICONTROL DIL] 类库( `dil.swc`)。 获取 [!UICONTROL DIL] Partner Solutions联系人提供的类库。

* JavaScript [!UICONTROL DIL] 页面上的数据收集代码。
* [DILActionScript库](../dil/dil-flash.md#flash-dil-actionscript) 加载到要从中收集数据的Flash对象中。
* Adobe [!DNL AppMeasurement] [!DNL AS] 库（版本3.5.2或更高版本）加载了 [!DNL Flash] 要从中收集数据的对象。

**将AllowScriptAccess设置为 `Always` 或`sameDomain`**

此 `AllowScriptAccess` 在加载SWF文件的HTML代码中，控制从SWF文件内执行出站URL访问的能力。 当您配置 [!UICONTROL Flash DIL] 数据集成，确保Flash `AllowScriptAccess` 参数设置为 `always` 或 `sameDomain`. [!UICONTROL Flash DIL] 如果符合以下条件，则数据收集将无法正常工作 `AllowScriptAccess` 设置为 `never`. 参见 [控制对脚本或主机网页的访问](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] 代码放置**

尝试放置JS [!UICONTROL DIL] 页面上的数据收集模块，以便在页面加载之前 [!DNL FLA] 文件。 当 [!DNL FLA] 文件先加载，然后再加载 [!UICONTROL DIL] 数据收集已准备就绪，您可能遗漏了初始数据信号 [!UICONTROL Flash DIL] 发送到该模块。 但是，一旦实例化， [!UICONTROL DIL] 数据收集模块将捕获所有后续传入的SWF文件数据 [!UICONTROL Flash DIL].

## FlashDIL收集的数据 {#data-collected}

[!UICONTROL Flash DIL] 从Adobe中捕获页面查看、链接跟踪、媒体跟踪和其他媒体查看事件 [!UICONTROL AppMeasurement] 库。

<!-- 

r_flash_dil_data_collected.xml

 -->

**页面查看事件**

除非另有指定 `s.trackVars`， [!UICONTROL Flash DIL] 从Adobe AppMeasurement收集以下数据：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**链接跟踪事件**

除非另有指定 `s.linkTrackVars`， [!UICONTROL Flash DIL] 从Adobe收集以下数据 [!UICONTROL AppMeasurement]：

* `pe` （调用的跟踪链接类型）
* `pev1` (链接 URL)
* `pev2`（链接文本）

**媒体跟踪事件**

除非另有指定 `s.Media.trackVars`， [!UICONTROL Flash DIL] 收集页面查看事件部分中枚举的所有数据。

**其他数据点**

默认情况下，将从这些参数中收集数据：

* `mediaName` （媒体/视频元素名称）
* `mediaAdName` (广告名称)
* `mediaAdParentName` （广告嵌套在其下的主媒体内容的名称）
* `mediaAdParentPod` （广告播放所在的主要内容中的面板或广告时间）
* `mediaAdParentPodPos` (广告在面板中播放时的数字位置。 一个面板中可以播放多个广告。

## FlashAudience Manager中的DIL数据 {#flash-dil-data}

此 [!UICONTROL Flash DIL] 模块可将Adobe AppMeasurement数据转换为Audience Manager特征和未使用的信号。

<!-- 

c_flash_dil_in_aam.xml

 -->

分析 [!UICONTROL Props]， [!UICONTROL eVars]和事件的作用方式与特征在Audience Manager中相似。 特征是键值对，用于构建区段。 例如，在Analytics属性中，如 `c30=foo`， `c30` 是键（常量）和 `foo` 是值（变量）。

**将Audience Manager特征与Analytics变量匹配**

使用由传递的Analytics数据 [!UICONTROL Flash DIL]，您应创建键值带有前缀的Audience Manager特征 `c_`.

有关示例，请参阅表：

| Analytics数据元素 | Analytics示例 | 作为Audience Manager特征 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**将DIL/分析数据作为未使用的信号**

Audience Manager接受Analytics [!UICONTROL Props]， [!UICONTROL eVars]、和事件，即使没有相应的特征也是如此。 在这种情况下，数据不可用于特征创建，并显示在 [“未使用的信号”报表](../reporting/dynamic-reports/unused-signals.md) 而是。 要充分利用此信息，请创建与通过传递的Analytics数据匹配的Audience Manager特征 [!UICONTROL Flash DIL] 库。

## FlashDILActionScript库 {#flash-dil-actionscript}

您的代码 [!DNL Flash] 对象以将Analytics数据发送到Audience Manager。

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 针对每个 [!DNL Flash] 对象，则代码支持一个合作伙伴实例( `d.partner`)。
>
>* 需要Adobe [!UICONTROL AppMeasurement] [!DNL AS] 库版本3.5.2或更高版本。

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
