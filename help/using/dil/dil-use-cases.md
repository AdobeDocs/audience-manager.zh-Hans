---
description: 针对特定DIL用例的代码示例和描述。
seo-description: 针对特定DIL用例的代码示例和描述。
seo-title: DIL使用案例和代码示例
solution: Audience Manager
title: DIL使用案例和代码示例
uuid: 27995c2d-652-438e-af99-b5477 f090 ae9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

针对特定DIL用例的代码示例和描述。

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

创建一个对象变量，它将有关页面元素的信息发送到Audience Manager。这对于一般数据收集或作为Analytics变量收集数据的替代方法很有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**描述**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. 这些示例使用变量容纳平面列表或数组中的数据元素。Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**保持值属性一致**

在传入数据时，请记住保持值属性相同。例如，如果您有两个值不同的相同键，则最后一个键-值对的值优先于前面的值对象。For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**示例1：将数据作为关键值对发送**

此基本示例以关键值对的形式向Audience Manager发送颜色和价格数据。您的代码可能类似于以下内容：

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
sample_ dil. api.信号({
c_ color：“blue”，
c_ price：“900”})；
sample_ dil. api. mit()；</code>
</pre>

**示例2：在对象中发送数据**

此高级示例演示如何将对象中的数据发送到Audience Manager。When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] 您的代码可能类似于以下内容：

<pre class="java"><code>var my_ object={
颜色：“blue”，
价格：“900”}；

var sample_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
//Load对象并将“c_”追加到键值对中的所有键，并将数据发送到AudienceManager。 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**示例3：在数组中发送页面数据**

In this case, the variable `my_object` uses an array to hold data. 此示例基于以上建议方法传递的信息，但添加额外层以适应产品类型和模型。您的代码可能类似于以下内容：

<pre class="java"><code>var my_ objects=[{
颜色：“blue”，
价格：“900”}，{
类型：“acura”，
模型：“tl”}]；

var sample_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；

for(var i=0；i&lt; my_ objects. length；i++)//Load对象并将“c_”追加到键值对中的所有键。 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_ LIKE_ This]
>
>* [信号](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

捕获引用URL并将其发送到Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>此方法仅在用户使用类似协议(HTTP与HTTPS)之间移动时才有效。例如，当您从安全站点导航到另一个安全站点时，浏览器会保留引用URL。在安全和不安全站点之间移动时，浏览器不会保留引用URL。This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**代码示例**

您的代码可能类似于以下内容：

<pre class="java"><code>var adobe_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
adobe_ dil. api.信号({d_ referer：document. referrer}). mit()；</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

将有关搜索引擎类型和关键字搜索的信息发送至Audience Manager。

<!-- 

c_dil_search_engine_valid.xml

 -->

**支持的搜索引擎**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**描述**

以下代码演示了如何获取任何支持的搜索引擎的搜索引介。In this case, let's assume a user searched on the term "homes" from [!DNL Google] Canada ( `www.google.ca`). 此代码将帮助您捕获这些搜索词并将其发送到Audience Manager。

**基本代码**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜索引擎代码示例**

In this case, let's assume that a user searched for the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` 是 [一个必需前缀](../features/traits/trait-variable-prefixes.md) ，它将客户定义的变量识别为Audience Manager。

<pre class="java"><code>var adobe_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
var search_ referrer= DIL. tools. getInstanceReader()；

if(search_ referrer&amp;&amp; search_ referrer. valid){
adobe_ dil. api.信号({
c_ se：se. name，
c_ st：se. keywords
}). mit()；
}}</code>
</pre>

**未列出的搜索引擎代码示例**

In this case, let's assume that a user searched for the term "homes" from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. 您的代码可能类似于以下内容：

<pre class="java"><code>var adobe_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
var search_ referrer= DIL. tools. getInstanceReader(document. referrer，{
HostPattern：/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

将值从键值对关联到另一个键。

<!-- 

c_dil_map_keys.xml

 -->

**描述**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. 客户定义的数据用于定位在事件调用中传入数据的特定站点。但是，有时您希望此信息在Audience Manager帐户中的所有属性中可用。To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

例如，您可以从特定站点收集ZIP代码数据，但要将其定向到所有Audience Manager属性。To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**代码示例**

您的代码可能类似于以下内容：

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_ LIKE_ This]
>
>* [关键变量的前缀要求](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

设置并使用GTM标签提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. 创建新容器或打开现有容器。
1. 向容器添加新标记。
1. 打开标记以对其进行编辑，然后：

   * 命名标记。
   * **[!UICONTROL Custom HTML Tag]** 从 **[!UICONTROL Tag Type]** 下拉列表中进行选择。
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * 单击 **[!UICONTROL Save]**.

1. 发布容器。
1. 生成容器标签代码并将其放置在库存上。

>[!MORE_ LIKE_ This]
>
>* [Google Tag Manager帮助中心](https://support.google.com/tagmanager#topic=3441530)

