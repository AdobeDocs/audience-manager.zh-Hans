---
description: 从广告服务器检索特定值。
seo-description: 从广告服务器检索特定值。
seo-title: dexgetQsVars
solution: Audience Manager
title: dexgetQsVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# dexGetQSVars{#dexgetqsvars}

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
| `containerNSID` | 整数 | [!DNL NSID] 要搜索的容器。Defaults is `0`. |

**响应**

Returns the variable value for a [!UICONTROL DIL] instance.

**示例代码**

<pre class="java"><code>var value= DIL. dexgetQsVars('<i>variableName</i>'，'<i>parterName</i>'，<i>containernSID</i>)；</code>
</pre>
