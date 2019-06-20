---
description: 介绍DIL. tools命名空间中的方法。这些实用程序功能帮助您执行特定任务。
seo-description: 介绍DIL. tools命名空间中的方法。这些实用程序功能帮助您执行特定任务。
seo-title: DIL工具
solution: Audience Manager
title: DIL工具
uuid: bc62ce2-16bd-4e80-b493-c816 ba643 b59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# DIL工具

Describes methods in the `DIL.tools` namespace. 这些实用程序功能帮助您执行特定任务。

<!-- 

c_dil_functions.xml

 -->

## getInstanceReferrer

返回用于到达当前页面的搜索词。

<!-- 

r_dil_get_search_referrer.xml

 -->

### Purpose of `getSearchReferrer`

In DIL, `getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo]) against `document.referrer` by default.

### 函数签名

Function signature: `DIL.tools.getSearchReferrer(uri, initConfig)`

### 函数参数

`getSearchReferrer` 接受：

* *`{string}`*： *(可选)* 包含搜索URL的字符串( `document.referrer` 如果未定义)。
* *`{object}`*： *(可选)* 包含 `hostPattern`、 `queryParam`或 `queryPattern`.

并返回：

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
   <td> 返回AOL、Ask、Bing、Google和Yahoo搜索引擎使用的关键字搜索词。 </td> 
   <td>
      <code>var&amp; amp；nbsp；results&amp; amp；nbsp；=&amp; amp；nbsp；DIL. tools. getInstallReferrer()；</code> 
  </td>
  </tr> 
  <tr> 
   <td>传入自定义URL</td> 
   <td>返回基于自定义URL的搜索引介。</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>与自定义正则表达式匹配URL主机名</b></td> 
   <td> 传入自定义正则表达式以匹配引用URL的主机名。 </td> 
   <td> 
  <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/
    search.aspx?q=adobe+rules",{ 
       hostPattern:/ehow\./, 
         queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>使用自定义正则表达式匹配搜索模式</b> </td> 
   <td> 传入自定义正则表达式以执行自定义搜索。 </td> 
   <td> 
    <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
    {
       hostPattern:/ehow\./, 
           search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## 解压缩功能

Disassembles a Uniform Resource Identifier ( [!DNL URI]) into its constituent components: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, and `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Function signature: `DIL.tools.decomposeURI`

### 函数参数

`decomposeURI` 接受：

* *`uri {string}`*： *(可选)* 包含URI的字符串。Defaults to `document.location.href` if not specified.

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

## getMetaGames

搜索网页上的meta标记中定义的特定内容，并在对象中返回该数据。

<!-- 

r_dil_get_metatags.xml

 -->

### 函数签名

Function signature: `DIL.tools.getMetaTags( 1 or more parameters)`

### 函数参数

`getMetaTags` 接受一个或多个名称参数(字符串类型)以进行搜索。它返回由键值对组成的对象。

### 示例代码

<pre class="&ldquo;javascript&rdquo;"><code>var datalb= DIL. create({
合作伙伴：“<i>parterName</i>”，
containernSite： <i>containernSID</i> })；
DataLibb. api.信号(DIL. tools. getMetaGs('<i>application</i>'，'<i>keywords</i>'，'<i>description</i>')，'c_'). mit()；</code>
</pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
