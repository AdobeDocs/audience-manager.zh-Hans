---
description: 检索特定于合作伙伴的DIL实例。
keywords: 受众经理api；aam api；受众经理API；aam apis
seo-description: 检索特定于合作伙伴的DIL实例。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6 b9-d6 b38513 d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

检索特定于合作伙伴的DIL实例。

**函数签名：**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 参数

| 名称 | 类型 | 描述 |
|---|---|---|
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | 默认 `0`值为。要搜索的容器的NSID。可选。 |

## 响应

成功的合作伙伴和容器NSID匹配返回合作伙伴特定 [!UICONTROL DIL] 实例。如果没有匹配项，API会返回(不会抛出)包含消息的错误”`The DIL instance with partner <name> and containerNSID <ID> was not found.`

## 示例代码

<pre class="java"><code>DIL. getDil('<i>合作伙伴</i>'、 <i>containernSID</i>)；
DIL. getDil('<i>合作伙伴</i>')；</code></pre>
