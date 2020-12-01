---
description: 检索特定于合作伙伴的DIL实例。
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: 检索特定于合作伙伴的DIL实例。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 17%

---


# getDil{#getdil}

检索特定于合作伙伴的DIL实例。

**函数签名：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 参数

| 名称 | 类型 | 描述 |
|---|---|---|
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | 默认值为`0`。 您正在搜索的容器的NSID。 可选。 |

## 响应

成功的合作伙伴和容器NSID匹配返回特定于合作伙伴的[!UICONTROL DIL]实例。 如果没有匹配项，则API返回（不抛出）消息“ `The DIL instance with partner <name> and containerNSID <ID> was not found.`”的错误

## 示例代码

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
