---
description: 擷取合作夥伴特定的DIL例項。
keywords: audience manager api；aam api；audience manager api；aam api
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 15%

---

# getDil{#getdil}

擷取合作夥伴特定的DIL例項。

**函式簽章：** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 参数

| 名称 | 类型 | 描述 |
|---|---|---|
| `partner` | 字符串 | 要搜尋的合作夥伴名稱。 |
| `containerNSID` | 整数 | 預設值為 `0`. 您要搜尋之容器的NSID。 可选。 |

## 响应

成功的合作夥伴和容器NSID相符專案會傳回特定於合作夥伴的專案 [!UICONTROL DIL] 執行個體。 如果沒有相符專案，API會傳回（不會擲回）錯誤訊息， 」 `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## 示例代码

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
