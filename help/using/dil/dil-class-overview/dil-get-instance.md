---
description: 检索特定于合作伙伴的DIL实例。
keywords: audience manager api；aam api；audience manager api；aam api
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 6%

---

# getDil{#getdil}

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此点之后不会开发[!DNL DIL]。 建议客户评估[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)。

检索特定于合作伙伴的DIL实例。

**函数签名：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 参数

| 名称 | 类型 | 描述 |
|---|---|---|
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | 默认值为`0`。 要搜索的容器的NSID。 可选。 |

## 响应

成功的伙伴和容器NSID匹配将返回特定于伙伴的[!UICONTROL DIL]实例。 如果没有匹配项，则API会返回（不丢弃）错误消息“ `The DIL instance with partner <name> and containerNSID <ID> was not found.`”

## 示例代码

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
