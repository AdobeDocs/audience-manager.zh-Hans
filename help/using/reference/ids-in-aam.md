---
description: 有关Adobe Audience Manager ID的完整列表，请参阅本文档。
keywords: DPID；DPUUID；CID；UUID；uuid；uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid、uuid
seo-description: 有关Adobe Audience Manager ID的完整列表，请参阅本文档。
seo-title: Audience Manager中ID的索引
solution: Audience Manager
title: Audience Manager中ID的索引
uuid: 292185EC-7c6a-414b-ab17-800c21 cb1 f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Audience Manager中ID的索引{#index-of-ids-in-audience-manager}

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
   <td colname="col2"> <p> <b><span class="keyword"> Audience Manager</span> 唯一用户ID </b> </p> <p> <span class="keyword"> Audience Manager</span> 与其交互的每个设备相关联的一个数字、38位设备ID。每当您在Audience Manager UI中看到对唯一用户的提及时，请考虑此ID。<p><span class="keyword"> Audience Manager</span> 尝试将此ID另存为“demdex. net”第三方域中的cookie。</p> </p> <p>Audience Manager UUID在事件调用中作为d_ uuid信号发送。 </p> </td> 
   <td colname="col3"> <p><code> demdex=079552616528803295039025058042704272278</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>imsOrID </p> </td> 
   <td colname="col2"> <p> <b>组织 ID</b> </p> <p>这是在注册Experience Cloud时提供的公司ID。要了解如何找到公司的组织ID，请阅读 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> 组织和帐户链接</a> 并向下滚动查找组织ID。</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>合作伙伴ID</b> </p> <p> PID是Audience Manager中 <span class="keyword"> 公司的ID</span>。<span class="keyword"> Audience Manager</span> 将imsOrID关联到PID。 </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>EID，MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>Experience Cloud ID(EID、旧版缩写MID或MCID)从您的组织ID和 <span class="keyword"> Audience Manager</span> 唯一用户ID以数学方式派生。只要这些ID保持不变，为特定用户生成正确的ECID就只是一个数学问题。借助相同的组织ID和Audience Manager UUID，您每次都能获得相同的EID值。您可以阅读 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 有关Cookie和Experience Cloud ID</a> 文档中的EID的更多信息。 </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>特征ID</b> </p> <p>特征ID可唯一标识 <span class="keyword"> Audience Manager</span> 环境中的特征。特征ID会分配给用户界面(UI)中的每个特征。 </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>区段ID </b> </p> <p>区段ID可在 <span class="keyword"> Audience Manager</span> 环境中唯一标识区段。区段ID会分配给UI中的每个区段。 </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>传统区段ID </b> </p> <p>此ID可在 <span class="keyword"> Audience Manager</span> 环境中唯一标识区段。将为UI中的每个区段分配一个旧版区段ID。 </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DestiID </p> </td> 
   <td colname="col2"> <p> <b>目标ID </b> </p> <p>目标ID可在 <span class="keyword"> Audience Manager</span> 环境中唯一标识目标。将为UI中的每个目标分配一个ID。 </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>数据源ID(也称为数据提供者ID)</b> </p> <p>数据源ID是ID或特征的命名空间。将ID分配给UI中的每个数据源(数据提供程序)。 </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>数据提供者唯一用户ID </b><b>(也称为CRM ID)</b> </p> <p>第三方ID。这是您在自己的CRM系统中识别最终用户的ID。您可以将DPuID与 <span class="keyword"> Audience Manager</span> UI同步，您可以在ID同步过程中将不同 <span class="wintitle"> 数据源</span> (DPID <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> )中的DPUUID同步</a>。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM ID </p> </td> 
   <td colname="col2"> <p>请参阅上面的DPUUID。 </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID，CID_ IC </p> </td>
   <td colname="col2"> <p> <b>客户ID，客户ID集成代码</b> </p> <p> <b>CID和CID_ IC键值对 <a href="../reference/cid.md"> 替换DPID和DPUUID</a>。</b> 它们提供的功能与DPID和DPUUID相同，但更有效，因为它们包含数据提供者ID和用户ID(或集成代码)，以便在一个键值对中。 </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7brick7ff4879e4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GID </li>
      <li>RIA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>设备广告ID</b> </p> <p>每个硬件设备的用于广告宣传的独特 ID。通常由设备或设备操作系统的制造商提供。 </p> </td> 
   <td colname="col3"> <p>IDFA、GID、Roku ID、Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>设备广告ID- IDFA- iOS设备</b> </p> <p> <b>IDFA</b> ID是设备制造商提供的移动设备标识符。这些ID代表运行iOS操作系统的设备。 </p> </td> 
   <td colname="col3"> <p> 此格式严格包含32 <i>个大写</i> 数字，分别由五个组显示并用连字符分隔，格式为8-4-4-4-12，总共为36个字符。 </p> <p><code> AEBE52E7-03EE-455A-B3 C4-E5728396239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>设备广告ID- GUID- Android设备</b> </p> <p><b>GID</b> ID是设备制造商提供的移动设备标识符。这些ID代表运行Android操作系统的设备。 </p> </td> 
   <td colname="col3"> <p>格式严格由32 <i>个小写</i> 十六进制数字组成，并以8-4-4-4-12格式显示并以连字符分隔，总共36个字符。 </p> <p> <code> e4fe9bde-ca0-47b6-908d-ffba3 fa184 f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku- RDA- Roku流设备</b> </p> <p><b>GID</b> RIDA ID是由Roku设备制造商提供的流设备标识符。</p> </td>
   <td colname="col3"> <p>格式严格由32 <i>个小写</i> 十六进制数字组成，并以8-4-4-4-12格式显示并以连字符分隔，总共36个字符。 </p> <p> <code> fcb2a29c-315a-5e6b-bynamer-d889 ba19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Microsoft Advertising ID- MAID- Windows10设备</b> </p> <p><b>MAID</b> ID是按每个用户为单位生成的Windows10设备标识符。</p> </td>
   <td colname="col3"> <p>MIMID格式化为字母数字字符串。</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID- Samsung设备</b> </p> Samsung DUID是Samsung TV提供的设备标识符。</p> </td>
   <td colname="col3"> <p>Samsung DUID格式化为字母数字字符串。</p></td>
  </tr>
 </tbody> 
</table>