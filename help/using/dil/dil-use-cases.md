---
description: 特定DIL用例的代码示例和描述。
seo-description: 特定DIL用例的代码示例和描述。
seo-title: DIL 用例和代码示例
solution: Audience Manager
title: DIL 用例和代码示例
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL实施
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---

# DIL 用例和代码示例{#dil-use-cases-and-code-samples}

特定DIL用例的代码示例和描述。

<!-- 

c_dil_use_case.xml

 -->

## 发送数据元素以Audience Manager并DIL {#send-data-elements-dil}

创建一个对象变量，以将有关页面元素的信息发送到Audience Manager。 这对于常规数据收集或作为使用Analytics变量收集数据的替代方法非常有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**描述**

以下代码演示了如何收集页面数据并将其发送到具有[!UICONTROL DIL]的Audience Manager。 这些示例使用变量将数据元素保存在平面列表或数组中。 请记住，将变量作为[键值对](../reference/key-value-pairs-explained.md)传递。 此外，请注意键值对中键前的`c_`前缀。 此[必需前缀](../features/traits/trait-variable-prefixes.md)标识信息为用户定义的数据。 在第一个示例中，您需要手动将`c_`附加到键。 在第二个示例中， [!UICONTROL DIL]会自动为您执行此操作。

**保持值属性一致**

传入数据时，请记住保持值属性相同。 例如，如果您有两个具有相同值的键，则最后一个键值对的值优先于前一个值对象。 例如，传入`color:blue`和`color:red`会将返回的值设置为红色（覆盖蓝色）。

**示例1:将数据作为键值对发送**

此基本示例以键值对的形式向Audience Manager发送颜色和价格数据。 您的代码可能类似于以下内容：

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**示例2:在对象中发送数据**

此高级示例演示了如何将对象中的数据发送到Audience Manager。 使用此方法时，[!UICONTROL DIL]允许您将对象作为函数参数传递到[!DNL signals()]方法中。 [!UICONTROL DIL] 您的代码可能类似于以下内容：

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**示例3:在数组中发送页面数据**

在这种情况下，变量`my_object`使用数组来保存数据。 此示例以上述推荐方法传入的信息为基础，但添加了一个额外的层以适应产品类型和模型。 您的代码可能类似于以下内容：

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## 捕获引荐URL {#capture-referring-url}

捕获并发送引荐URL以Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>仅当用户在使用相似协议（HTTP与HTTPS）的页面之间移动时，此方法才起作用。 例如，当您从安全网站导航到其他安全网站时，浏览器会保留一个引荐URL。 在安全网站和不安全网站之间移动时，浏览器不会保留反向链接URL。 此行为是正常的浏览器功能，不能被[!UICONTROL DIL]绕过。

**代码示例**

您的代码可能类似于以下内容：

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 捕获搜索引擎类型和关键词搜索词 {#capture-search-engine-types}

将有关搜索引擎类型和关键词搜索的信息发送到Audience Manager。

>[!IMPORTANT]
>
>本节介绍最新版本的DIL不支持的旧版功能。

**支持的搜索引擎**

默认情况下，`DIL.getSearchReferrer`识别来自这些搜索引擎（包括国际变体）的搜索：

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**描述**

以下代码演示了如何获取任何受支持的搜索引擎的搜索反向链接。 在这种情况下，假设用户从加拿大的[!DNL Google](`www.google.ca`)搜索了“homes”一词。 此代码将帮助您捕获这些搜索词并将它们发送到Audience Manager。

**基本代码**

获取搜索反向链接的基本代码（例如`google.com`）如下所示：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜索引擎代码示例**

在这种情况下，假设用户从加拿大的[!DNL Google](`www.google.ca`)搜索了“homes”一词。 请注意代码如何为搜索引擎(`c_se`)和搜索词(`c_st`)添加所需`c_`参数的前缀。 `c_` 是一个必 [需](../features/traits/trait-variable-prefixes.md) 的前缀，用于将这些变量标识为客户定义的变量以Audience Manager。

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**未列出的搜索引擎代码示例**

在这种情况下，假设用户从`dogpile.com`搜索词“homes”。 由于默认不支持[!DNL Dogpile]，因此您可以配置DIL以识别此搜索引擎并将搜索词返回Audience Manager。 您的代码可能类似于以下内容：

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## 将键值映射到其他键 {#map-key-values}

将键值对的值与另一个键值关联。

<!-- 

c_dil_map_keys.xml

 -->

**描述**

在键值对中，附加到键的`c_`前缀将信号标识为客户定义的数据。 客户定义的数据用于在特定网站上进行定位，该特定网站在事件调用中传递了数据。 但是，有时您希望此信息可在Audience Manager帐户的所有资产中使用。 为此，请将`c_`键值对中的值映射到平台级别键。 平台级别键值以`d_`为前缀，并且该信号可用于帐户中所有属性的定位。

例如，您从特定网站收集邮政编码数据，但希望将其定位到所有Audience Manager资产。 要在平台级别提供邮政编码，您可以映射客户定义的邮政编码密钥(例如，`c_zip`)到平台定义的键，如下所示。

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

## Google Tag Manager(GTM)中的流量DIL {#traffic-dil-gtm}

使用GTM标记设置和提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此过程假定您具有[!DNL Google Tag Manager]帐户、该产品的一些工作知识以及Audience Manager`dil.js`文件。

要在GTM中传输`dil.js`文件，请执行以下操作：

1. 创建新容器或打开现有容器。
1. 向容器中添加新标记。
1. 打开标记以对其进行编辑，并：

   * 命名标记。
   * 从&#x200B;**[!UICONTROL Tag Type]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Custom HTML Tag]**。
   * 在HTML字段中，将[!UICONTROL DIL]代码（库+自定义代码）放置在脚本标记`<script>DIL code</script>`中。
   * 单击 **[!UICONTROL Save]**.

1. 发布容器。
1. 生成容器标记代码，并将其放在您的库存中。

>[!MORELIKETHIS]
>
>* [Google Tag Manager帮助中心](https://support.google.com/tagmanager#topic=3441530)
>* [信号](../dil/dil-instance-methods.md#signals)
* [关键变量的前缀要求](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

