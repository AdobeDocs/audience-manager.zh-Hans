---
description: 了解区段的组成以及用于设置受众资格标准的表达式。还可以了解有关数据传输方式的信息。
landing-page-description: 了解区段的组成以及用于设置受众资格标准的表达式。还可以了解有关数据传输方式的信息。
short-description: 了解区段的组成以及用于设置受众资格标准的表达式。还可以了解有关数据传输方式的信息。
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: 信号、特征和区段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 21%

---

# [!UICONTROL Signals]、[!UICONTROL Traits]和[!UICONTROL Segments] {#signals-traits-and-segments}

描述[!DNL Audience Manager] [!UICONTROL segment]的组件、用于设置受众资格标准的表达式，以及如何在事件调用中传输数据。

## 构成和目的

[!DNL Audience Manager]数据包含[!UICONTROL signals]、[!UICONTROL traits]、[!UICONTROL segments]和相关资格规则。 数据元素和规则结合起来创建[!UICONTROL segments]。 [!UICONTROL Segments]将网站访客组织到相关组中。 下表定义了[!DNL Audience Manager] [!UICONTROL segment]中的三个主要组件。

| 元素 | 包含 | 示例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals]是[!DNL Audience Manager]中最小的数据单元，以[键值对](../reference/key-value-pairs-explained.md).<br><br>表示<ul><li>键是定义数据集的一个常量（例如，性别、颜色、价格）。</li><li>该值是一个与常量相关的变量（例如，男性/女性，绿色，100）。</li></ul>比较运算符连接键值对并设置它们之间的关系。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一个或多个[!UICONTROL signals].<br><br>的组合 [!DNL Boolean]表达式和比较运算符允许您创建[!UICONTROL trait]资格规则。 <br><br>使用[!UICONTROL traits]和[!UICONTROL trait]组的组合创建精确的资格要求。 | 从可用的[!UICONTROL signals]中，您可以创建表达为`product=camera AND price>1000`的`High End Camera Browser`规则 |
| [!UICONTROL Segment] | 共享一组通用属性并符合相关[!UICONTROL traits]条件的用户。 [!DNL Boolean]表达式以及回访间隔/频率要求，允许您创建[!UICONTROL segment]资格规则。<br><br>使用[!UICONTROL trait]和[!UICONTROL segment]规则的组合创建精确的资格要求。 | 从可用的[!UICONTROL traits]和[!UICONTROL signals]中，您可以创建表达为`(product=camera AND type=digital SLR) OR (price>1000)`的[!UICONTROL segment]规则 |

请使用下图来记录[!UICONTROL signals]、[!UICONTROL traits]和[!UICONTROL segments]之间的关系。

![](assets/signals-traits-segments.png)

使用可视工具和代码编辑器生成&#x200B;**规则[!UICONTROL Traits]和[!UICONTROL Segment]**

客户端使用[!DNL Audience Manager]用户界面中的可视工具和代码编辑器管理[!UICONTROL traits]和[!UICONTROL segments]。 可视化工具允许您使用搜索功能、弹出选项、下拉菜单和拖放功能创建规则。 代码编辑器为高级用户提供了一种以编程方式开发受众分段标准的方法。

**事件调用将数据发送到[!DNL Audience Manager]**

事件调用将数据从您的网站发送到[!DNL Audience Manager]。 该调用在[!DNL HTTP]请求中包含[!UICONTROL signal]、[!UICONTROL trait]和[!UICONTROL segment]数据。 事件本身就是[!DNL URL]字符串的`/event`部分之后的所有内容。 如以下示例所示，此进程只需要一个事件调用即可将多个变量传递到[!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [区段：目的、构成和规则](../features/segments/segments-purpose.md)
