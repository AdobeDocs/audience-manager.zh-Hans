---
description: 活动使用报告可帮助您视图和跟踪Audience Manager实例的活动使用情况，以便将实际使用情况与合同约定进行比较。
keywords: activity, usage, reporting, commitment
seo-description: 活动使用报告可帮助您视图和跟踪Audience Manager实例的活动使用情况，以便将实际使用情况与合同约定进行比较。
seo-title: 活动使用情况报表
solution: Audience Manager
title: 活动使用情况报表
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 6%

---


# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 概述 {#overview}

通过 [!UICONTROL Activity Usage Report]，您可以查看和跟踪 Audience Manager 实例的活动使用情况，从而清楚地了解实际的活动使用情况与合同承诺之间存在的差异。

此外，您还可以随时 [!UICONTROL Activity Usage Report] 下载记录保存和自定义分析。

## 注意事项 {#considerations}

具有 [!UICONTROL Activity Usage Report] 管理员权限的所有Audience Manager [用户均可](edit-account-settings.md)。

>[!IMPORTANT]
>
>显示 [!UICONTROL Activity Usage Report] 您的活动实例的Audience Manager使用统计信息。 如需查询与活动使用情况相关的账单，请联系您的Adobe代表。

## 用例 {#use-cases}

有两种主要用例 [!UICONTROL Activity Usage Report]:

* **根据您的活动使用承诺跟踪实际实例活动使用情况**: 大多数客户每个活动实例都有月度估计的活动承诺，然后在所有实例中累计为年度Audience Manager承诺。 虽然此报表不是付费报表，但对于您是否超出承诺的活动使用情况，它可以提供有帮助的指导。
* **实施更改的验证**: 如果您最近更新了实施(如设置服 [!DNL Adobe Analytics] 务器端转发或更改服务器 [!DNL Adobe Target] 呼叫设置)，此报告可以帮助您检查新活动卷是否与预期活动卷一致。

## 使用 [!UICONTROL Activity Usage Report] {#using}

要查看 [!UICONTROL Activity Usage Report]，请登录您的Audience Manager帐户，然后转 **[!UICONTROL Administration]** 到> **[!UICONTROL Usage]**。

![aur ui](assets/aur-ui.png)

接下来，使 **[!UICONTROL Reporting Interval]** 用过滤器选择生成报告的时间间隔。 您可以选择30天、60天、90天或自定义日期范围。

加载报表后，您可以看到所选时 [!UICONTROL Activities] 段的细分。

[!UICONTROL Activities] 定义与Audience Manager的所有现场和异地交互的聚合总数，分为以下类别:

* **[!UICONTROL Server Calls]**: 任何从网站、服务器、电子邮件、移动应用程序或其他系统发送给Audience Manager的数据收集或检索事件。
* **[!UICONTROL Pixel Calls](前称[!UICONTROL Impression Server Calls])**: 从广告（例如定位平台的印象量）或向Audience Manager发送的电子邮件印象呼叫收集的数据。 这要求查询字符串`d_event`中存在该参数。
* **[!UICONTROL On-Boarded Records]**: 从您自己的客户关系管理系统(CRM)或其他离线数据文件（如呼叫中心记录、设备ID和来自外部数据提供商的自定义数据服务）中摄取的唯一记录。
* **[!UICONTROL Log File Records]**: 来自日志文件的唯一记录从定位平台引入Audience Manager。

>[!NOTE]
>
>唯一记录定义了Adobe代表Audience Manager客户存储的文件中的每个数据记录。

此外，还可以使用 [!UICONTROL Activity Usage Trends] 图形类型在两种图形类型之间切换。

![aur-ui图](assets/aur-ui-graphs.png)

您还可以将光标悬停在时间轴中的特定日期上，以查看该日期的详细使用情况。

![奥尔霍弗](assets/aur-hover.png)

## 导出 [!UICONTROL Activity Usage Reports] {#export}

要更好地概述Audience Manager活动使用级别，您可 [!UICONTROL Activity Usage Report] 以根据要包含的记录类型导出。

![aur export](assets/aur-export.png)

和 **[!UICONTROL Onboarded Records Breakdown]** 报 **[!UICONTROL Onsite Server Calls Breakdown]** 表可提供对这些活动可用源数据的最精确的分析。 归因于这些细分的卷基于您的实施。

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

此报告包含按数据源细分的已载入记录。

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

此报告包含来自三个来源的服务器调用细分： [!UICONTROL Analytics]、 [!UICONTROL Target]和 [!UICONTROL Other]。

* **[!UICONTROL Analytics]**: 这些是从所有实例传递到Audience Manager的 [!UICONTROL Adobe Analytics] 可计费服务器调用，包括服务器端转发。 辅助服务器调用或重复服务器调用（如从多个报表包进行服务器端转发）不是可计费的活动，因此它们不包括在此细分中。
* **[!UICONTROL Target]**: 这些是从服务器端到Audience Manager [!UICONTROL Adobe Target] 的调用，用于作为服务器到服务器集成的一部分检索Audience Manager段数据。
* **[!UICONTROL Other]**: 包括来自任何其他网站或系统（合作伙伴站点、直接服务器调用等）、移动浏览器／应用程序调用 [!DNL SDK]的 [!DNL DIL]调用、事件调用和 [!DNL DCS] 调用。 如果设置为 [!DNL Target] cookie集成（而非服务器到服务器），则还包括来自的调用。
