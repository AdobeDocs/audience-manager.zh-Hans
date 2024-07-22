---
description: 在目标生成器中，配置部分包含“Cookie域”和“Publish数据收件人”字段。 利用这些功能，可创建规则以确定目标是设置Cookie还是返回Cookie。 Cookie域和Publish数据可相互独立工作且是可选的。 您可以创建Cookie目标，而无需使用任一目标。
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Cookie目标的可选设置
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 4%

---

# Cookie目标的可选设置 {#optional-settings-cookies}

在[!UICONTROL Destination Builder]中，[!UICONTROL Configuration section]包含[!UICONTROL Cookie Domain]和[!UICONTROL Publish Data To]字段。 利用这些功能，可创建规则以确定目标是设置Cookie还是返回Cookie。 [!UICONTROL Cookie Domain]和[!UICONTROL Publish Data To]相互独立工作，并且是可选的。 您可以创建Cookie目标，而无需使用任一目标。

## Cookie域：语法和示例 {#cookie-domain-syntax}

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
   <td colname="col2"> <p><span class="wintitle"> Cookie域</span>字段接受一个简单文本字符串，该字符串允许您在指定域或所有域上设置Cookie。 使用此功能时： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">为每个Cookie目标仅设置一个域。 请勿在<span class="wintitle"> Cookie域</span>字段中键入多个域。 改为创建另一个<span class="wintitle">目标</span>。 </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">请勿使用通配符。 </li> 
     </ul> </p> <p> 将<span class="wintitle"> Cookie域</span>字段留空可在所有域上设置Cookie。 这是默认设置。 </p> <p>要在特定域和子域上设置Cookie，请执行以下操作： </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">在<span class="wintitle"> Cookie域</span>字段中键入域的名称。 </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">域名以句点开头。 例如，<code> .somedomain.com</code>。 </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0"><code> https://www</code>前缀不是必需的。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>示例</b> </p> </td> 
   <td colname="col2"> <p>举个简单的例子，假设我们有一个名为sports.com的虚构网站。 Sports.com拥有高尔夫、棒球和足球的域名。 若要在所有运动域中设置Cookie，应在<span class="wintitle"> Cookie域</span>框中键入该值，如下所示： </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>这会告知<span class="keyword">Audience Manager</span>在包含模式<code><i>something</i></code>.sports.com的任何域中设置Cookie。 有关更复杂的一组示例，请参阅下文。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 复杂Cookie域示例

这些示例显示了[!DNL Audience Manager]是否会根据[!UICONTROL Cookie Domain]选项的配置方式设置Cookie。

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 网站 </th> 
   <th colname="col2" class="entry">Cookie域： .sports.com <p>Cookie集 </p> </th> 
   <th colname="col3" class="entry">Cookie域： .golf.sports.com <p>Cookie集 </p> </th> 
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

## Publish数据到 {#publish-data-to}

如果域符合您选择的选项所设置的标准，则[!UICONTROL Publish Data To]设置将返回Cookie。 选项包括：

* **[!UICONTROL All of our domains]**： （默认）返回任何域的[!DNL cookie]。
* **[!UICONTROL Only the selected domains]**：仅返回域列表中选定域的Cookie。
* **[!UICONTROL All of our domains except the selected domains]**：阻止所选域接收[!DNL cookie]。 所有其他域都可以接收[!DNL cookie]。

>[!MORELIKETHIS]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)
