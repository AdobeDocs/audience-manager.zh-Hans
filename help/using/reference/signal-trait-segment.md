---
description: 描述Audience Manager段的组件、用于设置受众资格标准的表达式，以及在事件呼叫中如何传输数据。
seo-description: 描述Audience Manager段的组件、用于设置受众资格标准的表达式，以及在事件呼叫中如何传输数据。
seo-title: 信号、特征和区段
solution: Audience Manager
title: 信号、特征和区段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 4%

---


# [!UICONTROL Signals]、 [!UICONTROL Traits]and [!UICONTROL Segments] {#signals-traits-and-segments}

描述表达式的组 [!DNL Audience Manager] 件、用 [!UICONTROL segment]于设置受众资格标准的，以及事件呼叫中如何传输数据。

## 构图和用途

[!DNL Audience Manager] 数据由、 [!UICONTROL signals]、 [!UICONTROL traits]和相关 [!UICONTROL segments]的资格规则组成。 数据元素和规则相结合以创建 [!UICONTROL segments]。 [!UICONTROL Segments] 将站点访客组织到相关组中。 下表定义了中的三个主体组 [!DNL Audience Manager] 件 [!UICONTROL segment]。

| 元素 | 由 | 示例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是中最小的数据单 [!DNL Audience Manager] 元，表示 [为键值对](../reference/key-value-pairs-explained.md)。<br><br><ul><li>关键是定义数据集（如性别、颜色、价格）的常数。</li><li>该值是与常数（例如，男／女、绿色、100）相关的变量。</li></ul>比较运算符连接键值对并设置它们之间的关系。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一个或多个组合 [!UICONTROL signals]。<br><br> [!DNL Boolean] 表达式和比较运算符允许您创建 [!UICONTROL trait] 资格规则。 <br><br>通过组合和组创建精确的 [!UICONTROL traits] 资格 [!UICONTROL trait] 要求。 | 您可以从 [!UICONTROL signals]可用内容创建 `High End Camera Browser` 以下表示的规则： `product=camera AND price>1000` |
| [!UICONTROL Segment] | 共享一组通用属性并符合相关资格的用户 [!UICONTROL traits]。 [!DNL Boolean] 表达式，以及最近／频率要求，允许您创建资格 [!UICONTROL segment] 规则。<br><br> 结合使用规则和规则，创建精确 [!UICONTROL trait] 的资 [!UICONTROL segment] 格要求。 | 在可用 [!UICONTROL traits] 和 [!UICONTROL signals]中，您可以创建 [!UICONTROL segment] 表示为：`(product=camera AND type=digital SLR) OR (price>1000)` |

使用下图记住、和之间 [!UICONTROL signals]的 [!UICONTROL traits]关系 [!UICONTROL segments]。

![](assets/signals-traits-segments.png)

**使用可[!UICONTROL Traits]视工[!UICONTROL Segment]具和代码编辑器构建和规则**

客户端在 [!UICONTROL traits] 用 [!UICONTROL segments] 户界面中使用可视工具和代码编辑器 [!DNL Audience Manager] 进行管理。 可视化工具允许您使用搜索功能、弹出选项、下拉菜单和拖放功能创建规则。 代码编辑器为高级用户提供了一种有序开发受众分段标准的方法。

**事件调用将数据发送到[!DNL Audience Manager]**

事件调用将数据从您的网站发送到 [!DNL Audience Manager]。 调用包含 [!UICONTROL signal]请求 [!UICONTROL trait]中的 [!UICONTROL segment] 、和数 [!DNL HTTP] 据。 事件本身是字符串 `/event` 之后的一 [!DNL URL] 切。 如以下示例所示，此过程只需一个事件调用即可将多个变量传递给 [!DNL Audience Manager]。

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [区段：目的、构成和规则](../features/segments/segments-purpose.md)

