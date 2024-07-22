---
description: 信号是Audience Manager内信息的最小单位。 它们表示在线资产上的用户交互或用户活动，并被传递到要在特征规则中使用的Audience Manager。
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: 了解信号
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# 了解信号

信号是Audience Manager内信息的最小单位。 它们表示在线资产上的用户交互或用户活动，并被传递到要在特征规则中使用的Audience Manager。

[!DNL Audience Manager]使用键值对表示信号。 例如，以下信号可能表示访客访问了包含电子产品的网页：

* `page = electronics`

[信号仪表板](../../features/data-explorer/data-explorer-signals-dashboard.md)显示可用于创建新特征的多种信号属性。 以下是可用信号属性的详细视图：

* *键值对*&#x200B;显示[!DNL Audience Manager]所接收信号的键值对。
* *信号类型*&#x200B;描述了每个信号的类别。 信号分为以下类别之一：
   * [可操作的日志文件](/help/using/integration/media-data-integration/actionable-log-files.md)：从媒体性能日志文件接收的实时信号；
   * [!DNL Adobe Analytics]：从您的[!DNL Adobe Analytics]帐户收到的实时信号；
   * 常规在线数据：受众活动生成的实时数据，未包含在可操作的日志文件和[!DNL Adobe Analytics]中；
   * 载入记录：通过批量数据传输接收的数据。
* *信号Source*&#x200B;取决于信号类型：
   * 对于已载入的信号，信号源是数据源名称。
   * 对于源自[!DNL Adobe Analytics]的信号，数据源将始终是报表包。
   * 对于可操作的日志文件和常规联机数据，不显示信号源信息。
* *总计数*&#x200B;显示[!DNL Audience Manager]在过去7天内接收实时信号的总次数。
* *包含在特征中*&#x200B;显示信号是否属于任何特征。 单击箭头可查看包含相应信号的特征。 对于不属于任何特征的信号，列值将更改为[!UICONTROL Create Onboarded Trait]或[!UICONTROL Create Rule-Based Trait]。

## 信号数据刷新频率

由于Audience Manager每天处理的数据量很大，[!UICONTROL Data Explorer]会根据信号类型以固定时间间隔刷新显示的信号数据：

* 实时信号数据（可操作的日志文件、[!DNL Adobe Analytics]数据和常规在线数据）每4到6小时刷新一次。
* 已载入的信号数据每24小时刷新一次。

## 相关概念

[信号、特征和区段](/help/using/reference/signal-trait-segment.md)
