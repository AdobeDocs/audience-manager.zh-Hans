---
description: 更新您的代码以使用d_cid或d_cid_ic而不是d_dpid和d_dpuuid。 DPID和DPUUID变量将继续工作，但您应将其视为已弃用。 这包括不带d_前缀的DPID和DPUUID变量。
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID取代DPID和DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 1%

---

# CID取代DPID和DPUUID{#cid-replaces-dpid-and-dpuuid}

更新您的代码以使用`d_cid`或`d_cid_ic`，而不是`d_dpid`和`d_dpuuid`。 DPID和DPUUID变量将继续工作，但您应将其视为已弃用。 这包括不带`d_ prefix`的DPID和DPUUID变量。

## DPID和DPUUID：审核 {#dpid-dpuuid-review}

DPID和DPUUID是包含数据提供程序ID和用户ID的键值对。 这些键值对将提供程序ID链接到用户ID。 它们会在事件调用、入站同步事件和ID调用期间发送数据。 如果没有这些ID，[!DNL Audience Manager]和其他服务或功能将无法匹配和同步ID。 这些变量有时使用或不使用`d_`前缀来表示，如下所示。 请注意，在代码中，*斜体*&#x200B;表示变量占位符。

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供程序ID (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数据提供程序唯一用户ID (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

这些键值对仍然有效，但已弃用。 您应该更新代码以改用CID或CID_IC。

## CID和CID_IC：关于 {#cid-cidic-about}

CID和CID_IC键值对将取代DPID和DPUUID。 它们提供与DPID和DPUUID相同的函数，但效率更高，因为它们在一个键值对中包括数据提供程序ID（或集成代码）和用户ID。 在每个键值对中：

* =符号用于分隔键及其相关值。
* 非打印ASCII字符%01用于分隔值。

`d_cid`和`d_cid_ic`使用以下语法。 请注意，在代码中，*斜体*&#x200B;表示变量占位符。

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>客户ID (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客户ID集成代码(CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> <span class="term">集成代码</span>是可以使用的替代ID，而不是由<span class="keyword"> Audience Manager</span>分配的数据Source ID。 如果需要配置集成代码，请参阅<a href="../features/manage-datasources.md#create-data-source">创建数据Source</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另请参阅[已声明ID的URL变量和语法](../features/declared-ids.md#variables-and-syntax)。

>[!NOTE]
>
>您可以将集成代码用于您自己的数据源以及您有权访问的全局[共享数据源](../features/datasources-list-and-settings.md#settings-menu-options)。 例如，在处理移动标识符数据源时，您可以使用集成代码。 完全按照以下指定方式使用以下集成代码：

* GAID的&#x200B;**DSID_20914**，表示运行Android操作系统的设备。
* IDFA的&#x200B;**DSID_20915**，表示运行iOS操作系统的设备。

**示例**

下表提供了按事件类型划分的示例。

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件类型 </th> 
   <th colname="col2" class="entry"> 示例 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>事件 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">新建： <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">已弃用： <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站同步(IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">新建： <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">已弃用： <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>生成Audience Manager UUID (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">新建： <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">已弃用： <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

每个调用还可以包含多个`d_cid`和`d_cid_ic`键值对，如下所示：

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## 开发团队的重要注意事项 {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>项目 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL编码 </p> </td> 
   <td colname="col2"> <p>您的开发团队<i>必须</i>对CID键值对中的以下变量应用URL编码： </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>注意：在将用户ID和集成代码<i>串联到字符串之前，必须对其进行URL编码。 </i>这是因为URL编码中不能捕获分隔两个变量的ASCII字符%01。 </p> </p> <p>URL编码可确保将包含保留字符或不安全字符（例如但不限于、+或=）的用户ID和集成代码正确传输到我们的服务器。 </p> <p>使用<a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII编码表</a>作为参考。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用全局共享数据源的集成代码 </p> </td> 
   <td colname="col2"> <p>您可以将集成代码用于您自己的数据源以及您有权访问的全局<a href="../features/datasources-list-and-settings.md#settings-menu-options">共享数据源</a>。 例如，在处理移动标识符数据源时，您可以使用集成代码。 完全按照以下指定方式使用以下集成代码： </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> GAID的<b>DSID_20914</b>，表示运行Android操作系统的设备。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> IDFA的<b>DSID_20915</b>，表示运行iOS操作系统的设备。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
