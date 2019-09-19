---
description: DART Enterprise（和其他目标类型）捕获Audience Manager唯一用户ID(UUID)值所需的代码。
seo-description: DART Enterprise（和其他目标类型）捕获Audience Manager唯一用户ID(UUID)值所需的代码。
seo-title: get_aamCookie代码
solution: Audience Manager
title: get_aamCookie代码
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` 代码 {#get-aamcookie-code}

捕获Audience Manager唯 [!DNL DART Enterprise] 一用户ID()值所需的代码(和其他目标类[!DNL UUID]型)。

在页面顶部定义此函数，最好在代码块 `<head>` 中定义。

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
