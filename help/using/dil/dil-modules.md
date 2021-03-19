---
description: 描述DIL.modules命名空间中的方法。 通过这些模块，您可以有计划地收集数据并使用Audience Manager对象。
seo-description: 描述DIL.modules命名空间中的方法。 通过这些模块，您可以有计划地收集数据并使用Audience Manager对象。
seo-title: DIL 模块
solution: Audience Manager
title: DIL 模块
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL实施
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 4%

---


# DIL 模块{#dil-modules}

描述`DIL.modules`命名空间中的方法。 通过这些模块，您可以有计划地收集数据并使用Audience Manager对象。

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

与[!UICONTROL DIL]一起发送[!DNL Analytics]标记元素（变量、prop、eVar等） Audience Manager。 以逗号分隔的列表返回数据。 在版本2.6中提供。

**函数签名：** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>必须在&#x200B;*页面*`s.t();`函数之前放置此代码。

<!-- 

r_dil_sc_init.xml

 -->

**参数**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>包含未枚举的<span class="keyword">分析</span>变量（如<code> pageName </code>、<code> channel </code>、<code> campaign </code>、<code> product </code>等）的字符串数组。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>包含枚举的<span class="keyword">分析</span>变量（如prop和evar）的对象数组(例如，<code> prop1 </code>、<code> prop2 </code>、<code> evar3 </code>、<code> evar4 </code>)。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 整数 </td> 
   <td colname="col3"> <p>指示要返回的重复名称数。 例如，要返回两个prop或evar，请设置<code> maxIndex:2 </code>。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>表示<span class="keyword"> Analytics </span>对象的对象。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>表示<span class="wintitle">DIL</span>的对象。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>其他选项： </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>如果未指定其他内容，则句点将替换为默认下划线(_)。 </p> <p>例如，<code> s.contextData = {abc.def = '123'} </code>将导致事件调用查询字符串中出现<code> c_contextData_abc_def=123 </code>。 </p> <p>此选项仅在<span class="wintitle">DIL</span> 5.0或更高版本中可用。 </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>例如，<code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code>将导致从上下文数据的数据收集中过滤字符串数组。 此选项不包括个人可识别信息(PII)。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**siteCatalyst.init捕获的数据**

此函数返回有关以下[!DNL Analytics]属性的详细信息：

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**示例代码**

此代码创建一个逗号分隔的[!DNL Analytics]列表（props、eVars等）事件 如果这些值存在。

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

要跟踪所有被监视的[!DNL Analytics]数据点，而不使用上面显示的附加函数，请自行调用`siteCatalyst.init`，如下所示：

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

`GA.submitUniversalAnalytics();`函数将数据从Google的[!DNL Universal Analytics]发送到Audience Manager。 此[!UICONTROL DIL]函数设计为可与`analytics.js`一起使用，后者是Google [!DNL Universal Analytics]的最新代码库。

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 对Google代码库没有任何见解或 `analytics.js` 控制。当或当Google发布新版本的`analytics.js`时，应验证[!UICONTROL DIL]数据收集是否仍在工作。
   >
   >
* 如果仍在使用Google的旧版分析跟踪代码（例如`ga.js`或`dc.js`），则不能使用`GA.submitUniversalAnalytics();`。 请改为参阅[GA.init](../dil/dil-modules.md#ga-init)。

>



**函数签名：** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**属性**

`GA.submitUniversalAnalytics();`函数接受以下属性。

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Google Analytics</span>实例的全局变量。 默认情况下，这通常为<code> ga </code>，除非您已自定义<span class="keyword">Google Analytics</span>代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>表示<span class="wintitle">DIL</span>实例的变量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>（可选）</i> 在库 <code> analytics.js </code> 中，内部属性是微型变量 <code> 'b' </code>。此变量保存<span class="keyword">Google Analytics</span>数据。 </p> <p>此属性是可选的，因为除非Google更改其内部变量的名称，否则您无需设置它。 例如，如果此微型变量更改为<code> 'a' </code>，您将调用<code> GA.submitUniversalAnalytics(); </code>，如下所示： </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

请记住先定义[!DNL Google Analytics] `ga`对象，然后再调用[!UICONTROL DIL]和`GA.submitUniversalAnalytics();`。 您的代码可能类似于：

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

`GA.init()`函数将[!DNL Google Analytics]的旧版/已弃用版本的数据发送到Audience Manager。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` 只能与Google的旧版分析跟踪代码或 `ga.js` 者 `dc.js`。如果使用`analytics.js`（Google [!DNL Universal Analytics]的最新代码库），则无法调用此[!UICONTROL DIL]函数。 [!DNL Audience Manager] 使用并 [!UICONTROL DIL] 应 [!DNL Universal Analytics] 查看 [GA.submitUniversalAnalytics的客户](../dil/dil-modules.md#ga-submit-universal-analytics)。

**函数签名：** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `_gaq` | 数组 | 包含GA命令的数组。 |
| `dilInstance` | 对象 | 包含DIL实例的对象。 |
| `trackVars` | 对象 | *（可选）* 由属性组成的对 `names` 象。此属性是要跟踪的GA命令名称数组。 |

**支持的GA函数调用**

默认情况下，`GA.init`从以下函数捕获数据：

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL为GA数据创建密钥**

Audience Manager在GA处理数组中的项时以键值对的形式接受数据。 要使用GA数据，[!UICONTROL DIL]会自动创建键值对并形成如下键：`c_ <key name>`。 此外，GA数组中的项以特定顺序显示。 因此，您必须按该顺序提供所有参数，即使这些参数不包含任何数据也是如此。 [!UICONTROL DIL] 映射以下GA方法的键：

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**示例代码**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

要跟踪所有监视的GA度量，而不使用上面显示的附加函数，请自行调用`GA.init`，如下所示：

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**示例事件调用**

对Audience Manager的URL事件调用可能类似于：

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics跟踪代码](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [完整的Web升级：ga.js/dc.js分析](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [将analytics.js添加到您的网站](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Ga对象方法参考](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

