---
description: AamGpt是一个JavaScript函数，用于读取Audience ManagerCookie数据，并将该信息发送到Google Publisher Tags。
seo-description: AamGpt是一个JavaScript函数，用于读取Audience ManagerCookie数据，并将该信息发送到Google Publisher Tags。
seo-title: Google Publisher Tag 的 Audience Manager 代码
solution: Audience Manager
title: Google Publisher Tag 的 Audience Manager 代码
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: 第三方集成
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 19%

---

# Google Publisher Tag 的 Audience Manager 代码 {#audience-manager-code-for-google-publisher-tags}

`AamGpt` 是一个 [!DNL JavaScript] 函数，用于读取Audience Managercookie数据并将该信息发送 [!DNL Google Publisher Tags]到。

>[!NOTE]
>
>如果您有自己的代码从[!UICONTROL UUID]和目标Cookie中读取Audience ManagerCookie数据，则不需要此函数。

## 示例代码

将`AamGpt`代码放在页面顶部，最好放在`<head>`代码块中。 `AamGpt`代码在下面提供：

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
