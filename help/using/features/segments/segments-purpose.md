---
description: 使用Segment Builder描述区段、其组成部分以及规则创建。
seo-description: 使用Segment Builder描述区段、其组成部分以及规则创建。
seo-title: 细分用途、组成和规则
solution: Audience Manager
title: 细分用途、组成和规则
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 细分： 目的、构成和规则 {#segments-purpose-composition-and-rules}

描述区段、其组成部分以及规则创建 [!UICONTROL Segment Builder]。

## 细分用途

( *`segment`* 或) *`audience`*&#x200B;是共享通用属性的一组用户。 在受众管理器中，您可以使用服务器端规则创建区段。 通过这些规则，您可以根据站点受众属性(如：

* 行为;
* 人口（年龄、性别、收入等）;
* 您可以在用户界面中定义的其他特性。

## 细分组成

受众管理器区段是由单个或一组特征组成的服务器端规则。 特征由称为键值对的数据元素组成。 除了在区段级别设置的规则外，这些键值对还包含符合特征和区段成员资格访客的条件。

## Adobe Analytics细分映射的注意事项

在将Adobe Analytics区段或报表包映射到您的Experience Cloud组织时，受众管理器会自动创建新的对应只读区段和特征。 您无法从存储管理器编辑或更改这些区段的受众位置。 但是，您对映射的Adobe Analytics区段或报表包执行的任何更改都反映在受众管理器中。

>[!TIP]
>
>受众管理器细分与细分不 [!DNL Adobe Analytics] 同。 阅 [读了解Analytics和受众管理器中的](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) “细分”，详细描述不同之处。

## 使用区段生成器创建基于规则的区段

与响应简单“是／否”条件而触发的传统像素不同，区段生成器允许您创建复杂的区段要求。 与特征一样，细分使用 [!DNL Boolean] 表达式[!DNL AND]( [!DNL OR]、、 [!DNL NOT])、比较运算符（大于、小于、等于等）和最近使用频率标准来评估数据。 这些功能有助于创建与您的业务需求相关的有重点的受众细分。

## 优点

细分可以改进基于标准像素的受众创建／细分流程，因为它们允许您：

* 构建具有第一方和第三方特征的相关有用细分。
* 使用布尔运算符、比较表达式和最近使用频率标准创建复杂的细分规则。
* 将细分数据发送到目标合作伙伴。
* 使用受众管理器报告监控性能。

>[!MORELIKETHIS]
>
>* [信号、特征和细分](../../reference/signal-trait-segment.md)

