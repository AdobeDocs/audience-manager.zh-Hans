---
description: 在选择退出管理方面，Adobe符合整个行业的标准。阅读有关Audience Manager支持的选择退出类型的完整信息。
seo-description: 在选择退出管理方面，Adobe符合整个行业的标准。阅读有关Audience Manager支持的选择退出类型的完整信息。
seo-title: 选择退出管理
solution: Audience Manager
title: 选择退出管理
uuid: 61b43e0e-bfe3-497e-ade2-6a942 a98407 e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Opt-out Management{#opt-out-management}

在选择退出管理方面，Adobe符合整个行业的标准。阅读有关Audience Manager支持的选择退出类型的完整信息。

## Global Opt-Out {#global-opt-out}

全局选择退出代表所有品牌的Audience Manager和其他Adobe Experience Cloud解决方案。下表列出了全局选择退出的方法：

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p><a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> “隐私选择”页面 </a> 提供了一个单击功能，可让最终用户控制和退出Adobe Experience Cloud广告解决方案(包括Audience Manager)的数据收集。Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section </a> of the Privacy Choices page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>对Audience Manager的直接API调用 </p> </td> 
   <td colname="col2"> <p>You can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curl -i“https://www.demdex.net/demoptout.jpg”—cookie”demdex=123456789012345678980123456780123678；dechtd=12；DST=12” </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备 </p> </td> 
   <td colname="col2"> <p>请参阅选择退出和隐私设置： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android设备 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS 设备 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的最终用户也可以访问我们行业标准合作伙伴的网站，选择退出全球数据收集。

* [数字广告联盟(DAA)](https://optout.aboutads.info/?c=2#!/)；
* [网络广告促进会(NAI)](https://optout.networkadvertising.org/?c=1#!/)。

遵循上述选择退出请求：

* Audience Manager将停止未来所有数据收集、细分或激活。
* 在120天后，历史数据将从用户配置文件中删除。

## Partner Level Opt-Out {#partner-opt-out}

合作伙伴级别选择退出允许特定Audience Manager合作伙伴退出数据收集。The partner-level opt-out works with [Declared ID](../../features/declared-ids.md) calls and Device ID calls, as described in the sections below.

### 包含已声明ID调用的合作伙伴级别选择退出

按照合作伙伴级选择退出的ID调用进行操作：

* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) linked to the [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection.
* Audience Manager将停止为链接到CRM ID的最后一个设备ID停止所有数据收集、细分或激活。
* 不删除历史数据。

<br/>

**退出调用**

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**示例**

You can make a declared ID opt-out request with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. 请参阅 [CID 取代 DPID 和 DPUUID](../../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

**选择退出CID和CID_ IC**

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| 选择退出 | 代码示例 |
|--- |--- |
| 数据提供者ID和用户ID。 | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| 集成代码和用户ID。 | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| 多d_ cid和d_ cid_ ic键值对。 | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### 使用设备ID调用的合作伙伴级别选择退出

You can opt-out from data collection on a given device ID for a brand by making the following calls to the [DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 选择退出 | 代码示例 |
|--- |--- |
| An Audience Manager Unique User ID (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Read more about `uuid`, `mid` and `imsOrgId` in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

使用设备ID调用之后的合作伙伴级选择退出：

* 设备ID已退出数据收集。
* Audience Manager将停止合作伙伴的所有数据收集、细分或激活，继续为设备ID前进。
* 不删除历史数据。
