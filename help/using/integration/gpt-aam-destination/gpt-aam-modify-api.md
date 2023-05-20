---
description: 新增if陳述式，在呼叫Google Publisher Tag .setTargeting方法之前檢查Audience ManagerCookie。
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: 修改 GPT setTargeting API 调用
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 7%

---

# 修改GPT `setTargeting` API呼叫 {#modify-the-gpt-settargeting-api-call}

Audience Manager新增if陳述式以在呼叫 [!DNL Google Publisher Tag] `.setTargeting` 方法。

## 使用檢查Audience ManagerCookie `IF` 陳述式

此 `.setTargeting` 方法會從Audience Manager目的地Cookie和不重複使用者ID Cookie ( `aam_uuid`)。 但是，如果 `.setTargeting` 之前叫用的次數 [!UICONTROL DIL] 寫入這些Cookie，或Cookie是空的，您可能會在頁面載入時看到錯誤。 為協助避免此問題，請換行 `.setTargeting` 中的方法 `if` 檢查這些Cookie的陳述式。 若未設定，此陳述式會防止 `.setTargeting` 不呼叫 `AamGpt` 函式。

### `IF` 陳述式程式碼範例

在此範例中，Audience Manager目的地Cookie名稱為 `Sample`. 在Audience Manager使用者介面中建立目的地Cookie時，請設定此名稱。 [!UICONTROL DIL] 設定 `aam_uuid` Cookie和名稱無法變更。

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>視您想要與整合的方式而定 [!DNL Google Ad Manager]，您只需要上述程式碼範例中的部分行：
>
>* 使用者端整合：僅使用第1-3行。
>* 伺服器端整合：不需要任何行。
>* 擷取 [!DNL Google Ad Manager] 用於報告的記錄檔 [!DNL Audience Manager]：僅使用第4-6行。 此程式碼會插入 `aam_uuid` Cookie放入記錄中，以便擷取它們以用於報表。


### `AamGpt` 函式和資料型別

定義中使用的關鍵變數 `if` 陳述式。

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 函数 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>傳回索引鍵 — 值區段配對中的索引鍵。 例如，如果您的機碼值組包含 <code> color=blue </code>，這會傳回 <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>字串陣列 </p> </td> 
   <td colname="col3"> <p>傳回陣列中的值，例如 <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>傳回Audience Manager的使用者ID，例如 <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [创建 GPT 目标](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher Tag 的 Audience Manager 代码](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

