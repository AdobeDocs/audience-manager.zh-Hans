---
description: 特定DIL用例的代码示例和说明。
seo-description: 特定DIL用例的代码示例和说明。
seo-title: DIL用例和代码示例
solution: Audience Manager
title: DIL用例和代码示例
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# DIL用例和代码示例{#dil-use-cases-and-code-samples}

特定DIL用例的代码示例和说明。

<!-- 

c_dil_use_case.xml

 -->

## 使用DIL将数据元素发送到Audience Manager {#send-data-elements-dil}

创建一个对象变量，用于将有关页面元素的信息发送到Audience Manager。 这对于常规数据收集或使用Analytics变量收集数据的替代方法很有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**描述**

以下代码演示如何收集页面数据并将其发送到Audience Manager [!UICONTROL DIL]。 这些示例使用变量将数据元素保存在平面列表或数组中。 记住，将变量作 [为键值对传递](../reference/key-value-pairs-explained.md)。 另外，请注 `c_` 意键值对中键前的前缀。 此必 [需的前缀](../features/traits/trait-variable-prefixes.md) ，将信息标识为用户定义的数据。 在第一个示例中，您需要手动追加 `c_` 到键。 在第二个示例中， [!UICONTROL DIL] 自动为您执行此操作。

**使值属性保持一致**

在传入数据时，请记住使值属性保持相同。 例如，如果您有两个具有相同值的键，则最后一个键值对的值优先于前一个值对象。 例如，传入并 `color:blue` 将返 `color:red` 回的值设置为红色（覆盖蓝色）。

**示例1:将数据作为键值对发送**

此基本示例以键值对的形式将颜色和价格数据发送给Audience Manager。 您的代码可能类似于以下内容：

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**示例2:在对象中发送数据**

此高级示例演示如何将对象中的数据发送到Audience Manager。 使用此方法时，允 [!UICONTROL DIL] 许将对象作为函数参数传递给该方 [!DNL signals()] 法。 [!UICONTROL DIL] 您的代码可能类似于以下内容：

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**示例3:在阵列中发送页面数据**

在这种情况下，变量 `my_object` 使用数组保存数据。 此示例构建于上述建议方法传入的信息之上，但添加了一个额外的层来适应产品类型和型号。 您的代码可能类似于以下内容：

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

## 捕获引用URL {#capture-referring-url}

捕获引用URL并将其发送到Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>此方法仅在用户在具有类似协议（HTTP与HTTPS）的页面之间移动时才有效。 例如，当您从安全站点导航到另一个安全站点时，浏览器会保留引用URL。 当您在安全和非安全站点之间移动时，浏览器不会保留引用URL。 此行为是常规的浏览器功能，不能被其绕过 [!UICONTROL DIL]。

**代码示例**

您的代码可能类似于以下内容：

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 捕获搜索引擎类型和关键字搜索词 {#capture-search-engine-types}

将有关搜索引擎类型和关键字搜索的信息发送到Audience Manager。

>[!IMPORTANT]
>
>本节介绍最新版DIL不支持的旧版功能。

**支持的搜索引擎**

默认情况下，可 `DIL.getSearchReferrer` 以识别来自这些搜索引擎（包括国际变量）的搜索：

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**描述**

以下代码演示如何获取任何支持的搜索引擎的搜索引用。 在此例中，假设用户从加拿大搜索了术语“ [!DNL Google] homes”( `www.google.ca`)。 此代码将帮助您捕获这些搜索词并将其发送到Audience Manager。

**基本代码**

用于获取搜索引用的基本代 `google.com`码（例如，从）如下所示：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**列出的搜索引擎代码示例**

在此例中，假设用户从加拿大搜索了“homes”( [!DNL Google] )这个词 `www.google.ca`语。 请注意代码如何将所需 `c_` 参数作为搜索引擎( `c_se`)和搜索词( `c_st`)的前缀。 `c_` 是必需 [的前缀](../features/traits/trait-variable-prefixes.md) ，可将这些前缀标识为Audience manager的客户定义变量。

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

在这种情况下，我们假设用户从中搜索了“homes”一词 `dogpile.com`。 由于 [!DNL Dogpile] 默认不支持DIL，因此您可以配置DIL以识别此搜索引擎并将搜索词返回给Audience Manager。 您的代码可能类似于以下内容：

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

将键值对的值关联到另一个键。

<!-- 

c_dil_map_keys.xml

 -->

**描述**

在键值对中，附加到键 `c_` 的前缀将信号标识为客户定义的数据。 客户定义的数据用于定位在活动调用中传入数据的特定站点。 但是，有时您希望Audience manager帐户中的所有属性都能提供此信息。 为此，请将键值对中的 `c_` 值映射到平台级键。 平台级别键前缀有， `d_` 并使该信号可用于帐户中所有属性的定位。

例如，您从特定站点收集邮政编码数据，但希望将其定位到您的所有Audience manager属性。 要使邮政编码在平台级别可用，您可以映射客户定义的邮政编码密钥(例如， `c_zip`)至平台定义的密钥，如下所示。

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

## Google标签管理器(GTM)中的流量DIL {#traffic-dil-gtm}

使用GTM标签设置和提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此过程假定您拥有一个帐 [!DNL Google Tag Manager] 户、该产品的一些工作知识以及您的Audience manager文 `dil.js` 件。

要在GTM中传 `dil.js` 输文件，请执行以下操作：

1. 创建新容器或打开现有容器。
1. 向容器添加新标记。
1. 打开标记以编辑它，并：

   * 命名标记。
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * 在HTML字段中，将代 [!UICONTROL DIL] 码（库+自定义代码）放在脚本标记内 `<script>DIL code</script>`。
   * 单击 **[!UICONTROL Save]**.

1. 发布容器。
1. 生成容器标记代码并将其放在您的库存中。

>[!MORELIKETHIS]
>
>* [Google Tag Manager帮助中心](https://support.google.com/tagmanager#topic=3441530)
>* [信号](../dil/dil-instance-methods.md#signals)
>* [关键变量的前缀要求](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)

