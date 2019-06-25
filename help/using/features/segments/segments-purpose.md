---
description: 使用区段生成器描述细分及其组成部分和规则创建。
seo-description: 使用区段生成器描述细分及其组成部分和规则创建。
seo-title: 区段用途、构图和规则
solution: Audience Manager
title: 区段用途、构图和规则
uuid: 886d4aem-b1 b6-4983-b4 fb-b552 d54 d51 ba
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes segments, their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## 区段用途

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. 在Audience Manager中，您可以使用服务器端规则创建细分。这些规则允许您根据网站访客属性构建受众组，例如：

* 行为;
* 人口统计(年龄、性别、收入等);
* 您可以在用户界面中定义的其他特性。

## 细分排版

Audience Manager区段是一个服务器端规则，由个人或特征组组成。特征由称为键值对的数据元素组成。这些键值对除了在细分级别设置的规则之外，还包含符合资格和细分会员资格访客资格的标准。

## 关于Adobe Analytics细分映射的注意事项

将Adobe Analytics区段或报表包映射到Experience Cloud组织时，Audience Manager会自动创建新的、对应的、只读的细分和特征。您无法从Audience Manager编辑或更改这些区段的存储位置。但是，在Audience Manager中对映射的Adobe Analytics区段或报表包执行的任何更改都会反映出来。

>[!TIP]
>
>Audience Manager segments are different from [!DNL Adobe Analytics] segments. Read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.

## 使用区段生成器创建基于规则的区段

与触发简单是非条件的传统像素不同，细分生成器允许您创建复杂的区段要求。Like traits, segments evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. 这些功能有助于创建与您的业务需求相关的重点受众细分。

## 优点

根据标准像素的受众创建/细分流程，细分可以得到改进，因为您可以：

* 使用第一方和第三方特征构建相关的实用细分。
* 使用Boolean操作符、比较表达式以及最近/频率条件创建复杂的复杂细分规则。
* 将区段数据发送给目标合作伙伴。
* 使用Audience Manager报告监控性能。

>[!MORE_ LIKE_ This]
>
>* [信号、特征和区段](../../reference/signal-trait-segment.md)

