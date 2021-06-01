---
description: 介绍 Audience Manager 区段的组件、用于设置受众资格标准的表达式，以及如何在事件调用中传输数据。
landing-page-description: 介绍区段的组件、用于设置受众资格标准的表达式，以及数据传输方式。
seo-title: 信号、特征和区段
solution: Audience Manager
title: 信号、特征和区段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 参考
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---

# [!UICONTROL Signals]、  [!UICONTROL Traits]和  [!UICONTROL Segments] {#signals-traits-and-segments}

描述[!DNL Audience Manager] [!UICONTROL segment]的组件、用于设置受众资格标准的表达式，以及如何在事件调用中传输数据。

## 构成和用途

[!DNL Audience Manager] 数据由、 [!UICONTROL signals]、和相 [!UICONTROL traits]关的 [!UICONTROL segments]资格规则组成。数据元素和规则可结合使用来创建[!UICONTROL segments]。 [!UICONTROL Segments] 将网站访客组织到相关组中。下表定义了[!DNL Audience Manager] [!UICONTROL segment]中的三个主要组件。

| 元素 | 包含 | 示例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是中的最小数据单 [!DNL Audience Manager] 元，以键 [值对表示](../reference/key-value-pairs-explained.md)。<br><br><ul><li>键是用于定义数据集（例如，性别、颜色、价格）的常量。</li><li>该值是与常量相关的变量（例如，男/女、绿色、100）。</li></ul>比较运算符连接键值对并设置它们之间的关系。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一个或多个[!UICONTROL signals].<br><br>的组合 [!DNL Boolean] 通过表达式和比较运算符，您可以创建 [!UICONTROL trait] 资格规则。<br><br>通过组和组的组合，创建精确的资 [!UICONTROL traits] 格 [!UICONTROL trait] 要求。 | 从可用的[!UICONTROL signals]中，可以创建一个`High End Camera Browser`规则，如下所示：`product=camera AND price>1000` |
| [!UICONTROL Segment] | 共享一组通用属性并符合相关[!UICONTROL traits]资格的用户。 [!DNL Boolean] 表达式以及回访间隔/频度要求，允许您创建鉴 [!UICONTROL segment] 别规则。<br><br> 通过和规则的组合创建精确的 [!UICONTROL trait] 资格 [!UICONTROL segment] 要求。 | 从可用的[!UICONTROL traits]和[!UICONTROL signals]中，可以创建一个[!UICONTROL segment]规则，如下所示：`(product=camera AND type=digital SLR) OR (price>1000)` |

使用下图记住[!UICONTROL signals]、[!UICONTROL traits]和[!UICONTROL segments]之间关系的思想说明。

![](assets/signals-traits-segments.png)

**使用可 [!UICONTROL Traits] 视 [!UICONTROL Segment] 工具和代码编辑器构建和规则**

客户端在[!DNL Audience Manager]用户界面中使用可视化工具和代码编辑器管理[!UICONTROL traits]和[!UICONTROL segments]。 可视化工具允许您使用搜索功能、弹出选项、下拉菜单和拖放功能创建规则。 代码编辑器为高级用户提供了一种以编程方式制定受众分段标准的方法。

**事件调用将数据发送到[!DNL Audience Manager]**

事件调用会将数据从您的网站发送到[!DNL Audience Manager]。 调用包含[!DNL HTTP]请求中的[!UICONTROL signal]、[!UICONTROL trait]和[!UICONTROL segment]数据。 事件本身是[!DNL URL]字符串`/event`部分之后的所有内容。 如以下示例所示，此过程只需要一次事件调用即可将多个变量传递到[!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [区段：目的、构成和规则](../features/segments/segments-purpose.md)

