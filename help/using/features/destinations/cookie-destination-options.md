---
description: 在目标生成器中，配置部分包含Cookie域和将数据发布到字段。这些规则允许您创建规则以确定目标设置cookie还是返回cookie。Cookie域和Publish Data可独立工作，并且为可选数据。您可以创建cookie目标，而无需使用其中任何一个。
seo-description: 在目标生成器中，配置部分包含Cookie域和将数据发布到字段。这些规则允许您创建规则以确定目标设置cookie还是返回cookie。Cookie域和Publish Data可独立工作，并且为可选数据。您可以创建cookie目标，而无需使用其中任何一个。
seo-title: Cookie目标的可选设置
solution: Audience Manager
title: Cookie目标的可选设置
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# Cookie目标的可选设置 {#optional-settings-cookies}

In [!UICONTROL Destination Builder]，the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields.这些规则允许您创建规则以确定目标设置cookie还是返回cookie。[!UICONTROL Cookie Domain] 独立 [!UICONTROL Publish Data To] 工作，并且是可选的。您可以创建cookie目标，而无需使用其中任何一个。

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
   <td colname="col2"> <p><span class="wintitle"> Cookie域</span> 字段接受一个简单的文本字符串，它允许您在指定的域或所有域上设置cookie。使用此功能时： </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">仅为每个cookie目标设置一个域。请勿在 <span class="wintitle"> Cookie域</span> 字段中键入多个域。请改用另 <span class="wintitle"> 一个目标</span> 。 </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">请勿使用通配符字符。 </li> 
     </ul> </p> <p> 将 <span class="wintitle"> Cookie域</span> 字段保留为空可在所有域上设置cookie。这是默认设置。 </p> <p>要在特定域和子域上设置cookie，请执行以下操作： </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">在 <span class="wintitle"> Cookie域</span> 字段中键入域名的名称。 </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">用句点启动域名。例如， <code> .somedomain.com</code>。 </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>示例</b> </p> </td> 
   <td colname="col2"> <p>例如，假设我们有一个名为sports. com的虚构网站。Sports.com有用于高尔夫、棒球和足球的域。要在所有运动域中设置cookie，您应在 <span class="wintitle"> Cookie域名</span> 中键入该cookie，如下所示： </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>这告诉 <span class="keyword"> Audience Manager</span> 在任何包含pattern. <code><i>sports. com模式</i></code>的域中设置cookie。请参阅下面的更复杂的示例。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 复杂Cookie域示例

这些示例将显示 [!DNL Audience Manager] 是否将根据配置 [!UICONTROL Cookie Domain] 选项设置Cookie。

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 网站 </th> 
   <th colname="col2" class="entry">Cookie域：.sports.com <p>Cookie集 </p> </th> 
   <th colname="col3" class="entry">Cookie域：.golf.sports.com <p>Cookie集 </p> </th> 
   <th colname="col4" class="entry">Cookie域：Blank <p>Cookie集 </p> </th> 
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

[!UICONTROL Publish Data To] 如果域符合您选择的选项设置的条件，则设置会返回cookie。选项包括：

* **[!UICONTROL All of our domains]**：(默认)返回任何域的一个 [!DNL cookie] 。
* **[!UICONTROL Only the selected domains]**：仅返回在域列表中选择的域的cookie。
* **[!UICONTROL All of our domains except the selected domains]**：阻止选定域接收 [!DNL cookie]。所有其他域都可以接收 [!DNL cookie]到一个。

>[!MORE_ LIKE_ This]
>
>* [创建Cookie目标](../../features/destinations/create-cookie-destination.md)