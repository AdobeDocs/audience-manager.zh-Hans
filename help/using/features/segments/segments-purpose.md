---
description: 使用Segment Builder描述区段、其组成部分以及规则创建。
seo-description: 使用Segment Builder描述区段、其组成部分以及规则创建。
seo-title: 细分用途、组成和规则
solution: Audience Manager
title: 细分用途、组成和规则
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# 细分： 目的、构成和规则 {#segments-purpose-composition-and-rules}

描述 [!UICONTROL segments]其组成部分以及规则创建 [!UICONTROL Segment Builder]。

## 用途 [!UICONTROL Segments]

( *`segment`* 或) *`audience`*&#x200B;是共享通用属性的一组用户。 在Audience Manager中，您使 [!UICONTROL segments] 用服务器端规则进行创建。 通过这些规则，您可以根据站点受众属性(如：

* 行为;
* 人口（年龄、性别、收入等）;
* 您可以在用户界面中定义的其他特性。

## [!UICONTROL Segment] 组合物

Audience Manager [!UICONTROL segment] 是由个人或特征组组成的服务器端规则。 特征由称为键值对的数据元素组成。 除了您在级别设置的规 [!UICONTROL segment] 则外，这些键值对还包含符合特征和成员资格访客条件的 [!UICONTROL segment] 条件。

## 关于映射的 [!UICONTROL Adobe Analytics] 注 [!UICONTROL Segment] 意事项

将AdobeAnalytics或报 [!UICONTROL segments] 表包映射到您的Experience Cloud组织时，Audience Manager会自动创建新的、相应的只读 [!UICONTROL segments] 和特征。 您无法编辑或更改这些存储的位 [!UICONTROL segments] 置(从Audience Manager)。 但是，您对映射的AdobeAnalytics或报表包执行的 [!UICONTROL segments] 任何更改都反映在Audience Manager中。

>[!TIP]
>
>Audience Manager [!UICONTROL segments] 与其他 [!DNL Adobe Analytics][!UICONTROL segments]不同。 阅 [读了解Analytics的细分和Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) ，以详细描述不同之处。

## 创建基于规则的 [!UICONTROL Segments] [!UICONTROL Segment Builder]

与传统的响应简单“是／否”条件而触发的像素不同，您 [!UICONTROL Segment Builder] 可以创建复杂的 [!UICONTROL segment] 要求。 例如， [!UICONTROL traits]使用 [!UICONTROL segments] 表达式( [!DNL Boolean] 、[!DNL AND]、)、比较 [!DNL OR][!DNL NOT]运算符（大于、小于、等于等）和最近使用频率标准来评估数据。 这些功能有助于创建与您的 [!UICONTROL segments] 业务需求相关的有重点的受众。

## 优点

[!UICONTROL Segments] 改进基于标准像素的受众创建／分段流程，因为它们允许您：

* 利用第一方 [!UICONTROL segments] 和第三方特征构建相关、有用的内容。
* 使用布尔运算符、比较表达式和最近使用频率标准创建复杂的细分规则。
* 将数 [!UICONTROL segment] 据发送到目标合作伙伴。
* 使用Audience Manager报告监视性能。

>[!MORELIKETHIS]
>
>* [信号、特征和细分](../../reference/signal-trait-segment.md)

