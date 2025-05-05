---
description: 特定DIL用例的代码示例和描述。
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL用例和代码示例
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# DIL用例和代码示例{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此点之后不会开发[!DNL DIL]。 建议客户评估[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)。

特定DIL用例的代码示例和描述。

<!-- 

c_dil_use_case.xml

 -->

## 将数据元素发送到DIL的Audience Manager {#send-data-elements-dil}

创建一个对象变量，以将有关页面元素的信息发送到Audience Manager。 这对常规数据收集或用Analytics变量收集数据的替代方法非常有用。

<!-- 

c_dil_send_page_objects.xml

 -->

**描述**

以下代码演示了如何收集页面数据并将这些数据发送给[!UICONTROL DIL]的Audience Manager。 这些示例使用变量将数据元素保存在平面列表或数组中。 请记住，将变量作为[键值对](../reference/key-value-pairs-explained.md)传递。 此外，请注意键值对中的键之前的`c_`前缀。 此[必需的前缀](../features/traits/trait-variable-prefixes.md)将信息标识为用户定义的数据。 在第一个示例中，您需要手动将`c_`附加到键。 在第二个示例中，[!UICONTROL DIL]自动为您执行此操作。

**保持值属性一致**

传入数据时，请记住保持值属性相同。 例如，如果您有两个值不同的相同键，则最后一个键 — 值对的值优先于前面的值对象。 例如，传入`color:blue`和`color:red`会将返回的值设置为红色（覆盖蓝色）。

**示例1：将数据作为键值对发送**

此基本示例将颜色和价格数据以键值对的形式发送到Audience Manager。 您的代码可能类似于以下内容：

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals(&lbrace; 
   c_color:"blue", 
   c_price:"900" 
&rbrace;); 
sample_dil.api.submit();
</code></pre>

**示例2：在对象中发送数据**

此高级示例演示了如何将对象中的数据发送到Audience Manager。 使用此方法时，[!UICONTROL DIL]允许您将对象作为函数参数传递到[!DNL signals()]方法中。 [!UICONTROL DIL]您的代码可能类似于以下内容：

<pre class="java"><code>
var my_object = &lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**示例3：在数组中发送页面数据**

在这种情况下，变量`my_object`使用数组来保存数据。 此示例以上述推荐方法传递的信息为基础，但添加了额外的层以适应产品类型和模型。 您的代码可能类似于以下内容：

<pre class="java"><code>
var my_objects = &lbrack;&lbrace; 
   color : "blue", 
   price : "900" 
&rbrace;, &lbrace; 
   type : "acura", 
   model : "tl" 
&rbrace;&rbrack;; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
&lbrace; 
    sample_dil.api.signals(my_objects[i], "c_"); 
&rbrace; 
sample_dil.api.submit();
</code></pre>

## 捕获反向链接URL {#capture-referring-url}

捕获反向链接URL并将其发送给Audience Manager。

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>仅当用户在具有相似协议（HTTP与HTTPS）的页面之间移动时，此方法才有效。 例如，当您从一个安全站点导航到另一个安全站点时，浏览器会保留一个反向链接URL。 在安全站点和不安全站点之间移动时，浏览器不会保留反向链接URL。 此行为是正常的浏览器功能，无法被[!UICONTROL DIL]规避。

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
>此部分介绍旧版功能，最新版本的DIL不支持此功能。

**支持的搜索引擎**

默认情况下，`DIL.getSearchReferrer`可以识别来自这些搜索引擎的搜索（包括国际变体）：

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**描述**

以下代码演示了如何获取任何受支持的搜索引擎的搜索反向链接。 在本例中，假设用户从[!DNL Google]加拿大(`www.google.ca`)搜索术语“homes”。 此代码将帮助您捕获这些搜索词并将它们发送到Audience Manager。

**基本代码**

用于获取搜索反向链接的基本代码（例如，从`google.com`）如下所示：

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**已列出搜索引擎代码示例**

在这种情况下，假设用户从[!DNL Google]加拿大(`www.google.ca`)搜索术语“homes”。 请注意代码如何为搜索引擎(`c_se`)和搜索词(`c_st`)所需的`c_`参数添加前缀。 `c_`是[必需的前缀](../features/traits/trait-variable-prefixes.md)，它将它们标识为要Audience Manager的客户定义的变量。

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

**未列出的搜索引擎代码示例**

在这种情况下，假设用户从`dogpile.com`中搜索术语“homes”。 由于[!DNL Dogpile]默认不受支持，因此您可以配置DIL以识别此搜索引擎并将搜索词返回给Audience Manager。 您的代码可能类似于以下内容：

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, &lbrace;  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
&rbrace;); 
 
if (search_referrer && search_referrer.valid) &lbrace; 
  adobe_dil.api.signals(&lbrace; 
    c_se : se.name, 
    c_st : se.keywords 
  &rbrace;).submit(); 
&rbrace;
</code></pre>

## 将键值映射到其他键 {#map-key-values}

将键值对中的值关联到另一个键。

<!-- 

c_dil_map_keys.xml

 -->

**描述**

在键值对中，附加到键的`c_`前缀将信号标识为客户定义的数据。 客户定义的数据用于定位在事件调用中传入数据的特定网站。 但是，有时您会希望此信息在Audience Manager帐户中的所有资产中均可用。 为此，请将`c_`键值对中的值映射到平台级别键。 平台级别密钥以`d_`为前缀，并且该信号可用于在您的帐户的所有属性中进行定位。

例如，您从特定网站收集邮政编码数据，但希望将其定位到所有Audience Manager资产。 要使邮政编码在平台级别可用，您可以将客户定义的邮政编码键（例如`c_zip`）映射到如下所示的平台定义的键。

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

## Google Tag Manager (GTM)中的流量DIL {#traffic-dil-gtm}

使用GTM标记设置并提供DIL。

<!-- 

t_dil_google_tagmanager.xml

 -->

此过程假定您拥有[!DNL Google Tag Manager]帐户、对该产品的一些工作知识以及您的Audience Manager`dil.js`文件。

要在GTM中传输`dil.js`文件，请执行以下操作：

1. 创建新容器或打开现有容器。
1. 向容器中添加新标记。
1. 打开标记以对其进行编辑，并：

   * 命名标记。
   * 从&#x200B;**[!UICONTROL Tag Type]**&#x200B;下拉列表中选择&#x200B;**[!UICONTROL Custom HTML Tag]**。
   * 在HTML字段中，将[!UICONTROL DIL]代码（库+自定义代码）放置在脚本标记`<script>DIL code</script>`中。
   * 单击 **[!UICONTROL Save]**。

1. Publish容器。
1. 生成集装箱标记代码并将其放在库存中。

>[!MORELIKETHIS]
>
>* [Google Tag Manager帮助中心](https://support.google.com/tagmanager#topic=3441530)
>* [信号](../dil/dil-instance-methods.md#signals)
>* [关键变量的前缀要求](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html?lang=zh-Hans#prefix-requirements-for-key-variables)
