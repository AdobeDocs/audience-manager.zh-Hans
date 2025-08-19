---
description: 介绍DIL.tools命名空间中的方法。 这些实用程序功能可帮助您执行特定任务。
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---

# DIL Tools

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此之后不会开发[!DNL DIL]。 建议客户评估[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)。

描述`DIL.tools`命名空间中的方法。 这些实用程序功能可帮助您执行特定任务。

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

返回用于访问当前页面的搜索词。

<!-- 

r_dil_get_search_referrer.xml

 -->

### `getSearchReferrer`的目的

在DIL中，`getSearchReferrer`返回用于访问您的网站的搜索结果（名称和关键字）。 您可以将特定搜索词传递到此函数，或者让此函数默认针对[!DNL AOL]搜索支持的搜索引擎（[!DNL Ask]、[!DNL Bing]、[!DNL Google]、[!DNL Yahoo]和`document.referrer`）。

### 函数签名

函数签名： `DIL.tools.getSearchReferrer(uri, initConfig)`

### 函数参数

`getSearchReferrer`接受：

* *`{string}`*： *（可选）*&#x200B;包含搜索URL的字符串（如果未定义，则使用`document.referrer`）。
* *`{object}`*： *（可选）*&#x200B;包含`hostPattern`、`queryParam`或`queryPattern`配置的对象。

并返回：

* `{object}`包含有效名称和关键字的对象。

### 示例

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> 搜索类型 </th> 
   <th> 描述 </th> 
   <th> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 默认搜索</td> 
   <td> 返回AOL、Ask、Bing、Google和Yahoo搜索引擎使用的关键词搜索词。 </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>传入自定义URL</td> 
   <td>基于自定义URL返回搜索反向链接。</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>将URL主机名与自定义正则表达式匹配</b></td> 
   <td> 传入自定义正则表达式以匹配反向链接URL的主机名。 </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>将搜索模式与自定义正则表达式匹配</b> </td> 
   <td> 传入自定义正则表达式以执行自定义搜索。 </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

将统一资源标识符([!DNL URI])分解到其组成组件中： `hash`、`host`、`href`、`pathname`、`protocol`、`search`和`[!DNL uriParams]`。

<!-- 

r_dil_decompose.xml

 -->

函数签名： `DIL.tools.decomposeURI`

### 函数参数

`decomposeURI`接受：

* *`uri {string}`*： *（可选）*&#x200B;包含URI的字符串。 如果未指定，则默认为`document.location.href`。

并返回：

* *`{object}`*：包含有效名称和关键字的对象。

### 示例代码


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTag

搜索网页上的元标记中定义的特定内容，并在对象中返回该数据。

<!-- 

r_dil_get_metatags.xml

 -->

### 函数签名

函数签名： `DIL.tools.getMetaTags( 1 or more parameters)`

### 函数参数

`getMetaTags`接受要搜索的一个或多个名称参数（字符串类型）。 它会返回一个由键值对组成的对象。

### 示例代码

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
