---
description: 在Destination Builder中，“配置”部分包含Cookie域和将数据发布到字段。 这些规则允许您创建规则，以确定目标是设置Cookie还是返回Cookie。 Cookie域和发布数据相互独立工作，是可选的。 您可以创建Cookie目标，而无需使用其中任何一个。
seo-description: 在Destination Builder中，“配置”部分包含Cookie域和将数据发布到字段。 这些规则允许您创建规则，以确定目标是设置Cookie还是返回Cookie。 Cookie域和发布数据相互独立工作，是可选的。 您可以创建Cookie目标，而无需使用其中任何一个。
seo-title: Cookie 目标的可选设置
solution: Audience Manager
title: Cookie 目标的可选设置
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 7%

---


# Cookie 目标的可选设置 {#optional-settings-cookies}

在[!UICONTROL Destination Builder]中，[!UICONTROL Configuration section]包含[!UICONTROL Cookie Domain]和[!UICONTROL Publish Data To]字段。 这些规则允许您创建规则，以确定目标是设置Cookie还是返回Cookie。 [!UICONTROL Cookie Domain] 并 [!UICONTROL Publish Data To] 且相互独立，是可选的。您可以创建Cookie目标，而无需使用其中任何一个。

## Cookie域：语法和示例{#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie 域 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>语法</b> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Cookie域</span>字段接受一个简单的文本字符串，它允许您在指定域或所有域上设置Cookie。 使用此功能时： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">为每个Cookie目标仅设置一个域。 请勿在<span class="wintitle"> Cookie域</span>字段中键入多个域。 请改为创建另一个<span class="wintitle">目标</span>。 </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">请勿使用通配符。 </li> 
     </ul> </p> <p> 将<span class="wintitle"> Cookie域</span>字段留空，以在所有域上设置Cookie。 这是默认设置。 </p> <p>要在特定域和子域上设置Cookie: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">在<span class="wintitle"> Cookie域</span>字段中键入域名。 </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">开始带句点的域名。 例如，<code> .somedomain.com</code>。 </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">不需要<code> https://www</code>前缀。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>示例</b> </p> </td> 
   <td colname="col2"> <p>举个简单的例子，假设我们有一个虚构的网站，名为sports.com。 Sports.com有高尔夫、棒球和足球的域。 要在所有体育域中设置Cookie，您应在<span class="wintitle"> Cookie域</span>框中键入，如下所示： </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>这告知<span class="keyword">Audience Manager</span>在任何包含模式<code><i>something</i></code>.sports.com的域中设置cookie。 请参见下文，了解更复杂的示例集。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 复杂Cookie域示例

这些示例显示是否将根据如何配置[!DNL Audience Manager]选项来设置cookie。[!UICONTROL Cookie Domain]

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 网站 </th> 
   <th colname="col2" class="entry">Cookie域：.sports.com <p>Cookie集 </p> </th> 
   <th colname="col3" class="entry">Cookie域：.golf.sports.com <p>Cookie集 </p> </th> 
   <th colname="col4" class="entry">Cookie域：空白 <p>Cookie集 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 是 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> 是 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> 否 </td> 
   <td colname="col3"> 否 </td> 
   <td colname="col4"> 是 </td> 
  </tr> 
 </tbody> 
</table>

## 将数据发布到{#publish-data-to}

如果域满足您选择的选项所设置的条件，则[!UICONTROL Publish Data To]设置将返回cookie。 选项包括：

* **[!UICONTROL All of our domains]**:（默认）返回 [!DNL cookie] 任何域的值。
* **[!UICONTROL Only the selected domains]**:仅为在域列表中选择的域返回cookie。
* **[!UICONTROL All of our domains except the selected domains]**:阻止所选域接收 [!DNL cookie]。所有其他域都可以接收[!DNL cookie]。

>[!MORELIKETHIS]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)