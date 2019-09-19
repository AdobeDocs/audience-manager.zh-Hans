---
description: Adobe在选择退出管理方面遵守所有行业标准。 阅读以了解有关Audience manager支持的退出类型的完整信息。
seo-description: Adobe在选择退出管理方面遵守所有行业标准。 阅读以了解有关Audience manager支持的退出类型的完整信息。
seo-title: 选择退出管理
solution: Audience Manager
title: 选择退出管理
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# 选择退出管理{#opt-out-management}

Adobe在选择退出管理方面遵守所有行业标准。 阅读以了解有关Audience manager支持的退出类型的完整信息。

## 全局退出 {#global-opt-out}

全球选择退出是指在Audience manager和其他适用于所有品牌的Adobe Experience cloud解决方案中选择退出。 下表列出了用于全局退出的方法：

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
   <td colname="col2"> <p>您 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 的隐私权选择页 </a> 面提供一键功能，让您的最终用户能够控制Adobe Experience cloud广告解决方案（包括Audience Manager）收集和选择退出数据。 具体而言，请参阅“ <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 隐私权选择” </a> 页面的业务客户部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>直接向Audience manager调用API </p> </td> 
   <td colname="col2"> <p>通过调用以下DCS API并包含 <a href="../../reference/ids-in-aam.md"> Audience Manager用户ID，您可以退出所有Audience Manager品牌的数据收集 </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=123456789012345678901234567890123456789012345678;dextp=12;DST=12” </code> </p> <p>因此，我们将为已提交 <code>的Audience Manager用户ID设置demdex=NOTARGET</code><code>和dextp=NOTARGET</code> cookies。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备 </p> </td> 
   <td colname="col2"> <p>请参阅以下选项和隐私设置： </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android设备 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS 设备 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

您的最终用户还可以通过访问我们行业标准合作伙伴的网站，选择退出全球数据收集。

* [数字广告联盟(DAA)](https://optout.aboutads.info/?c=2#!/);
* [网络广告计划(NAI)](https://optout.networkadvertising.org/?c=1#!/)。

按照上述选择退出请求执行操作：

* Audience manager将在以后停止所有数据收集、细分或激活。
* 120天后，历史数据将从用户配置文件中删除。

## 合作伙伴级别选择退出 {#partner-opt-out}

合作伙伴级别的退出允许从特定Audience manager合作伙伴的数据收集中选择退出。 合作伙伴级别的退出功能适用于 [Declared ID调用和Device](../../features/declared-ids.md) ID调用，如以下各节所述。

### 使用声明的ID调用的合作伙伴级别退出

使用声明的ID调用执行合作伙伴级别的退出操作：

* 与[CRM ID链接的最后一个设备ID(](../../reference/ids-in-aam.md)Audience Manager唯一用户ID [](../../reference/ids-in-aam.md) )已选择不进行数据收集。
* Audience manager将停止对链接到CRM ID的最后一个设备ID的所有数据收集、细分或激活。
* 不会删除历史数据。

<br/>

**退出呼叫**

当Audience manager收到合作伙伴级别的退出请求时，DCS返回的JSON包含错误代码171 [，其中包含消息](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)[!UICONTROL "Encountered opt out tag"]，而不是Audience manager用户ID。

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

您可以对和键值对发出声明的ID `d_cid` 退出 `d_cid_ic` 请求。 旧参数(如和 `d_dpid` 仍可 `d_dpuuid` 用，但被视为已弃用。 请参阅 [CID 取代 DPID 和 DPUUID](../../reference/cid.md)。In the examples, *italics* indicates a variable placeholder.

**使用CID和CID_IC选择退出**

有关说明和语法，请参阅 [URL变量和Declared ID的语法](../../features/declared-ids.md#variables-and-syntax)。

| 选择退出使用 | 代码示例 |
|--- |--- |
| 数据提供者ID和用户ID。 | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| 集成代码和用户ID。 | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| 多个d_cid和d_cid_ic键值对。 | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### 通过设备ID调用退出合作伙伴级别

通过对 [DCS API进行以下调用，可以选择退出品牌的给定设备ID上的数据收集](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 选择退出使用 | 代码示例 |
|--- |--- |
| Audience Manager唯一用户ID(`uuid`)。 | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID(`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

在Audience manager中， `uuid`阅读 `mid` ID索 `imsOrgId` 引，了解更多相关信息 [](/help/using/reference/ids-in-aam.md)。

通过设备ID调用执行合作伙伴级别的退出操作：

* 设备ID已选择退出数据收集。
* Audience manager将停止为合作伙伴收集、细分或激活所有数据，以后将停止设备ID。
* 不会删除历史数据。
