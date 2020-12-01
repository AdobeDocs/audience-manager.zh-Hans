---
description: 信号是Audience Manager内信息的最小单位。 它们表示您在线属性上的用户交互或用户活动，并传递给Audience Manager以用于特征规则。
seo-description: 信号是Audience Manager内信息的最小单位。 它们表示您在线属性上的用户交互或用户活动，并传递给Audience Manager以用于特征规则。
seo-title: 了解信号
title: 了解信号
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 2%

---


# 了解信号

信号是Audience Manager内信息的最小单位。 它们表示您的在线属性上的用户交互或用户活动，并传递给Audience Manager以用于特征规则。

[!DNL Audience Manager] 使用键值对来表示信号。例如，以下信号可能表示访客已到达包含电子产品的网页：

* `page = electronics`

[信号仪表板符](../../features/data-explorer/data-explorer-signals-dashboard.md)显示多种类型的信号属性，可用于创建新特征。 下面是可用信号属性的详细视图:

* *键值对* 向您显示接收信号的键值对 [!DNL Audience Manager]。
* *信号* 类型描述每个信号的类别。信号属于以下类别之一：
   * [可操作的日志文件](/help/using/integration/media-data-integration/actionable-log-files.md):从媒体性能日志文件接收的实时信号；
   * [!DNL Adobe Analytics]:从你的账户收到的实时 [!DNL Adobe Analytics] 信号；
   * 一般在线数据：由受众活动生成且未包含在可操作日志文件和[!DNL Adobe Analytics]中的实时数据；
   * 载入的记录：通过批量数据传输接收的数据。
* *信号* 源取决于信号类型：
   * 对于已载入的信号，信号源是数据源名称。
   * 对于源自[!DNL Adobe Analytics]的信号，数据源将始终为报表包。
   * 对于可操作的日志文件和一般在线数据，不显示信号源信息。
* *“总* 计数”显示过去7天内接收实时信号 [!DNL Audience Manager] 的总次数。
* *“Traits”* 中会显示信号是否属于任何特征。单击箭头可查看包含相应信号的特征。 对于不属于任何特征的信号，列值将变为[!UICONTROL Create Onboarded Trait]或[!UICONTROL Create Rule-Based Trait]。

## 信号数据刷新频率

由于Audience Manager每天处理的数据量很大，[!UICONTROL Data Explorer]会根据信号类型以固定时间间隔刷新显示的信号数据：

* 实时信号数据（可操作的日志文件、[!DNL Adobe Analytics]数据和一般在线数据）每4到6小时刷新一次。
* 载入的信号数据每24小时更新一次。

## 相关概念

[信号、特征和区段](/help/using/reference/signal-trait-segment.md)