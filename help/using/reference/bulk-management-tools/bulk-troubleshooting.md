---
description: 當工作表傳回錯誤或您的大量請求失敗時，該怎麼做。
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: 批量管理工具疑难解答提示
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 4%

---

# 批量管理工具疑难解答提示{#troubleshooting-tips-for-bulk-management-tools}

當工作表傳回錯誤或您的大量請求失敗時，該怎麼做。



<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[RBAC群組許可權](../../features/administration/administration-overview.md) 指派於 [!DNL Audience Manager] UI遵循以下規範： [!UICONTROL Bulk Management Tools].

網路流量大、伺服器使用量及大型資料集等因素，都可能導致大量請求失敗或逾時。 如果發生問題，工作表會停止寫入資料並顯示錯誤訊息。 發生此情況時，您應該：

* 閱讀錯誤訊息。
* 修正問題。
* 刪除所有已更新的列。
* 請再次嘗試大量請求。

## 驗證錯誤、長時間延遲或無回應行為 {#delays-behavior}

下表列出使用工作表提出大量請求時可能會遇到的一些常見問題。 請嘗試使用建議的解決方案來修正這些問題。 如果建議的解決方案無法解決問題，您應該儲存工作、重新啟動電腦，然後再次嘗試請求，而不啟動或使用其他應用程式。

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 故障 </th> 
   <th colname="col2" class="entry"> 解决方案 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>驗證錯誤</b> </td> 
   <td colname="col2"> 
    <b>更新至最新版Microsoft Excel</b>：發行新版Microsoft Excel時，若您使用舊版，您可能會在「大量管理」工作表中遇到驗證錯誤。 更新至最新版Microsoft Excel以解決驗證錯誤。
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>長時間延遲</b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b>關閉相容性模式</b>：檢查您是否在Microsoft Excel的相容性模式中開啟其他工作表。 相容性模式可以增加執行時間。 請關閉您在此模式中可能開啟的任何試算表，然後再次嘗試您的大量請求。 </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b>系統資源</b>：有限的系統資源造成長時間延遲。 在提出大量請求之前，請嘗試關閉所有其他程式。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>無回應</b> </td> 
   <td colname="col2">如果您按一下動作按鈕，沒有任何反應： 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">請確定您有正確的選取動作標題集。 </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">請確定您對複製的頁首使用正確的工作表。 </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">檢查您要在大量作業中使用的資料位置。 所有標頭都以欄A、列1開頭。 所有資料都會進入對應的標題中，從欄A第2列開始（緊接在標題下方）。 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 错误消息

有時候，進行大量變更時，您會收到錯誤訊息。 若要解譯錯誤訊息，請參閱 [已定義的回應代碼](/help/using/api/rest-api-main/aam-api-getting-started.md) （位於我們的API檔案中）。
