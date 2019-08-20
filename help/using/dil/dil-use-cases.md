---
description: 针对特定DIL用例的代码示例和描述。
seo-description: 针对特定DIL用例的代码示例和描述。
seo-title: DIL使用案例和代码示例
solution: Audience Manager
title: DIL使用案例和代码示例
uuid: 27995c2d-652-438e-af99-b5477 f090 ae9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# DIL使用案例和代码示例{#dil-use-cases-and-code-samples}

针对特定DIL用例的代码示例和描述。

<!-- 

c_dil_use_case.xml

 -->

## 使用DIL将数据元素发送到Audience Manager {#send-data-elements-dil}

创建一个对象变量，它将有关页面元素的信息发送到Audience Manager。这对于一般数据收集或作为Analytics变量收集数据的替代方法很有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**描述**

以下代码演示如何收集页面数据并将其发送到Audience Manager [!UICONTROL DIL]。这些示例使用变量容纳平面列表或数组中的数据元素。记住，将变量作为 [关键值对传递](../reference/key-value-pairs-explained.md)。另外，在键值对中的键之前注意 `c_` 前缀。此 [必需前缀](../features/traits/trait-variable-prefixes.md) 将信息标识为用户定义的数据。在第一个示例中，您需要手动附加 `c_` 到密钥。在第二个示例中，自动为您 [!UICONTROL DIL] 执行此操作。

**保持值属性一致**

在传入数据时，请记住保持值属性相同。例如，如果您有两个值不同的相同键，则最后一个键-值对的值优先于前面的值对象。例如，传入并 `color:blue``color:red` 将返回的值设置为红色(覆盖蓝色)。

**示例1：将数据作为关键值对发送**

此基本示例以关键值对的形式向Audience Manager发送颜色和价格数据。您的代码可能类似于以下内容：

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
sample_ dil. api.信号({
c_ color：“blue”，
c_ price：“900”})；
sample_ dil. api. mit()；</code>
</pre>

**示例2：在对象中发送数据**

此高级示例演示如何将对象中的数据发送到Audience Manager。使用此方法时， [!UICONTROL DIL] 允许您将对象作为函数参数传递到 [!DNL signals()] 方法中。[!UICONTROL DIL] 您的代码可能类似于以下内容：

<pre class="java"><code>var my_ object={
颜色：“blue”，
价格：“900”}；

var sample_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
//Load对象并将“c_”追加到键值对中的所有键，并将数据发送到AudienceManager。 
sample_ dil. api.信号(my_ object，“c_”). mit()；</code>
</pre>

**示例3：在数组中发送页面数据**

在这种情况下，变量 `my_object` 使用数组保存数据。此示例基于以上建议方法传递的信息，但添加额外层以适应产品类型和模型。您的代码可能类似于以下内容：

<pre class="java"><code>var my_ objects=[{
颜色：“blue”，
价格：“900”}，{
类型：“acura”，
模型：“tl”}]；

var sample_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；

