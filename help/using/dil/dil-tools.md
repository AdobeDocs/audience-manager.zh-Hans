---
description: 描述DIL.tools命名空间中的方法。 这些实用程序功能可帮助您执行特定任务。
seo-description: 描述DIL.tools命名空间中的方法。 这些实用程序功能可帮助您执行特定任务。
seo-title: DIL 工具
solution: Audience Manager
title: DIL 工具
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL实施
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 5%

---

# DIL 工具

描述`DIL.tools`命名空间中的方法。 这些实用程序功能可帮助您执行特定任务。

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

返回用于访问当前页面的搜索词。

<!-- 

r_dil_get_search_referrer.xml

 -->

### `getSearchReferrer`的用途

在DIL中，`getSearchReferrer`返回用于访问您的网站的搜索结果（名称和关键词）。 默认情况下，您可以将特定搜索词传递到此函数，或者允许其针对`document.referrer`搜索支持的搜索引擎（[!DNL AOL]、[!DNL Ask]、[!DNL Bing]、[!DNL Google]和[!DNL Yahoo]）。

### 函数签名

函数签名：`DIL.tools.getSearchReferrer(uri, initConfig)`

### 函数参数

`getSearchReferrer` 接受：

* *`{string}`*: *（可选）* 包含搜索URL的字符串(如果未定义， `document.referrer` 则使用)。
* *`{object}`*: *（可选）* 包含、或配置 `hostPattern`的 `queryParam`对象 `queryPattern`。

和返回：

* `{object}` 包含有效名称和关键字的对象。

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
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>在自定义URL中传递</td> 
   <td>根据自定义URL返回搜索反向链接。</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>将URL主机名与自定义正则表达式匹配</b></td> 
   <td> 在自定义正则表达式中传递，以匹配引荐URL的主机名。 </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>使用自定义正则表达式匹配搜索模式</b> </td> 
   <td> 在自定义正则表达式中传递以执行自定义搜索。 </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

将统一资源标识符([!DNL URI])分解为其组成组件：`hash`、`host`、`href`、`pathname`、`protocol`、`search`和`[!DNL uriParams]`。

<!-- 

r_dil_decompose.xml

 -->

函数签名：`DIL.tools.decomposeURI`

### 函数参数

`decomposeURI` 接受：

* *`uri {string}`*: *（可选）* 包含URI的字符串。如果未指定，则默认为`document.location.href`。

和返回：

* *`{object}`*:包含有效名称和关键字的对象。

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

## getMetaTags

搜索在网页的元标记中定义的特定内容，并在对象中返回该数据。

<!-- 

r_dil_get_metatags.xml

 -->

### 函数签名

函数签名：`DIL.tools.getMetaTags( 1 or more parameters)`

### 函数参数

`getMetaTags` 接受要搜索的一个或多个名称参数（字符串类型）。它返回由键值对组成的对象。

### 示例代码

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
