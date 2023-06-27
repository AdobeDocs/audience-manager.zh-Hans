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
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%

---

# getDil{#getdil}

>[!WARNING]
>
>自2023年7月起，Adobe已停止开发电子烟产品。 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 扩展。
><br><br>
>现有客户可以继续使用其 [!DNL DIL] 实现。 但是，Adobe将不会开发 [!DNL DIL] 超越了这一点。 建议客户评估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 长期数据收集策略。
><br><br>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而是。

检索特定于合作伙伴的DIL实例。

**函数签名：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 参数

| 名称 | 类型 | 描述 |
|---|---|---|
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | 默认为 `0`. 正在搜索的容器的NSID。 可选。 |

## 响应

成功的伙伴和容器NSID匹配将返回特定于伙伴的匹配 [!UICONTROL DIL] 实例。 如果没有匹配项，则API会返回（不引发）包含消息“ ”的错误 `The DIL instance with partner <name> and containerNSID <ID> was not found.`”

## 示例代码

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
