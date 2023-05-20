---
description: 說明DIL.tools名稱空間中的方法。 这些实用函数可帮助您执行特定的任务。
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL 工具
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 5%

---

# DIL 工具

說明中的方法 `DIL.tools` 名稱空間。 這些公用程式功能可協助您執行特定工作。

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

返回用于访问当前页面搜索术语。

<!-- 

r_dil_get_search_referrer.xml

 -->

### 目的 `getSearchReferrer`

在 DIL 中， `getSearchReferrer` 返回用于访问您网站的搜索结果（名称和关键词）。 您可以将特定搜索术语传递到此函数，或让其搜索受支持的搜索引擎（ [!DNL AOL] 、 [!DNL Google] [!DNL Ask] [!DNL Bing] 、、、和 [!DNL Yahoo] ）。 `document.referrer`

### 函数签名

函数签名： `DIL.tools.getSearchReferrer(uri, initConfig)`

### 函数参数

`getSearchReferrer` 接受：

* *`{string}`*： *（可選）* 包含搜尋URL的字串(使用 `document.referrer` （如果未定義）。
* *`{object}`*： *（可選）* 一個物件，其中包含下列專案的設定： `hostPattern`， `queryParam`，或 `queryPattern`.

并返回：

* `{object}` 包含有效名称和关键词的对象。

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
   <td> 默认 Search</td> 
   <td> 返回 AOL、Ask、Bing、Google 和 Yahoo 搜索引擎使用关键词搜索术语。 </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>傳入自訂URL</td> 
   <td>根據自訂URL傳回搜尋反向連結。</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>比對URL主機名稱與自訂規則運算式</b></td> 
   <td> 传入自定义 regex 以匹配反向链接 URL 的主机名称。 </td> 
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
   <td> <b>将 Search 模式与自定义 Regex 匹配</b> </td> 
   <td> 传入自定义 regex 以执行自定义搜索。 </td> 
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

将一致资源标识符（ [!DNL URI] ）分解为其构成组件： `hash` 、 `host` 、 `href` `search` `pathname` `protocol` 、、、和。 `[!DNL uriParams]`

<!-- 

r_dil_decompose.xml

 -->

函数签名： `DIL.tools.decomposeURI`

### 函数参数

`decomposeURI` 接受：

* *`uri {string}`*： *（可選）* 包含URI的字串。 預設為 `document.location.href` 若未指定。

並傳回：

* *`{object}`*：包含有效名稱和關鍵字的物件。

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

搜索在网页的 meta 标记中定义的特定内容，并返回对象中的数据。

<!-- 

r_dil_get_metatags.xml

 -->

### 函数签名

函数签名： `DIL.tools.getMetaTags( 1 or more parameters)`

### 函数参数

`getMetaTags` 接受要搜尋的一或多個名稱引數（字串型別）。 它會傳回由索引鍵值配對組成的物件。

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
