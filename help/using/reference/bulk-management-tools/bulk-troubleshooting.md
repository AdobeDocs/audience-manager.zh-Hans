---
description: 当工作表返回错误或批量请求失败时该怎么做。
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: 批量管理工具的疑难解答提示
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# 批量管理工具的疑难解答提示{#troubleshooting-tips-for-bulk-management-tools}

当工作表返回错误或批量请求失败时该怎么做。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[接受在](../../features/administration/administration-overview.md) UI中分配的[!DNL Audience Manager]RBAC组权限[!UICONTROL Bulk Management Tools]。

网络流量大、服务器使用率高和数据集大等因素可能会导致批量请求失败或超时。 如果出现问题，工作表将停止写入数据并显示错误消息。 发生这种情况时，您应：

* 阅读错误消息。
* 修复问题。
* 删除所有已更新的行。
* 请重试批量请求。

## 身份验证错误、长时间延迟或无响应行为 {#delays-behavior}

下表列出了在使用工作表批量请求时可能遇到的一些常见问题。 请尝试使用建议的解决方案修复这些问题。 如果建议的解决方案不能解决问题，您应该保存工作，重新启动计算机，然后再次尝试请求，而不启动或处理其他应用程序。

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 故障 </th> 
   <th colname="col2" class="entry"> 解决方案 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>身份验证错误</b> </td> 
   <td colname="col2"> 
    <b>更新到最新版本的Microsoft Excel</b>：如果发布新版本的Microsoft Excel并且您使用的是旧版本，则批量管理工作表中可能会遇到身份验证错误。 请更新至最新版本的Microsoft Excel以解决身份验证错误。
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>长延迟</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>关闭兼容模式</b>：检查您是否在Microsoft Excel的兼容模式下打开了其他工作表。 兼容模式会增加运行时间。 请关闭在此模式下可能打开的任何电子表格，然后再次尝试批量请求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系统资源</b>：有限的系统资源导致长时间延迟。 尝试在批量请求之前关闭所有其他程序。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>无响应</b> </td> 
   <td colname="col2">如果单击某个操作按钮，则不会发生任何情况： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">确保您有正确的选择操作标头集。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">确保为复制的题头使用正确的工作表。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">检查要在批量操作中使用的数据的位置。 所有标题都以列A行1开头。 所有数据都进入相应的标题中，从列A的第2行开始（紧接在标题下方）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 错误消息

有时，在进行批量更改时可能会收到错误消息。 要解释错误消息，请参阅API文档中的[定义的响应代码](/help/using/api/rest-api-main/aam-api-getting-started.md)。
