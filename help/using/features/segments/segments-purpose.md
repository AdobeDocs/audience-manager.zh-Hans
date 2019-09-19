---
description: 使用区段生成器描述区段、其组成部分和规则创建。
seo-description: 使用区段生成器描述区段、其组成部分和规则创建。
seo-title: 细分用途、组成和规则
solution: Audience Manager
title: 细分用途、组成和规则
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# 区段：目的、构成和规则 {#segments-purpose-composition-and-rules}

描述区段、其组成部分以及规则创建 [!UICONTROL Segment Builder]。

## 细分用途

A *`segment`* (或 *`audience`*)是共享通用属性的一组用户。 在Audience manager中，您可以使用服务器端规则创建区段。 通过这些规则，您可以根据网站访客属性(如：

* 行为;
* 人口（年龄、性别、收入等）;
* 您可以在用户界面中定义的其他特性。

## 细分组成

Audience manager区段是由个人或特征组组成的服务器端规则。 特征由称为键值对的数据元素组成。 除了您在区段级别设置的规则之外，这些键值对还包含符合访客资格的特征和区段成员资格条件。

## Adobe Analytics细分映射的注意事项

 在将Adobe Analytics区段或报表包映射到您的Experience cloud组织时，Audience manager会自动创建新的对应只读区段和特征。 您不能从Audience manager编辑或更改这些区段的存储位置。 但是，您对映射的Adobe Analytics区段或报表包执行的任何更改都会反映在Audience Manager中。

>[!TIP]
>
>Audience manager细分与细分不 [!DNL Adobe Analytics] 同。 阅 [读了解Analytics和Audience manager中的细分](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) ，深入了解差异。

## 使用Segment Builder创建基于规则的细分

与响应简单是／否条件的传统像素不同，区段生成器允许您创建复杂的区段要求。 与特征一样，区段使用表 [!DNL Boolean] 达式([!DNL AND]、 [!DNL OR]、 [!DNL NOT])、比较运算符（大于、小于、等于等）和新近度／频率标准来评估数据。 这些功能有助于创建与您的业务需求相关的有重点的受众细分。

## 优点

细分可以改进基于像素的标准受众创建／细分流程，因为它们允许您：

* 构建具有第一方和第三方特征的相关有用细分。
* 使用布尔运算符、比较表达式和最近期／频率标准创建复杂的细分规则。
* 将区段数据发送到目标合作伙伴。
* 使用Audience manager报告监控性能。

>[!MORE_LIKE_THIS]
>
>* [信号、特征和区段](../../reference/signal-trait-segment.md)

