---
description: 当工作表返回错误或批量请求失败时，该怎么办。
seo-description: 当工作表返回错误或批量请求失败时，该怎么办。
seo-title: 批量管理工具疑难解答提示
solution: Audience Manager
title: 批量管理工具疑难解答提示
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 5%

---

# 批量管理工具疑难解答提示{#troubleshooting-tips-for-bulk-management-tools}

当工作表返回错误或批量请求失败时，该怎么办。



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[在UI中](../../features/administration/administration-overview.md) 分配的RBAC组 [!DNL Audience Manager] 权限将在中得 [!UICONTROL Bulk Management Tools]到。

网络流量大、服务器使用量大和数据集大等因素可能会导致批量请求失败或超时。 如果出现问题，工作表将停止写入数据并显示错误消息。 发生此情况时，您应：

* 阅读错误消息。
* 解决问题。
* 删除所有已更新的行。
* 再次尝试批量请求。

## 身份验证错误、长延迟或无响应行为{#delays-behavior}

下表列出了在使用工作表进行批量请求时可能遇到的一些常见问题。 尝试使用推荐的解决方案来解决这些问题。 如果建议的解决方案没有解决问题，您应保存您的工作，重新启动计算机，然后重试请求，而无需启动或使用其他应用程序。

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 故障 </th> 
   <th colname="col2" class="entry"> 解决方案 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>验证错误</b> </td> 
   <td colname="col2"> 
    <b>更新至最新版本的Microsoft Excel</b>:当发布新版本的Microsoft Excel并且您使用的是旧版本时，您可能会在批量管理工作表中遇到身份验证错误。更新至最新版本的Microsoft Excel以解决身份验证错误。
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>长时间延迟</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>关闭兼容性模式</b>:检查您是否在Microsoft Excel的兼容模式下打开了其他工作表。兼容性模式可以增加运行时间。 关闭在此模式下可能打开的任何电子表格，然后重试批量请求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系统资源</b>:系统资源有限，导致了长时间的延迟。在发出批量请求之前，请尝试关闭所有其他程序。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>无响应</b> </td> 
   <td colname="col2">如果单击操作按钮，则不会发生任何情况： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">确保为选择操作设置了正确的标头集。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">确保为复制的标题使用正确的工作表。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">检查要在批量操作中使用的数据的位置。 所有标题都从A列第1行开始。 所有数据都会进入相应的标题中，从第A列第2行开始（紧靠标题下方）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 错误消息

有时，进行批量更改时可能会收到错误消息。 要解释错误消息，请参阅API文档中的[定义的响应代码](/help/using/api/rest-api-main/aam-api-getting-started.md) 。
