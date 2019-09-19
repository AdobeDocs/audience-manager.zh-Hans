---
description: 有关Adobe Audience Manager ID的完整列表，请参阅本文档。
keywords: DPID;DPUUID;CID;UUID;uid;uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: 有关Adobe Audience Manager ID的完整列表，请参阅本文档。
seo-title: Audience manager中的ID索引
solution: Audience Manager
title: Audience manager中的ID索引
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Audience manager中的ID索引{#index-of-ids-in-audience-manager}

有关Adobe Audience Manager ID的完整列表，请参阅本文档。

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 名称和说明 </th> 
   <th colname="col3" class="entry"> 示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> Unique User ID </b> </p> <p> Audience manager与其交互的每台设备关联的38位数 <span class="keyword"> 字设备</span> ID。 每当您在Audience Manager UI中看到提及独特用户时，请考虑此ID。<p><span class="keyword"> Audience Manager会尝试将此ID另存为“demdex.net”第三方域中的cookie。</span></p> </p> <p>在事件调用中，Audience Manager UUID作为d_uuid信号发送。 </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>组织 ID</b> </p> <p>这是公司在注册Experience cloud时获得的ID。 要了解如何查找您公司的组织ID，请阅读“组织和帐 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> 户关联”</a> ，然后向下滚动以查找您的组织ID。</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>合作伙伴ID</b> </p> <p> PID是 <span class="keyword"> Audience Manager中的公司ID</span>。 <span class="keyword"> Audience Manager</span> 将imsOrgId与PID关联。 </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>Experience Cloud ID（ECID，旧版缩写MID或MCID）是从您的组织ID和 <span class="keyword"> Audience Manager</span> Unique User ID中以数学方式派生的。 只要这些ID保持不变，为特定用户生成正确的ECID就只是一个数学问题。 使用相同的组织ID和Audience Manager UUID时，您每次都能获得相同的ECID值。 您可以在Cookies和Experience Cloud ID文档中阅读 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 有关ECID的更多信息</a> 。 </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>特征ID</b> </p> <p>特征ID可唯一标识 <span class="keyword"> Audience Manager环境中的特征</span> 。 在用户界面(UI)中，将为每个特征分配一个特征ID。 </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>区段ID </b> </p> <p>区段ID可唯一标识 <span class="keyword"> Audience Manager环境中的区段</span> 。 在UI中，会为每个区段分配一个区段ID。 </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>旧版区段ID </b> </p> <p>此ID可唯一标识 <span class="keyword"> Audience Manager环境中的区段</span> 。 旧版区段ID将分配给UI中的每个区段。 </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>目标ID </b> </p> <p>目标ID可唯一标识 <span class="keyword"> Audience Manager环境中的目标</span> 。 在UI中，会为每个目标分配一个ID。 </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>数据源ID（也称为数据提供者ID）</b> </p> <p>数据源ID是ID或特征的命名空间。 在UI中，每个数据源（数据提供者）都会分配一个ID。 </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>数据提供者唯一 </b> 用户ID( <b>也称为CRM ID)</b> </p> <p>第三方ID。 这是您在自己的CRM系统中识别最终用户的ID。 您可以将DPUUID与 <span class="keyword"> Audience Manager</span> UUID同步，也可以在ID同步过程中同步来自不同数据源 <span class="wintitle"> (DPUUID)的DPUUID</span><a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"></a>。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM ID </p> </td> 
   <td colname="col2"> <p>请参阅上面的DPUUID。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>客户ID，客户ID集成代码</b> </p> <p> <b>CID和CID_IC键值对替换 <a href="../reference/cid.md"> DPID和DPUUID</a>。</b> 它们提供的函数与DPID和DPUUID相同，但效率更高，因为它们将数据提供者ID和用户ID（或集成代码）包含在单个键值对中。 </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>瑞达</li>
      <li>女佣</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>设备广告ID</b> </p> <p>每个硬件设备的用于广告宣传的独特 ID。通常由设备或设备操作系统的制造商提供。 </p> </td> 
   <td colname="col3"> <p>IDFA、GAID、Roku ID、Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>设备广告ID - IDFA - iOS设备</b> </p> <p> <b>IDFA</b> ID是设备制造商提供的移动设备标识符。 这些ID表示运行iOS操作系统的设备。 </p> </td> 
   <td colname="col3"> <p> 格式严格由32个大写 <i>十六进制数字组成</i> ，以5组显示，以连字符分隔，格式为8-4-4-4-12，总共36个字符。 </p> <p><code> AEBE52E7-03EE-455A-B3C4-E57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>设备广告ID - GAID - android设备</b> </p> <p><b>GAID</b> ID是设备制造商提供的移动设备标识符。 这些ID表示运行Android操作系统的设备。 </p> </td> 
   <td colname="col3"> <p>格式严格由32个小 <i>写的十六进制数字组成</i> ，以五组显示，以连字符分隔，格式为8-4-4-4-12，总共36个字符。 </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Roku流设备</b> </p> <p><b>GAID</b> RIDA ID是Roku设备制造商提供的流式设备标识符。</p> </td>
   <td colname="col3"> <p>格式严格由32个小 <i>写的十六进制数字组成</i> ，以五组显示，以连字符分隔，格式为8-4-4-4-12，总共36个字符。 </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19ada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID - MAID - Windows 10设备</b> </p> <p><b>MAID</b> ID是Windows 10根据每个设备、每个用户生成的设备标识符。</p> </td>
   <td colname="col3"> <p>MAID的格式为字母数字字符串。</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Samsung设备</b> </p> Samsung DUID是Samsung TV提供的设备标识符。</p> </td>
   <td colname="col3"> <p>Samsung DUID的格式为字母数字字符串。</p></td>
  </tr>
 </tbody> 
</table>