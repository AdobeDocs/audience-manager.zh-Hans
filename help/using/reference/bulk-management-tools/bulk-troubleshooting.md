---
description: 当工作表返回错误或批量请求失败时应执行的操作。
seo-description: 当工作表返回错误或批量请求失败时应执行的操作。
seo-title: 批量管理工具故障排除提示
solution: Audience Manager
title: 批量管理工具故障排除提示
uuid: 550908a1-e24 e-4f31-954b-7132c0 c8 dc3 e
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Troubleshooting Tips for Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

当工作表返回错误或批量请求失败时应执行的操作。



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

大量网络流量、服务器使用情况和大型数据集等因素可能导致批量请求失败或超时。如果存在问题，工作表会停止编写数据并显示错误消息。发生这种情况时，您应该：

* 阅读错误消息。
* 解决问题。
* 删除已更新的所有行。
* 再次尝试批量请求。

## Long delays or unresponsive behavior {#delays-behavior}

下表列出了在使用工作表进行批量请求时可能遇到的一些常见问题。尝试解决这些建议的解决方案问题。如果推荐的解决方案未解决问题，您应保存您的工作，重新启动计算机，并在不启动或使用其他应用程序的情况下再次尝试请求。

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 故障 </th> 
   <th colname="col2" class="entry"> 解决方案 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>长时间延迟</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>关闭兼容性模式</b>：检查您是否在Microsoft Excel兼容性模式下打开其他工作表。兼容模式可增加运行时。关闭在此模式下打开的任何电子表格，然后再次尝试批量请求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系统资源</b>：系统资源有限会导致长时间延迟。在批量请求之前，请尝试关闭所有其他计划。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>无响应</b> </td> 
   <td colname="col2">如果单击动作按钮，则不会发生任何情况： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">确保选择操作的标题正确。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">确保您正在使用复制的标题的正确工作表。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">检查要批量操作中使用的数据的位置。所有标题都从A列第行开始。所有数据都转到相应的标题，从A第A行(紧靠标题下方)开始。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

