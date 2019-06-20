---
description: 更新代码以使用d_ cid或d_ cid_ ic而不是d_ dpid和d_ dpuuid。DPID和DPUUID变量将继续工作，但您应考虑已弃用。这包括不带d_前缀的DPID和DPUUID变体。
seo-description: 更新代码以使用d_ cid或d_ cid_ ic而不是d_ dpid和d_ dpuuid。DPID和DPUUID变量将继续工作，但您应考虑已弃用。这包括不带d_前缀的DPID和DPUUID变体。
seo-title: CID替换DPID和DPUUID
solution: Audience Manager
title: CID替换DPID和DPUUID
uuid: 3641eac5-b19 e-45d5-bc1 c-35a23 b4 bab8 c
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Update your code to use `d_cid` or `d_cid_ic` instead of `d_dpid` and `d_dpuuid`. DPID和DPUUID变量将继续工作，但您应考虑已弃用。This includes DPID and DPUUID variants without the `d_ prefix`.

## DPID and DPUUID: A Review {#dpid-dpuuid-review}

DPID和DPUUID是包含数据提供者ID和用户ID的键值对。这些键值将提供者ID关联到用户ID。它们在事件调用期间、入站同步事件和ID调用中发送数据。Without them, [!DNL Audience Manager], and other services or features, would not have a way to match and synchronize IDs. These variables are sometimes expressed with or without the `d_` prefix as shown below. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 语法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供者ID(DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_ dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>数据提供者ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>数据提供者唯一用户ID(DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_ dpuid=<i>data provider唯一用户ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuid=<i>data provider唯一用户ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

这些键值对仍然有效，但已弃用。应更新代码以使用CID或CID_ IC。

## CID and CID_IC: About {#cid-cidic-about}

CID和CID_ IC键值对替换DPID和DPUUID。它们提供的功能与DPID和DPUUID相同，但效率更高，因为它们包含数据提供者ID(或集成代码)和单个键值对中的用户ID。在每个键值对中：

* =符号将键与其相关值分开。
* 非打印ASCII字符%1会分隔这些值。

`d_cid` 并 `d_cid_ic` 使用下面显示的语法。Note, in the code, *italics* indicates a variable placeholder.

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
   <td colname="col2"> <p> <code>d_ cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客户ID集成代码(CID_ IC) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid_ ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> <span class="term"> 集成代码</span> 是可以使用的替代ID，而不是 <span class="keyword"> 由Audience Manager分配的数据源ID</span>。See <a href="../features/manage-datasources.md#create-data-source"> Create a Data Source</a> if you need to configure an integration code. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also, [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>You can use integration codes for your own data sources and for global [shared data sources](../features/datasources-list-and-settings.md#settings-menu-options), which you have access to. 例如，使用移动标识符数据源时，您可以使用集成代码。请按照以下指定的方式使用以下集成代码：

* **GSID_20914** ，用于GUID，代表运行Android操作系统的设备。
* **IDSID_20915** for IDFA，代表运行iOS操作系统的设备。

**示例**

下表按事件类型提供示例。

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
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">New: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Deprecated: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站同步(IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">New: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Deprecated: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>生成Audience Manager UUID(ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">New: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Deprecated: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Each call can also include multiple `d_cid` and `d_cid_ic` key value pairs like this:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Important Considerations for Development Teams {#dev-considerations}

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
   <td colname="col2"> <p>Your development teams <i>must</i> apply URL encoding to the following variables in the CID key-value pair: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> 用户ID</code><code> (dpuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> 集成代码</code> </li> 
     </ul> </p> <p> <p>Note: You must URL encode the user ID and integration code <i>before</i> concatenating them into a string. 这是因为在URL编码中不能捕获分隔两个变量的ASCII字符%01。 </p> </p> <p>URL编码确保您的用户ID和包含保留或不安全字符(如但不限于)的集成代码正确传输到我们的服务器。 </p> <p>Use the <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII encoding table</a> for reference. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用全球共享数据源的集成代码 </p> </td> 
   <td colname="col2"> <p>You can use integration codes for your own data sources and for global <a href="../features/datasources-list-and-settings.md#settings-menu-options"> shared data sources</a>, which you have access to. 例如，使用移动标识符数据源时，您可以使用集成代码。请按照以下指定的方式使用以下集成代码： </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>GSID_20914</b> ，用于GUID，代表运行Android操作系统的设备。 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>IDSID_20915</b> for IDFA，代表运行iOS操作系统的设备。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

