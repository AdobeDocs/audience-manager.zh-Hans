---
description: 活动使用情况报告可帮助您查看和跟踪Audience Manager实例的活动使用情况，以便将实际使用情况与合同约定进行比较。
keywords: activity, usage, reporting, commitment
seo-description: 活动使用情况报告可帮助您查看和跟踪Audience Manager实例的活动使用情况，以便将实际使用情况与合同约定进行比较。
seo-title: 活动使用情况报告
solution: Audience Manager
title: 活动使用情况报告
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 7a3914af8fb225508f57724a75fe2547aac3f241

---


# 活动使用情况报告

## 概述 {#overview}

它 [!UICONTROL Activity Usage Report] 可帮助您查看和跟踪Audience Manager实例的活动使用情况，让您清楚地了解活动使用情况与合同约定的情况。

此外，您还可以根据需要随 [!UICONTROL Activity Usage Report] 时下载记录保存和自定义分析。

## 注意事项 {#considerations}

此 [!UICONTROL Activity Usage Report] 选项适用于所有具有管理员权限 [的Audience Manager用户](edit-account-settings.md)。

> [!IMPORTANT]
>
> 此 [!UICONTROL Activity Usage Report] 处显示Audience manager实例的活动使用情况统计数据。 有关与活动使用情况相关的任何收费查询，请联系您的Adobe代表。

## 用例 {#use-cases}

有两种主要用例 [!UICONTROL Activity Usage Report]:

* **根据活动使用情况承诺跟踪实际实例活动使用情况**:大多数客户每个Audience manager实例都有月度活动承诺，然后将其累积到所有实例的年度活动承诺中。 虽然此报告不是付费报告，但对于您是否超出承诺的活动使用情况，它可以提供有帮助的指导。
* **实施更改的验证**:如果您最近更新了实施，如设置Analytics服务器端转发或更改Target服务器调用设置，此报告可以帮助您检查新活动卷是否与预期的活动卷一致。

## 使用活动使用情况报告 {#using}

要查看 [!UICONTROL Activity Usage Report]，请登录您的Audience manager帐户，然后转到 **[!UICONTROL Administration]**>**[!UICONTROL Usage]**。

![aur-ui](assets/aur-ui.png)

接下来，使用 **[!UICONTROL Reporting Interval]**过滤器选择生成报告的时间间隔。 您可以选择30天、60天、90天或自定义日期范围。

加载报表后，您可以查看选定时段 [!UICONTROL Activities] 的细目。

[!UICONTROL Activities] 定义与Audience manager的所有现场和离站交互的总计，分为以下类别：

* **[!UICONTROL Server Calls]**:任何从网站、服务器、电子邮件、移动应用程序或其他系统发送到Audience manager的数据收集或检索事件。
* **[!UICONTROL Pixel Calls](前称[!UICONTROL Impression Server Calls])**:从广告（例如定位平台中的印象量）或向Audience Manager发送的电子邮件印象调用中收集的数据。 这要求查询字符串 `d_event` 中存在该参数。
* **[!UICONTROL On-Boarded Records]**:从您自己的客户关系管理系统(CRM)或其他离线数据文件（如呼叫中心记录、设备ID和来自外部数据提供商的自定义数据服务）中摄取的唯一记录。
* **[!UICONTROL Log File Records]**:从定位平台摄取到Audience manager的日志文件中的独特记录。

> [!NOTE]
> 唯一记录定义了Adobe代表Audience manager客户存储的文件中的每个数据记录。

此外，您还可以使用图 [!UICONTROL Activity Usage Trends] 形类型在两种类型的图形之间切换。

![aur-ui图](assets/aur-ui-graphs.png)

您还可以将光标悬停在时间轴中的特定日期上，以查看该日期的详细使用情况。

![aur-hover](assets/aur-hover.png)

## 导出活动使用情况报告 {#export}

要更好地概述Audience manager的活动使用级别，您可以 [!UICONTROL Activity Usage Report] 根据要包含的记录类型导出。

![aur-export](assets/aur-export.png)

和报 **[!UICONTROL Onboarded Records Breakdown]**表**[!UICONTROL Onsite Server Calls Breakdown]** 提供了对可用于这些活动的源数据的最精细的分析。 归因于这些细分的卷基于您的实施。

### 载入的记录细分 {#onboarded-breakdown}

此报告包含按数据源细分的已载入记录。

### 现场服务器呼叫故障 {#onsite-breakdown}

此报告包含从以下三个来源对服务器调用的细分： [!UICONTROL Analytics]、 [!UICONTROL Target]和 [!UICONTROL Other]。

* **[!UICONTROL Analytics]**:这些是从所有Adobe Analytics实例传递到Audience manager的收费服务器调用，包括服务器端转发。 次服务器调用或重复的服务器调用（如从多个报表包进行服务器端转发）不是收费活动，因此它们不包括在此细目中。
* **[!UICONTROL Target]**:这些是从Adobe target到Audience Manager的服务器端调用，用于作为服务器到服务器集成的一部分检索Audience manager细分数据。
* **[!UICONTROL Other]**:包括来自任何其他网站或系统（合作伙伴站点、直接服务器调用等）、移动浏览器／应用程序调用[!DNL SDK]、[!DNL DIL]活动调用和调用的[!DNL DCS]调用。 如果设置为[!DNL Target]cookie集成（而不是服务器到服务器），则还包括来自的调用。
