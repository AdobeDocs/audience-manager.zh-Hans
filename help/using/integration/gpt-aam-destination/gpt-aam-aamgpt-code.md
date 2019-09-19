---
description: AamGpt是一个JavaScript函数，它读取Audience Manager cookie数据，并将该信息发送到Google Publisher标记。
seo-description: AamGpt是一个JavaScript函数，它读取Audience Manager cookie数据，并将该信息发送到Google Publisher标记。
seo-title: Google Publisher标记的Audience Manager代码
solution: Audience Manager
title: Google Publisher标记的Audience Manager代码
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Google Publisher标记的Audience Manager代码 {#audience-manager-code-for-google-publisher-tags}

`AamGpt` 是读取 [!DNL JavaScript] Audience Manager cookie数据并将该信息发送到的函数 [!DNL Google Publisher Tags]。

>[!NOTE]
>
>如果您有自己的代码从和目标cookie中读取Audience Manager Cookie数据，则不需要此 [!UICONTROL UUID] 函数。

## 示例代码

将代 `AamGpt` 码放在页面顶部，最好放在代码 `<head>` 块中。 代 `AamGpt` 码如下所示：

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
