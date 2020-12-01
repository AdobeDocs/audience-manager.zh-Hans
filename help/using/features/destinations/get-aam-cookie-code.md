---
description: DART Enterprise（和其他目标类型）需要的代码，用于捕获Audience Manager唯一用户ID(UUID)值。
seo-description: DART Enterprise（和其他目标类型）需要的代码，用于捕获Audience Manager唯一用户ID(UUID)值。
seo-title: get_aamCookie 代码
solution: Audience Manager
title: get_aamCookie 代码
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 9%

---


# `get_aamCookie` 代码 {#get-aamcookie-code}

[!DNL DART Enterprise]（和其他目标类型）需要的代码，用于捕获Audience Manager唯一用户ID([!DNL UUID])值。

在页面顶部定义此函数，最好在`<head>`代码块中。

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
