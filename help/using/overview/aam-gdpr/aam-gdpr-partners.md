---
description: 本页概述了合作伙伴在信息可用时直接提供的信息，以及与Audience Manager实践相关的任何含义。 对进行这些更新的合作伙伴而言，关键影响是2018年5月25日生效的GDPR（一般数据保护规定）和新的IAB GDPR透明度和同意框架（IAB框架）的结果。
seo-description: 本页概述了合作伙伴在信息可用时直接提供的信息，以及与Audience Manager实践相关的任何含义。 对进行这些更新的合作伙伴而言，关键影响是2018年5月25日生效的GDPR（一般数据保护规定）和新的IAB GDPR透明度和同意框架（IAB框架）的结果。
seo-title: 目标的GDPR注意事项
solution: Audience Manager
title: 目标的GDPR注意事项
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# 目标的GDPR注意事项{#gdpr-considerations-for-destinations}

本页概述了合作伙伴在信息可用时直接提供的信息，以及与Audience Manager实践相关的任何含义。 对进行这些更新的合作伙伴而言，关键影响是2018年5月25日生效的GDPR（一般数据保护规定）和新的IAB GDPR透明度和同意框架（IAB框架）的结果。

Adobe合作伙伴拥有其业务流程，并可能会决定不时更新与Audience manager的集成要求。 我们正积极与Audience Manager合作伙伴生态系统合作，以便让客户了解变化。

## Audience manager合作伙伴更新- ID同步 {#partner-updates-id-syncs}

如下表所示，一些合作伙伴已更改了与Audience manager的集成要求，以包含基于IAB框架的支持，以符合GDPR标准。

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>合作伙伴名称 </p> </th> 
   <th colname="col2" class="entry"> <p>预期影响 </p> </th> 
   <th colname="col3" class="entry"> <p>更改的状态 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Found/DataX </p> </td> 
   <td colname="col2"> <p>合作伙伴会删除欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>2018年5月22日以来的现场直播 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>交易台 </p> </td> 
   <td colname="col2"> <p>合作伙伴会删除欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未生效 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>合作伙伴会删除欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未生效 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>合作伙伴会删除欧盟用户的ID同步 </p> </td> 
   <td colname="col3"> <p>尚未生效 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI更新- Yahoo/Found/DataX集成 {#ui-update}

除了对上述IAB框架的更新之外，Yahoo/Andom/DataX还为其分类和受众API添加了新参数 **gdpr****和** gdpr_mode。 他们的参数告知Yahoo/Founce/DataX他们有权作为数据处理者或作为数据管理者处理特定段。 因此，将区段发送到Yahoo/Ansom/DataX目标的Audience manager客户必须根据与Andom的协议指定相应的参数（处理者或控制者）。

请联系您的顾问或客户关怀以设置正确的参数。 除非我们收到请求此更新的书面通信，否则Adobe不能代表客户进行此更新。 请联系您的Yahoo/Fousm/DataX代表，了解这些参数的完整定义。

## 具有取消细分功能的Audience manager合作伙伴 {#aam-partners-with-unsegmentation}

为了帮助客户自动执行GDPR请求，Audience manager通过向激活合作伙伴发送取消细分（或删除细分）信息，通知他们有关数据主体删除请求的信息。

但是，我们的一些激活合作伙伴：

1. 无法支持取消细分Adobe和／或
1. 无法在30天内以最频繁的方式接收我们的更新。

在这些情况下，您无法通过Audience manager以自动方式向激活合作伙伴发送删除请求。 下载我们 [的Partner excel表](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx) ，了解哪些Audience manager激活合作伙伴支持取消细分。
