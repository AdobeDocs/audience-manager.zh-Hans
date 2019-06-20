---
description: 检索特定于合作伙伴的DIL实例。
keywords: 受众经理api；aam api；受众经理API；aam apis
seo-description: 检索特定于合作伙伴的DIL实例。
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6 b9-d6 b38513 d487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

检索特定于合作伙伴的DIL实例。

**函数签名：**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 参数

| 名称 | 类型 | 描述 |
|---|---|---|
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | Defaults is `0`. 要搜索的容器的NSID。可选。 |

## 响应

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## 示例代码

<pre class="java"><code>DIL. getDil('<i>合作伙伴</i>'、 <i>containernSID</i>)；
DIL. getDil('<i>合作伙伴</i>')；</code>
</pre>
