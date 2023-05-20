---
description: DART Enterprise （和其他目的地型別）擷取Audience Manager不重複使用者ID (UUID)值所需的代碼。
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie 代码
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 7%

---

# `get_aamCookie` 代码 {#get-aamcookie-code}

需要的程式碼 [!DNL DART Enterprise] （和其他目的地型別）來擷取Audience Manager的不重複使用者ID ([!DNL UUID])值。

在頁面頂端定義此函式，最好是在 `<head>` 程式碼區塊。

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
