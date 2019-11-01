---
description: 在Destination builder中，“配置”部分包含Cookie域和“将数据发布到”字段。 这些规则允许您创建规则以确定目标是设置Cookie还是返回Cookie。 Cookie域和发布数据相互独立工作，是可选的。 您可以创建Cookie目标，而无需使用其中任一选项。
seo-description: 在Destination builder中，“配置”部分包含Cookie域和“将数据发布到”字段。 这些规则允许您创建规则以确定目标是设置Cookie还是返回Cookie。 Cookie域和发布数据相互独立工作，是可选的。 您可以创建Cookie目标，而无需使用其中任一选项。
seo-title: Cookie目标的可选设置
solution: Audience Manager
title: Cookie目标的可选设置
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Cookie目标的可选设置 {#optional-settings-cookies}

在 [!UICONTROL Destination Builder]中， [!UICONTROL Configuration section] 包含 [!UICONTROL Cookie Domain] 和字 [!UICONTROL Publish Data To] 段。 这些规则允许您创建规则以确定目标是设置Cookie还是返回Cookie。 [!UICONTROL Cookie Domain] 相互 [!UICONTROL Publish Data To] 独立工作，是可选的。 您可以创建Cookie目标，而无需使用其中任一选项。

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
   <td colname="col2"> <p>“ <span class="wintitle"> Cookie域</span> ”字段接受一个简单的文本字符串，通过该字符串可在指定域或所有域上设置Cookie。 使用此功能时： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">为每个Cookie目标仅设置一个域。 请勿在“ <span class="wintitle"> Cookie域”字段中键入多个域</span> 。 请改为创建 <span class="wintitle"> 另一个目标</span> 。 </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">请勿使用通配符。 </li> 
     </ul> </p> <p> 将“ <span class="wintitle"> Cookie域</span> ”字段留空可在所有域上设置Cookie。 这是默认设置。 </p> <p>在特定域和子域上设置Cookie: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">在“ <span class="wintitle"> Cookie域”字段中键入域名</span> 。 </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">以句点开始域名。 For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>示例</b> </p> </td> 
   <td colname="col2"> <p>举个简单的例子，假设我们有一个虚构的网站，名为sports.com。 Sports.com拥有高尔夫球、棒球和足球等领域。 要在所有体育域中设置Cookie，您应在 <span class="wintitle"> Cookie域框中键入Cookie</span> ，如下所示： </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>这会告 <span class="keyword"> 诉Audience Manager</span> ，在包含pattern <code><i>something</i></code>.sports.com的任何域中设置Cookie。 请参见下文，了解更复杂的示例集。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 复杂的Cookie域示例

这些示例显示 [!DNL Audience Manager] 是否将根据选项的配置方式设 [!UICONTROL Cookie Domain] 置Cookie。

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

## 将数据发布到 {#publish-data-to}

如果 [!UICONTROL Publish Data To] 域满足您选择的选项设置的条件，则设置将返回cookie。 选项包括：

* **[!UICONTROL All of our domains]**:（默认）返回任 [!DNL cookie] 何域的值。
* **[!UICONTROL Only the selected domains]**:仅为在域列表中选择的域返回Cookie。
* **[!UICONTROL All of our domains except the selected domains]**:阻止选定域接收 [!DNL cookie]。 所有其他域都可以接收 [!DNL cookie]。

>[!MORELIKETHIS]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)