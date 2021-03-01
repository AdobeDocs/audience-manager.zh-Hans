---
description: 介绍 Audience Manager 区段的组件、用于设置受众资格标准的表达式，以及如何在事件调用中传输数据。
landing-page-description: 介绍区段的组件、用于设置受众资格标准的表达式，以及数据传输方式。
seo-title: 信号、特征和区段
solution: Audience Manager
title: 信号、特征和区段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 参考
translation-type: tm+mt
source-git-commit: e6348c85e7df6428802d54b2c90385ce95f50e1a
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---


# [!UICONTROL Signals]、  [!UICONTROL Traits]and  [!UICONTROL Segments] {#signals-traits-and-segments}

描述[!DNL Audience Manager] [!UICONTROL segment]的组件、用于设置受众资格标准的表达式以及事件调用中数据传输的方式。

## 构图和用途

[!DNL Audience Manager] 数据包括 [!UICONTROL signals]、 [!UICONTROL traits]、 [!UICONTROL segments]以及相关资格规则。数据元素和规则组合在一起创建[!UICONTROL segments]。 [!UICONTROL Segments] 将站点访客组织到相关组中。下表定义了[!DNL Audience Manager] [!UICONTROL segment]中的三个主组件。

| 元素 | 包含 | 示例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是中最小的数据单 [!DNL Audience Manager] 位，表示 [为键值对](../reference/key-value-pairs-explained.md)。<br><br><ul><li>关键是定义数据集（如性别、颜色、价格）的常量。</li><li>该值是与常量相关的变量（例如，男/女、绿色、100）。</li></ul>比较运算符会加入键值对并设置它们之间的关系。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一个或多个[!UICONTROL signals]的组合。<br><br> [!DNL Boolean] 表达式和比较运算符允许您创建 [!UICONTROL trait] 资格规则。<br><br>通过组合和组创建精确的 [!UICONTROL traits] 资格 [!UICONTROL trait] 要求。 | 从可用的[!UICONTROL signals]中，可以创建表示为：`product=camera AND price>1000``High End Camera Browser` |
| [!UICONTROL Segment] | 共享一组常用属性并符合相关[!UICONTROL traits]条件的用户。 [!DNL Boolean] 表达式，以及最近/频率要求，允许您创建资 [!UICONTROL segment] 格规则。<br><br> 通过组合规则创建精确的资 [!UICONTROL trait] 格 [!UICONTROL segment] 要求。 | 在可用的[!UICONTROL traits]和[!UICONTROL signals]中，您可以创建一个表示为：`(product=camera AND type=digital SLR) OR (price>1000)`的[!UICONTROL segment]规则 |

请使用下图记住[!UICONTROL signals]、[!UICONTROL traits]和[!UICONTROL segments]之间关系。

![](assets/signals-traits-segments.png)

**使用可 [!UICONTROL Traits] 视工 [!UICONTROL Segment] 具和代码编辑器构建和规则**

客户端在[!DNL Audience Manager]用户界面中使用可视工具和代码编辑器管理[!UICONTROL traits]和[!UICONTROL segments]。 可视工具允许您使用搜索功能、弹出选项、下拉菜单和拖放功能创建规则。 代码编辑器为高级用户提供了一种有计划地开发受众分段标准的方法。

**事件调用将数据发送到[!DNL Audience Manager]**

事件调用将数据从您的网站发送到[!DNL Audience Manager]。 该调用包含[!DNL HTTP]请求中的[!UICONTROL signal]、[!UICONTROL trait]和[!UICONTROL segment]数据。 事件本身是[!DNL URL]字符串的`/event`部分之后的所有内容。 如下例所示，此过程只需要一个事件调用即可将多个变量传递到[!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [区段：目的、构成和规则](../features/segments/segments-purpose.md)

