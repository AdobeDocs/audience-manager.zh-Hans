---
description: 从广告服务器检索特定值。
seo-description: 从广告服务器检索特定值。
seo-title: dexgetQsVars
solution: Audience Manager
title: dexgetQsVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# dexgetQsVars{#dexgetqsvars}

从广告服务器检索特定值。

**函数签名：**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `variableName` | 字符串 | 要获得值的变量的名称。 |
| `partner` | 字符串 | 要搜索的合作伙伴名称。 |
| `containerNSID` | 整数 | [!DNL NSID] 要搜索的容器。默认 `0`值为。 |

**响应**

返回 [!UICONTROL DIL] 实例的变量值。

**示例代码**

<pre class="java"><code>var value= DIL. dexgetQsVars('<i>variableName</i>'，'<i>parterName</i>'，<i>containernSID</i>)；</code></pre>
