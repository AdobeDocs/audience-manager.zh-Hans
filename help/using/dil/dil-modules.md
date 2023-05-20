---
description: 說明DIL.modules名稱空間中的方法。 這些模組可讓您以程式設計方式收集資料並處理Audience Manager物件。
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL 模块
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 4%

---

# DIL 模块{#dil-modules}

說明中的方法 `DIL.modules` 名稱空間。 這些模組可讓您以程式設計方式收集資料並處理Audience Manager物件。

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

与 [!UICONTROL DIL] 发送 [!DNL Analytics] 标记元素（变量、Prop、evar 等）一起工作 要 Audience Manager。 以逗号分隔的列表返回数据。 版本2.6 中提供。

**函数签名：** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>您必须将此代码放置在函数的页面 ** `s.t();` 上。

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
   <td colname="col3"> <p>包含未列舉之字串的陣列 <span class="keyword"> 分析 </span> 變數如 <code> pageName </code>， <code> channel </code>， <code> campaign </code>， <code> product </code>等。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>包含列舉的物件陣列 <span class="keyword"> 分析 </span> prop和evar等變數(例如 <code> prop1 </code>， <code> prop2 </code>， <code> evar3 </code>， <code> evar4 </code>)。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 整数 </td> 
   <td colname="col3"> <p>指出您想要傳回的疊代名稱數目。 例如，若要傳回兩個prop或evar，請設定 <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>一個物件，代表 <span class="keyword"> 分析 </span> 物件。 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>一個物件，代表 <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> 对象 </td> 
   <td colname="col3"> <p>其他選項： </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>如果您未指定其他內容，句點會取代為預設底線( _ )。 </p> <p>例如 <code> s.contextData = {abc.def = '123'} </code> ，将在事件调用查询字符串中生成 <code> c_contextData_abc_def=123 </code> 。 </p> <p>此选项仅在 DIL </span> version 5.0 或更高版本中 <span class="wintitle"> 可用。 </span></p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>例如， <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> 将导致从上下文数据的数据收集中过滤字符串数组。 此选项会排除个人身份信息（PII）。 </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**由 siteCatalyst 捕获的数据。初始化**

此函数会返回以下 [!DNL Analytics] 属性的详细信息：

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

此程式碼會建立 [!DNL Analytics] 事件（prop、eVar等） 如果值存在。

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

若要追蹤所有受監控的專案，請執行下列動作 [!DNL Analytics] 沒有上述其他函式的資料點，叫用 `siteCatalyst.init` 如下所示：

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

此 `GA.submitUniversalAnalytics();` 函式會從Google傳送資料 [!DNL Universal Analytics] 以Audience Manager。 此 [!UICONTROL DIL] 功能專為搭配以下用途而設計： `analytics.js`，此元件為Google的最新程式碼庫 [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 無法深入瞭解或控制Google `analytics.js` 程式碼程式庫。 您應確認 [!UICONTROL DIL] 當Google發行新版時，資料收集仍正常運作 `analytics.js`.
>
>* 您無法使用 `GA.submitUniversalAnalytics();` 如果您仍在使用Google的舊版Analytics追蹤代碼(例如， `ga.js` 或 `dc.js`)。 另請參閱 [GA.init](../dil/dil-modules.md#ga-init) 而非。
>


**函式簽章：** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**属性**

此 `GA.submitUniversalAnalytics();` 函数接受以下属性。

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
   <td colname="col2"> <p>Google Analytics </span> 实例 <span class="keyword"> 的全局变量。這通常是 <code> ga </code> 根據預設，除非您已自訂 <span class="keyword"> Google Analytics </span> 程式碼。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>代表您執行個體的變數 <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>（可選）</i> 在 <code> analytics.js </code> 程式庫，內部屬性是縮制的變數 <code> 'b' </code>. 此變數保留 <span class="keyword"> Google Analytics </span> 資料。 </p> <p>此屬性為選用，因為除非Google變更其內部變數的名稱，否則您不需要進行設定。 例如，如果此縮制變數變更為 <code> 'a' </code>，您可以呼叫 <code> GA.submitUniversalAnalytics(); </code> 如下所示： </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**示例**

請記得定義 [!DNL Google Analytics] `ga` 物件優先，呼叫前 [!UICONTROL DIL] 和 `GA.submitUniversalAnalytics();`. 您的程式碼可能如下所示：

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

此 `GA.init()` 函式會從舊版/已棄用的版本傳送資料 [!DNL Google Analytics] 以Audience Manager。

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` 僅適用於Google的舊版Analytics追蹤代碼、 `ga.js` 或 `dc.js`. 您無法叫用這個 [!UICONTROL DIL] 函式（若您使用） `analytics.js`，此元件為Google的最新程式碼庫 [!DNL Universal Analytics]. [!DNL Audience Manager] 使用的客戶 [!UICONTROL DIL] 和 [!DNL Universal Analytics] 應該會看到 [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**函式簽章：** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**参数**

| 名称 | 类型 | 描述 |
|---|---|---|
| `_gaq` | 数组 | 包含 GA 命令的数组。 |
| `dilInstance` | 对象 | 包含 DIL 实例的对象。 |
| `trackVars` | 对象 | *（可选）* 包含 `names` 属性的对象。 此屬性是您要追蹤的GA命令名稱陣列。 |

**支援的GA函式呼叫**

依預設， `GA.init` 從下列函式擷取資料：

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL建立GA資料的索引鍵**

Audience Manager接受索引鍵值配對形式的資料，而GA則可處理陣列中的專案。 要使用 GA 数据，请自动创建键值对， [!UICONTROL DIL] 并形成一个关键点赞： `c_ <key name>` 。 此外，GA陣列中的專案會以特定順序顯示。 因此，您必須依此順序提供所有引數，即使引數不含任何資料亦然。 [!UICONTROL DIL] 對應下列GA方法的索引鍵：

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

若要在不使用上述其他函式的情況下追蹤所有監督的GA測量結果，請叫用 `GA.init` 如下所示：

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**範例事件呼叫**

對Audience Manager的URL事件呼叫看起來可能類似這樣：

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics追蹤代碼](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [完成網頁升級： ga.js/dc.js至analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [將analytics.js新增至您的網站](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga物件方法參考](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

