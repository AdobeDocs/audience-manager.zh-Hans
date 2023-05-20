---
description: 從廣告伺服器擷取特定值。
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 18%

---

# dexGetQSVars{#dexgetqsvars}

從廣告伺服器擷取特定值。

**函式簽章：** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `variableName` | 字符串 | 您要為其取得值的變數名稱。 |
| `partner` | 字符串 | 要搜尋的合作夥伴名稱。 |
| `containerNSID` | 整数 | 此 [!DNL NSID] 您正在搜尋的容器。 預設值為 `0`. |

**响应**

傳回 [!UICONTROL DIL] 執行個體。

**示例代码**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
