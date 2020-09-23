---
description: DART Enterprise（和其他目标类型）需要的代码，用于捕获Audience Manager唯一用户ID(UUID)值。
seo-description: DART Enterprise（和其他目标类型）需要的代码，用于捕获Audience Manager唯一用户ID(UUID)值。
seo-title: get_aamCookie 代码
solution: Audience Manager
title: get_aamCookie 代码
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 7d0735fa9620b7765db7be8d3a7c8731536ffd32
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 11%

---


# get_aamCookie 代码 {#get-aamcookie-code}

捕获Audience Manager唯 [!DNL DART Enterprise] 一用户ID()值所需的代码(和其[!DNL UUID]他目标类型)。

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
