---
description: DART Enterprise(和其他目标类型)所要求的代码以捕获Audience Manager唯一用户ID(UUID)值。
seo-description: DART Enterprise(和其他目标类型)所要求的代码以捕获Audience Manager唯一用户ID(UUID)值。
seo-title: get_ aAmacookies代码
solution: Audience Manager
title: get_ aAmacookies代码
uuid: 89c30FE3-dobe6-4d18-b161-104167d75 bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` 代码 {#get-aamcookie-code}

Code required by [!DNL DART Enterprise] (and other destination types) to capture the Audience Manager unique user ID ([!DNL UUID]) value.

Define this function at the top of the page, ideally within the `<head>` code block.

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
