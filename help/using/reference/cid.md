---
description: 更新您的代码以使用d_cid或d_cid_ic，而不是d_dpid和d_dpuuid。 DPID和DPUUID变量将继续工作，但您应将其视为已弃用。 这包括不带d_前缀的DPID和DPUUID变量。
seo-description: 更新您的代码以使用d_cid或d_cid_ic，而不是d_dpid和d_dpuuid。 DPID和DPUUID变量将继续工作，但您应将其视为已弃用。 这包括不带d_前缀的DPID和DPUUID变量。
seo-title: CID 取代 DPID 和 DPUUID
solution: Audience Manager
title: CID 取代 DPID 和 DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: 参考
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 4%

---

# CID 取代 DPID 和 DPUUID{#cid-replaces-dpid-and-dpuuid}

更新您的代码以使用`d_cid`或`d_cid_ic`，而不是`d_dpid`和`d_dpuuid`。 DPID和DPUUID变量将继续工作，但您应将其视为已弃用。 这包括不带`d_ prefix`的DPID和DPUUID变量。

## DPID和DPUUID:{#dpid-dpuuid-review}评论

DPID和DPUUID是包含数据提供程序ID和用户ID的键值对。 这些键值对将提供程序ID关联到用户ID。 它们在事件调用期间发送数据，用于入站同步事件和ID调用。 如果没有ID、[!DNL Audience Manager]和其他服务或功能，将无法匹配和同步ID。 这些变量有时使用或不带`d_`前缀表示，如下所示。 请注意，在代码中， *斜体*&#x200B;表示变量占位符。

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供程序ID(DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数据提供程序独特用户ID(DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

这些键值对仍然有效，但已弃用。 您应更新代码以改用CID或CID_IC。

## CID和CID_IC:关于{#cid-cidic-about}

CID和CID_IC键值对将取代DPID和DPUUID。 它们提供的函数与DPID和DPUUID相同，但效率更高，因为它们将数据提供程序ID（或集成代码）和用户ID包含在单个键值对中。 在每个键值对中：

* =符号将键与其相关值分隔开。
* 非打印ASCII字符%01用于分隔值。

`d_cid` 和使 `d_cid_ic` 用下面显示的语法。请注意，在代码中， *斜体*&#x200B;表示变量占位符。

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>客户ID(CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客户ID集成代码(CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> <span class="term">集成代码</span>是可以使用的替代ID，而不是由<span class="keyword">Audience Manager</span>分配的数据源ID。 如果需要配置集成代码，请参阅<a href="../features/manage-datasources.md#create-data-source">创建数据源</a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

另请参阅[已声明ID的URL变量和语法](../features/declared-ids.md#variables-and-syntax)。

>[!NOTE]
>
>您可以将集成代码用于您自己的数据源和全局[共享数据源](../features/datasources-list-and-settings.md#settings-menu-options)，您有权访问这些数据源。 例如，在使用移动标识符数据源时，您可以使用集成代码。 完全按照以下指定方式使用以下集成代码：

* **用于GAID的DSID_20914** ，表示运行Android操作系统的设备。
* **用于IDFA的DSID_20915** ，表示运行iOS操作系统的设备。

**示例**

下表按事件类型提供了相关示例。

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
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">新增了: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">已弃用: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站同步(IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">新增了: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">已弃用: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>生成Audience ManagerUUID(ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">新增了: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">已弃用: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

每个调用还可以包含多个`d_cid`和`d_cid_ic`键值对，如下所示：

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## 开发团队的重要注意事项{#dev-considerations}

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
   <td colname="col2"> <p>您的开发团队<i>必须</i>将URL编码应用于CID键值对中的以下变量： </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>注意：必须先对用户ID和集成代码<i>进行URL编码，然后再将用户ID和集成代码</i>连接到字符串中。 这是因为在URL编码中不能捕获用于分隔两个变量的ASCII字符%01。 </p> </p> <p>URL编码可确保将包含保留或不安全字符（例如，但不限于，+或=）的用户ID和集成代码正确传输到我们的服务器。 </p> <p>使用<a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII编码表</a>作为参考。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>将集成代码用于全局共享数据源 </p> </td> 
   <td colname="col2"> <p>您可以将集成代码用于您自己的数据源和全局<a href="../features/datasources-list-and-settings.md#settings-menu-options">共享数据源</a>，您有权访问这些数据源。 例如，在使用移动标识符数据源时，您可以使用集成代码。 完全按照以下指定方式使用以下集成代码： </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>用于GAID的DSID_20914</b> ，表示运行Android操作系统的设备。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>用于IDFA的DSID_20915</b> ，表示运行iOS操作系统的设备。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
