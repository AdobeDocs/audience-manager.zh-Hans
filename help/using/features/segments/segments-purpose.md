---
description: 使用区段生成器描述区段、其组成部分和规则创建。
seo-description: 使用区段生成器描述区段、其组成部分和规则创建。
seo-title: 区段目的、构成和规则
solution: Audience Manager
title: 区段目的、构成和规则
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 区段
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# 区段：目的、构成和规则 {#segments-purpose-composition-and-rules}

描述[!UICONTROL segments]、其组成部分以及使用[!UICONTROL Segment Builder]创建规则。

## [!UICONTROL Segments]的用途

*`segment`*（或&#x200B;*`audience`*）是一组共享通用属性的用户。 在Audience Manager中，使用服务器端规则创建[!UICONTROL segments]。 这些规则允许您根据网站访客属性构建受众群组，例如：

* 行为;
* 人口统计（年龄、性别、收入等）;
* 您可以在用户界面中定义的其他特征。

## [!UICONTROL Segment] 组合物

Audience Manager[!UICONTROL segment]是由单个或多组特征组成的服务器端规则。 特征由称为键值对的数据元素组成。 除了在[!UICONTROL segment]级别设置的规则之外，这些键值对还包含使访客符合特征和[!UICONTROL segment]成员资格的条件。

## 关于[!UICONTROL Adobe Analytics] [!UICONTROL Segment]映射的注意事项

将Adobe Analytics [!UICONTROL segments]或报表包映射到Experience Cloud组织时，Audience Manager会自动创建新的、相应的只读[!UICONTROL segments]和特征。 不能从Audience Manager中编辑或更改这些[!UICONTROL segments]的存储位置。 但是，您对映射的Adobe Analytics [!UICONTROL segments]或报表包执行的任何更改都将反映在Audience Manager中。

>[!TIP]
>
>Audience Manager[!UICONTROL segments]与[!DNL Adobe Analytics] [!UICONTROL segments]不同。 请阅读[了解Analytics和Audience Manager中的区段](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) ，以深入了解两者之间的差异。

## 使用[!UICONTROL Segment Builder]创建基于规则的[!UICONTROL Segments]

与响应简单“是”/“否”条件而触发的传统像素不同，[!UICONTROL Segment Builder]允许您创建复杂的[!UICONTROL segment]要求。 与[!UICONTROL traits]类似，[!UICONTROL segments]使用[!DNL Boolean]表达式([!DNL AND]、[!DNL OR]、[!DNL NOT])、比较运算符（大于、小于、等于等）和回访间隔/频度标准来评估数据。 这些功能有助于创建与您的业务需求相关的重点受众[!UICONTROL segments]。

## 优点

[!UICONTROL Segments] 改进了基于像素的标准受众创建/分段流程，因为通过这些流程，您可以：

* 构建具有第一方和第三方特征的相关有用[!UICONTROL segments]。
* 使用布尔运算符、比较表达式和回访间隔/频度标准创建复杂的分段规则。
* 将[!UICONTROL segment]数据发送到目标合作伙伴。
* 使用Audience Manager报告监控性能。

>[!MORELIKETHIS]
>
>* [信号、特征和区段](../../reference/signal-trait-segment.md)

