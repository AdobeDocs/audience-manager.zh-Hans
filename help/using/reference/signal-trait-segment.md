---
description: 了解区段的组成以及用于设置受众资格标准的表达式。还可以了解有关数据传输方式的信息。
landing-page-description: 了解区段的组成以及用于设置受众资格标准的表达式。还可以了解有关数据传输方式的信息。
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: 信号、特征和区段
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 16%

---

# [!UICONTROL Signals], [!UICONTROL Traits]和 [!UICONTROL Segments] {#signals-traits-and-segments}

描述 [!DNL Audience Manager] [!UICONTROL segment]、用于设置受众资格标准的表达式，以及如何在事件调用中传输数据。

## 构成和用途

[!DNL Audience Manager] 数据由 [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]，以及相关资格规则。 数据元素和规则可组合在一起创建 [!UICONTROL segments]. [!UICONTROL Segments] 将网站访客组织到相关组中。 下表定义了 [!DNL Audience Manager] [!UICONTROL segment].

| 元素 | 包含 | 示例 |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] 是 [!DNL Audience Manager] 表示为 [键值对](../reference/key-value-pairs-explained.md).<br><br><ul><li>键是用于定义数据集（例如，性别、颜色、价格）的常量。</li><li>该值是与常量相关的变量（例如，男/女、绿色、100）。</li></ul>比较运算符连接键值对并设置它们之间的关系。 | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | 一个或多个组合 [!UICONTROL signals].<br><br> [!DNL Boolean] 表达式和比较运算符允许您创建 [!UICONTROL trait] 资格规则。 <br><br>通过 [!UICONTROL traits] 和 [!UICONTROL trait] 群组。 | 从可用 [!UICONTROL signals]，您可以创建 `High End Camera Browser` 规则表示为： `product=camera AND price>1000` |
| [!UICONTROL Segment] | 共享一组通用属性并符合相关资格的用户 [!UICONTROL traits]. [!DNL Boolean] 表达式和回访间隔/频度要求允许您创建 [!UICONTROL segment] 资格规则。<br><br> 通过 [!UICONTROL trait] 和 [!UICONTROL segment] 规则。 | 从可用 [!UICONTROL traits] 和 [!UICONTROL signals]，您可以创建 [!UICONTROL segment] 规则表示为：`(product=camera AND type=digital SLR) OR (price>1000)` |

使用下图，在脑中记下 [!UICONTROL signals], [!UICONTROL traits]和 [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**生成 [!UICONTROL Traits] 和 [!UICONTROL Segment] 使用可视化工具和代码编辑器的规则**

客户端管理 [!UICONTROL traits] 和 [!UICONTROL segments] 和代码编辑器 [!DNL Audience Manager] 用户界面。 可视化工具允许您使用搜索功能、弹出选项、下拉菜单和拖放功能创建规则。 代码编辑器为高级用户提供了一种以编程方式制定受众分段标准的方法。

**事件调用将数据发送到[!DNL Audience Manager]**

事件调用会将数据从您的网站发送到 [!DNL Audience Manager]. 调用包含 [!UICONTROL signal], [!UICONTROL trait]和 [!UICONTROL segment] 数据 [!DNL HTTP] 请求。 活动本身就是 `/event` 部分 [!DNL URL] 字符串。 如以下示例所示，此过程只需一个事件调用即可将多个变量传递到 [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [区段：目的、构成和规则](../features/segments/segments-purpose.md)

