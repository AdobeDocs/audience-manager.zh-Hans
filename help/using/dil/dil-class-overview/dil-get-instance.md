---
description: 检索特定于合作伙伴的DIL实例。
keywords: audience manager api;aam api;audience manager api;aam api
seo-description: 检索特定于合作伙伴的DIL实例。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL实施
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%

---

# getDil{#getdil}

检索特定于合作伙伴的DIL实例。

**函数签名：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 参数

| 名称 | 类型 | 描述 |
|---|---|---|
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | 默认值为`0`。 要搜索的容器的NSID。 可选。 |

## 响应

成功的合作伙伴和容器NSID匹配会返回特定于合作伙伴的[!UICONTROL DIL]实例。 如果没有匹配项，则API会返回（不引发）消息中出现“ `The DIL instance with partner <name> and containerNSID <ID> was not found.`”的错误

## 示例代码

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