for(var i=0；i&lt; my_ objects. length；i++)//Load对象并将“c_”追加到键值对中的所有键。 
{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{{
sample_ dil. api.信号(my_ objects[i]，“c_”)；
} 
sample_ dil. api. mit()；</code>
</pre>

>[!MORE_ LIKE_ This]
>
>* [信号](../dil/dil-instance-methods.md#signals)


## 捕获引用URL {#capture-referring-url}

捕获引用URL并将其发送到Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>此方法仅在用户使用类似协议(HTTP与HTTPS)之间移动时才有效。例如，当您从安全站点导航到另一个安全站点时，浏览器会保留引用URL。在安全和不安全站点之间移动时，浏览器不会保留引用URL。此行为是正常的浏览器功能，不能被规避 [!UICONTROL DIL]。

**代码示例**

您的代码可能类似于以下内容：

<pre class="java"><code>var adobe_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
adobe_ dil. api.信号({d_ referer：document. referrer}). mit()；</code>
</pre>

## 捕获搜索引擎类型和关键字搜索词 {#capture-search-engine-types}

将有关搜索引擎类型和关键字搜索的信息发送至Audience Manager。

>[!IMPORTANT]
>
>本节介绍旧版功能，该功能在DIL的最新版本中不受支持。

**支持的搜索引擎**

默认 `DIL.getSearchReferrer` 情况下，识别来自这些搜索引擎的搜索(包括国际变量)：

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**描述**

以下代码演示了如何获取任何支持的搜索引擎的搜索引介。在这种情况下，假设用户在 [!DNL Google] 加拿大( `www.google.ca`)的术语“家”中搜索。此代码将帮助您捕获这些搜索词并将其发送到Audience Manager。

**基本代码**

获取搜索参照文件(例如，从中 `google.com`获取)的基本代码如下：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜索引擎代码示例**

在这种情况下，假设用户从 [!DNL Google] 加拿大( `www.google.ca`)搜索术语“home”。注意代码如何将所需 `c_` 参数前缀为搜索引擎( `c_se`)和搜索词( `c_st`)。`c_` 是 [一个必需前缀](../features/traits/trait-variable-prefixes.md) ，它将客户定义的变量识别为Audience Manager。

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

在这种情况下，假设用户搜索“主页” `dogpile.com`。由于 [!DNL Dogpile] 默认不支持，您可以配置DIL以识别此搜索引擎，并将搜索词返回Audience Manager。您的代码可能类似于以下内容：

<pre class="java"><code>var adobe_ dil= DIL. create({合作伙伴：“<i>合作伙伴名称</i>”})；
var search_ referrer= DIL. tools. getInstanceReader(document. referrer，{
HostPattern：/dogpile\./，
QueryParam：“q”})；

if(search_ referrer&amp;&amp; search_ referrer. valid){
adobe_ dil. api.信号({
c_ se：se. name，
c_ st：se. keywords
}). mit()；
}}</code>
</pre>

## 将键值映射到其他键 {#map-key-values}

将值从键值对关联到另一个键。

<!-- 

c_dil_map_keys.xml

 -->

**描述**

在键值对中，附加到键的 `c_` 前缀将标识为客户定义的数据。客户定义的数据用于定位在事件调用中传入数据的特定站点。但是，有时您希望此信息在Audience Manager帐户中的所有属性中可用。为此，请将 `c_` 键值对中的值映射到平台级别键。平台级别密钥已预先修复 `d_` ，并使信号可用于帐户中所有属性的定位。

例如，您可以从特定站点收集ZIP代码数据，但要将其定向到所有Audience Manager属性。要使ZIP代码在平台级别可用，您可以将客户定义的ZIP码密钥(例如 `c_zip`)映射到平台定义的密钥，如下所示。

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


## Google Tag Manager(GTM)中的流量DIL {#traffic-dil-gtm}

设置并使用GTM标签提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此过程假定您拥有 [!DNL Google Tag Manager] 帐户、对该产品的一些有效知识以及Audience Manager `dil.js` 文件。

要在GTM中传送 `dil.js` 文件，请执行以下操作：

1. 创建新容器或打开现有容器。
1. 向容器添加新标记。
1. 打开标记以对其进行编辑，然后：

   * 命名标记。
   * **[!UICONTROL Custom HTML Tag]** 从 **[!UICONTROL Tag Type]** 下拉列表中进行选择。
   * 在HTML字段中，将 [!UICONTROL DIL] 代码(库+自定义代码)放入脚本标签 `<script>DIL code</script>`中。
   * 单击 **[!UICONTROL Save]**.

1. 发布容器。
1. 生成容器标签代码并将其放置在库存上。

>[!MORE_ LIKE_ This]
>
>* [Google Tag Manager帮助中心](https://support.google.com/tagmanager#topic=3441530)

