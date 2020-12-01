---
description: 使用Segment Builder描述区段、其组成部分以及规则创建。
seo-description: 使用Segment Builder描述区段、其组成部分以及规则创建。
seo-title: 细分用途、组成和规则
solution: Audience Manager
title: 细分用途、组成和规则
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# 区段：目的、构成和规则 {#segments-purpose-composition-and-rules}

描述[!UICONTROL segments]、其组成部分以及使用[!UICONTROL Segment Builder]创建规则。

## [!UICONTROL Segments]的用途

*`segment`*（或&#x200B;*`audience`*）是一组共享通用属性的用户。 在Audience Manager中，使用服务器端规则创建[!UICONTROL segments]。 通过这些规则，您可以根据站点受众属性(如：

* 行为;
* 人口（年龄、性别、收入等）;
* 您可以在用户界面中定义的其他特性。

## [!UICONTROL Segment] 组合物

Audience Manager[!UICONTROL segment]是服务器端规则，由个人或特征组组成。 特征由称为键值对的数据元素组成。 除了您在[!UICONTROL segment]级别设置的规则外，这些键值对还包含符合特征访客和[!UICONTROL segment]成员资格条件的条件。

## 关于[!UICONTROL Adobe Analytics] [!UICONTROL Segment]映射的注意事项

当将Adobe Analytics[!UICONTROL segments]或报表包映射到您的Experience Cloud组织时，Audience Manager会自动创建新的、相应的只读[!UICONTROL segments]和特征。 不能编辑或更改这些[!UICONTROL segments]的存储位置，而不能从Audience Manager。 但是，您对映射的Adobe Analytics[!UICONTROL segments]或报表包执行的任何更改都反映在Audience Manager中。

>[!TIP]
>
>Audience Manager[!UICONTROL segments]与[!DNL Adobe Analytics] [!UICONTROL segments]不同。 请阅读[了解分析和Audience Manager中的细分](https://docs.adobe.com/content/help/zh-Hans/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)，详细了解差异。

## 使用[!UICONTROL Segment Builder]创建基于规则的[!UICONTROL Segments]

与响应简单“是／否”条件而触发的传统像素不同，[!UICONTROL Segment Builder]允许您创建复杂的[!UICONTROL segment]要求。 与[!UICONTROL traits]类似，[!UICONTROL segments]使用[!DNL Boolean]表达式([!DNL AND]、[!DNL OR]、[!DNL NOT])、比较运算符（大于、小于、等于等于等）和最近／频率标准来评估数据。 这些功能有助于创建与您的业务需求相关的重点受众[!UICONTROL segments]。

## 优点

[!UICONTROL Segments] 改进基于标准像素的受众创建／分段流程，因为它们允许您：

* 使用第一方和第三方特征构建相关、有用的[!UICONTROL segments]。
* 使用布尔运算符、比较表达式和最近使用频率标准创建复杂的细分规则。
* 将[!UICONTROL segment]数据发送到目标合作伙伴。
* 使用Audience Manager报告监视性能。

>[!MORELIKETHIS]
>
>* [信号、特征和区段](../../reference/signal-trait-segment.md)

