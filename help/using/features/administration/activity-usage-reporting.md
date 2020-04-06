---
description: 活动使用报告可帮助您视图和跟踪受众管理者实例的活动使用情况，以便将实际使用情况与合同约定进行比较。
keywords: activity, usage, reporting, commitment
seo-description: 活动使用报告可帮助您视图和跟踪受众管理者实例的活动使用情况，以便将实际使用情况与合同约定进行比较。
seo-title: 活动使用报告
solution: Audience Manager
title: 活动使用报告
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# 活动使用报告

## 概述 {#overview}

它可 [!UICONTROL Activity Usage Report] 以帮助您视图和跟踪受众管理器实例的活动使用情况，让您清楚地了解活动使用情况与合同约定的情况。

此外，您还可以根据需要随 [!UICONTROL Activity Usage Report] 时下载记录保存和自定义分析。

## 注意事项 {#considerations}

此选项 [!UICONTROL Activity Usage Report] 适用于所有具有管理员权限的受众管 [理器用户](edit-account-settings.md)。

>[!IMPORTANT]
>
>显示 [!UICONTROL Activity Usage Report] 您的活动管理器实例的受众使用统计信息。 有关与您的活动使用情况相关的收费查询，请联系您的Adobe代表。

## 用例 {#use-cases}

有两种主要用例 [!UICONTROL Activity Usage Report]:

* **根据您的活动使用承诺跟踪实际实例活动使用情况**:大多数客户每个活动管理器实例都有月度估计的活动承诺，然后在所有实例中累计为每年的受众承诺。 虽然此报告不是付费报告，但对于您是否超出承诺的活动使用量，它可以提供有帮助的指导。
* **实施更改的验证**:如果您最近更新了实施，如设置Analytics服务器端转发或更改目标服务器调用设置，此报告可以帮助您检查新活动卷是否与预期活动卷一致。

## 使用活动使用情况报告 {#using}

要查看 [!UICONTROL Activity Usage Report]，请登录您的受众经理帐户，然后转到 **[!UICONTROL Administration]** > **[!UICONTROL Usage]**。

![aur-ui](assets/aur-ui.png)

接下来，使用 **[!UICONTROL Reporting Interval]** 过滤器选择生成报告的时间间隔。 您可以选择30天、60天、90天或自定义日期范围。

加载报表后，您可以查看选定时段 [!UICONTROL Activities] 的细目。

[!UICONTROL Activities] 定义与聚合经理的所有现场和离站交互的受众总数，分为以下类别:

* **[!UICONTROL Server Calls]**:任何从网站、服务器、电子邮件、移动应用程序或其他系统发送到受众管理器的数据收集或检索事件。
* **[!UICONTROL Pixel Calls](前称[!UICONTROL Impression Server Calls])**:从广告（如定位平台中的印象量）或向受众经理发送的电子邮件印象调用中收集的数据。 这要求在查询字符串`d_event`中存在该参数。
* **[!UICONTROL On-Boarded Records]**:从您自己的客户关系管理系统(CRM)或其他离线数据文件（如呼叫中心记录、设备ID和来自外部数据提供商的自定义数据服务）中摄取的唯一记录。
* **[!UICONTROL Log File Records]**:从定位平台引入到受众管理器的日志文件中的唯一记录。

>[!NOTE]
>
>唯一记录定义了Adobe代表受众经理客户存储的文件中的每个数据记录。

此外，您还可以使用图 [!UICONTROL Activity Usage Trends] 形类型在两种类型的图形之间切换。

![aur-ui图](assets/aur-ui-graphs.png)

您还可以将光标悬停在时间轴中的特定日期上，以查看该日期的详细使用情况。

![aur-hover](assets/aur-hover.png)

## 导出活动使用情况报告 {#export}

要更好地概述受众管理器活动的使用级别，您可以 [!UICONTROL Activity Usage Report] 根据要包含的记录类型导出。

![aur-export](assets/aur-export.png)

和 **[!UICONTROL Onboarded Records Breakdown]** 报 **[!UICONTROL Onsite Server Calls Breakdown]** 告可提供对这些活动可用源数据的最精细的分析。 归因于这些细分的卷基于您的实施。

### 载入的记录细分 {#onboarded-breakdown}

此报告包含按数据源细分的已载入记录。

### 现场服务器呼叫故障 {#onsite-breakdown}

此报告包含从以下三个来源对服务器调用的细分： [!UICONTROL Analytics]、 [!UICONTROL Target]和 [!UICONTROL Other]。

* **[!UICONTROL Analytics]**:这些是从所有Adobe Analytics实例传递给受众管理器的收费服务器调用，包括服务器端转发。 次服务器调用或重复服务器调用（如从多个报表包进行服务器端转发）不是收费活动，因此它们不包括在此细分中。
* **[!UICONTROL Target]**:这些是从Adobe目标到受众管理器的服务器端调用，作为服务器到服务器集成的一部分，它们用于检索受众管理器区段数据。
* **[!UICONTROL Other]**:包括来自任何其他网站或系统（合作伙伴站点、直接服务器调用等）、移动浏览器／应用程序调用的调 [!DNL SDK]用、 [!DNL DIL]事件调用和调 [!DNL DCS] 用。 如果设置为 [!DNL Target] cookie集成（而不是服务器到服务器），则还包括来自的调用。
