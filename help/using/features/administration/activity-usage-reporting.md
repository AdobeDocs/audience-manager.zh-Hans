---
description: 活动使用情况报表可帮助您查看和跟踪Audience Manager实例的活动使用情况，以便您可以将实际使用情况与合同承诺进行比较。
keywords: 活动、使用情况、报表、承诺
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: 活动使用情况报表
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## 概述 {#overview}

通过 [!UICONTROL Activity Usage Report]，您可以查看和跟踪 Audience Manager 实例的活动使用情况，从而清楚地了解实际的活动使用情况与合同承诺之间存在的差异。

此外，您可以根据需要随时下载[!UICONTROL Activity Usage Report]，以保留记录和自定义分析。

## 注意事项 {#considerations}

[!UICONTROL Activity Usage Report]适用于具有[管理员权限](edit-account-settings.md)的所有Audience Manager用户。

>[!IMPORTANT]
>
>[!UICONTROL Activity Usage Report]显示Audience Manager实例的活动使用情况统计数据。 有关与您的活动使用情况相关的任何计费查询，请联系您的Adobe代表。

## 用例 {#use-cases}

[!UICONTROL Activity Usage Report]有两个主要用例：

* **根据活动使用情况承诺跟踪实际实例活动使用情况**：大多数客户具有每个Audience Manager实例的每月估计活动承诺，然后将其累计到所有实例的每年活动承诺中。 虽然此报表不是计费报表，但它可以就您是否超出承诺的活动使用情况提供有益的指导。
* **验证实施更改**：如果您最近更新了实施，例如设置[!DNL Adobe Analytics]服务器端转发或更改[!DNL Adobe Target]服务器调用设置，此报表可以帮助您检查新的活动卷是否与预期的活动卷一致。

## 使用[!UICONTROL Activity Usage Report] {#using}

若要查看[!UICONTROL Activity Usage Report]，请登录到您的Audience Manager帐户，然后转到&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Usage]**。

![aur-ui](assets/aur-ui.png)

接下来，使用&#x200B;**[!UICONTROL Reporting Interval]**&#x200B;筛选器选择要为其生成报告的时间间隔。 您可以选择30、60、90天或自定义日期范围。

加载报告后，您可以看到选定时间段内[!UICONTROL Activities]的细分。

[!UICONTROL Activities]定义与Audience Manager的所有现场和异地交互的总计，分为以下类别：

* **[!UICONTROL Server Calls]**：从网站、服务器、电子邮件、移动应用程序或其他系统发送给Audience Manager的任何数据收集或检索事件。
* **[!UICONTROL Pixel Calls]（以前称为[!UICONTROL Impression Server Calls]）**：从广告收集的数据（例如来自定位平台的展示数量）或向Audience Manager发出的电子邮件展示调用数。 查询字符串中必须存在`d_event`参数。
* **[!UICONTROL On-Boarded Records]**：从您自己的客户关系管理系统(CRM)或其他离线数据文件中摄取的唯一记录，例如呼叫中心记录、设备ID和来自外部数据提供商的自定义数据馈送。
* **[!UICONTROL Log File Records]**：从定位平台摄取到Audience Manager中的日志文件中的唯一记录。

>[!NOTE]
>
>唯一记录定义由Adobe代表Audience Manager客户存储的文件中的每一条数据记录。

此外，您可以使用[!UICONTROL Activity Usage Trends]图形类型在两个图形类型之间切换。

![aur-ui-graphs](assets/aur-ui-graphs.png)

您还可以将光标悬停在时间轴中的特定日期上，以查看该日期的详细使用情况。

![aur-hover](assets/aur-hover.png)

## 正在导出[!UICONTROL Activity Usage Reports] {#export}

为了更好地了解Audience Manager活动使用级别，您可以根据要包含的记录类型导出[!UICONTROL Activity Usage Report]。

![aur-export](assets/aur-export.png)

**[!UICONTROL Onboarded Records Breakdown]**&#x200B;和&#x200B;**[!UICONTROL Onsite Server Calls Breakdown]**&#x200B;报表提供了这些活动可用源数据的最精细见解。 归因到这些划分的量将基于您的实施。

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

此报表包含按数据源细分的已载入记录。

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

此报表包含来自三个源的服务器调用细分：[!UICONTROL Analytics]、[!UICONTROL Target]和[!UICONTROL Other]。

* **[!UICONTROL Analytics]**：这些是从所有[!UICONTROL Adobe Analytics]实例传递到Audience Manager的可计费服务器调用，包括服务器端转发。 次级服务器调用或重复的服务器调用（与从多个报表包进行服务器端转发的情况一样）不计费，因此它们不会包含在此划分中。
* **[!UICONTROL Target]**：这些是从[!UICONTROL Adobe Target]到Audience Manager的服务器端调用，用于检索Audience Manager区段数据，作为服务器到服务器集成的一部分。
* **[!UICONTROL Other]**：包含来自任何其他网站或系统（合作伙伴网站、直接服务器调用等）的调用、通过[!DNL SDK]、[!DNL DIL]、事件调用和[!DNL DCS]调用进行的移动设备浏览器/应用程序调用。 如果设置为Cookie集成（而不是服务器到服务器），则还包括来自[!DNL Target]的调用。
