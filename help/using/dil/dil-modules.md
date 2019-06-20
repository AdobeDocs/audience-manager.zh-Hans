---
description: 介绍DIL. modules命名空间中的方法。这些模块可让您以编程方式收集数据并与Audience Manager对象一起工作。
seo-description: 介绍DIL. modules命名空间中的方法。这些模块可让您以编程方式收集数据并与Audience Manager对象一起工作。
seo-title: DIL模块
solution: Audience Manager
title: DIL模块
uuid: d4c0d8dd-79f8-448e-b17 c-c935415 dd449
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# DIL Modules{#dil-modules}

Describes methods in the `DIL.modules` namespace. 这些模块可让您以编程方式收集数据并与Audience Manager对象一起工作。

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Works with [!UICONTROL DIL] to send [!DNL Analytics] tag elements (variables, props, eVars, etc.) Audience Manager。返回逗号分隔列表中的数据。版本2.6中提供。

**函数签名：**`DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>You must place this code on the page *before* the `s.t();` function.

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
   <td colname="col1"> <code> name </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>An array of strings that contains un-enumerated <span class="keyword"> Analytics </span> variables like <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, etc. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> 迭代名称 </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>An array of objects that contains enumerated <span class="keyword"> Analytics </span> variables like props and evars (e.g. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> MaxIndex </code> </td> 
   <td colname="col2"> 整数 </td> 
   <td colname="col3"> <p>指示要返回的重复名称数。For example, to return two props or evars, set <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> SiteCatalystreportSuite </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>An object that represents the <span class="keyword"> Analytics </span> object. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> DilinStation </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>An object that represents <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>其他选项： </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataAli碘s带 </code> </p> <p>如果未指定其他内容，则句点将替换为默认下划线(_)。 </p> <p>For example <code> s.contextData = {abc.def = '123'} </code>would result in <code> c_contextData_abc_def=123 </code> in the event call query string. </p> <p>This option is available only in <span class="wintitle"> DIL </span> version 5.0 or later. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>For example, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> would result in the array of strings being filtered from the data collection of context data. 此选项排除个人识别信息(PII)。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**由SiteCatalyst. init捕获的数据**

This function returns details on the following [!DNL Analytics] properties:

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

This code creates a comma separated list of [!DNL Analytics] events (props, eVars, etc.) 如果存在这些值。

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

To track all the monitored [!DNL Analytics] data points without the additional function shown above, invoke `siteCatalyst.init` by itself like this:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

`GA.submitUniversalAnalytics();` 该函数将数据从Google发送 [!DNL Universal Analytics] 到Audience Manager。This [!UICONTROL DIL] function is designed to work with `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 对Google `analytics.js` 代码库没有任何见解或控制。You should verify that [!UICONTROL DIL] data collection is still working if or when Google releases new versions of `analytics.js`.
   >
   >
* `GA.submitUniversalAnalytics();` 如果您仍在使用Google的传统分析跟踪代码(例如， `ga.js` 或 `dc.js`)，则无法使用。See [GA.init](../dil/dil-modules.md#ga-init) instead.
>



**函数签名：**`DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**属性**

`GA.submitUniversalAnalytics();` 函数接受以下属性。

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 属性 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> GaObject </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> 您的Google Analytics实例的全局变量 </span>。This is usually <code> ga </code> by default, unless you've customized your <span class="keyword"> Google Analytics </span> code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DilinStation </code> </p> </td> 
   <td colname="col2"> <p>The variable that represents your instance of <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> InternalpropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(可选)</i> 在 <code> 分析. js </code> 库中，internal属性是mince变量 <code> “b” </code>。This variable holds <span class="keyword"> Google Analytics </span> data. </p> <p>此属性是可选的，因为除非Google更改其内部变量的名称，否则您无需设置它。For example, if this minified variable changed to <code> 'a' </code>, you would call <code> GA.submitUniversalAnalytics(); </code> like this: </p> <p> <code> DIL. modules. GasubMitunialAnalytics(ga、DilinStation、'a')； </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

Remember to define the [!DNL Google Analytics] `ga` object first, before calling [!UICONTROL DIL] and `GA.submitUniversalAnalytics();`. 您的代码可能类似于：

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

>[!MORE_ LIKE_ This]
>
>* [ga对象方法参考](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)


## GA.init {#ga-init}

`GA.init()` 该函数将数据从旧版/已弃用的Audience [!DNL Google Analytics] Manager版本发送。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` 只能与Google的传统分析跟踪代码配合使用 `ga.js``dc.js`。You cannot invoke this [!UICONTROL DIL] function if you use `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics]. [!DNL Audience Manager] 使用 [!UICONTROL DIL] 并 [!DNL Universal Analytics] 应该看到 [GA. SubmisitalAnalytics的客户](../dil/dil-modules.md#ga-submit-universal-analytics)。

**函数签名：**`DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `_gaq` | 数组 | 包含GA命令的数组。 |
| `dilInstance` | 对象 | 包含DIL实例的对象。 |
| `trackVars` | 对象 | *(可选)* 由该 `names` 属性组成的对象。此属性是您要跟踪的一系列GA命令名称。 |

**支持的GA函数调用**

By default, `GA.init` captures data from the following functions:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL为GA数据创建密钥**

Audience Manager以键值对的形式接受数据，同时GA可与数组中的项目配合使用。To work with GA data, [!UICONTROL DIL] creates a key-value pair automatically and forms a key like this: `c_ <key name>`. 此外，GA数组中的项目以特定顺序显示。因此，即使它们不包含数据，您也必须按该顺序提供所有参数。[!UICONTROL DIL] 映射键用于以下GA方法：

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

To track all the monitored GA metrics without the additional function shown above, invoke `GA.init` by itself like this:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**示例事件调用**

对Audience Manager的URL事件调用可能类似于：

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORE_ LIKE_ This]
>
>* [Google Analytics跟踪代码](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [完整Web升级：ga.js/dc.js分析. js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [将分析. js添加到您的站点](https://developers.google.com/analytics/devguides/collection/analyticsjs/)

