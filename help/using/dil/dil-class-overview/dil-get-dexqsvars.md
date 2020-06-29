---
description: 从广告服务器检索特定值。
seo-description: 从广告服务器检索特定值。
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 17%

---


# dexGetQSVars{#dexgetqsvars}

从广告服务器检索特定值。

**函数签名：** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `variableName` | 字符串 | 要获取值的变量的名称。 |
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | 你 [!DNL NSID] 正在搜索的容器。 默认值 `0`为。 |

**响应**

返回实例的变 [!UICONTROL DIL] 量值。

**示例代码**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
