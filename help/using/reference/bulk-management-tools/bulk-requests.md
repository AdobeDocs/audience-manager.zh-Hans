---
description: 大量請求會傳回您可以與「更新」、「建立」、「預估」和「刪除」工作表中的不同標頭一起使用的資料。
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: 批量请求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---

# 批量请求{#bulk-requests}

大量請求會傳回您可以與「更新」、「建立」、「預估」和「刪除」工作表中的不同標頭一起使用的資料。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC群組許可權](../../features/administration/administration-overview.md) 指派於 [!DNL Audience Manager] UI遵循以下規範： [!UICONTROL Bulk Management Tools].

此 [!UICONTROL Request] 工作表沒有自己的欄標題集，您不需要將ID複製到任何欄。 而是會根據您在工具列中按一下之動作按鈕傳回資料。 此外，選用的報表功能也會傳回畫素引發的頻率計數，以及數個固定時間間隔的不重複使用者計數。

若要提出大量請求，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Request]** 標籤。
2. 在工作表頂端的工具列中，按一下與您要使用之資料對應的請求按鈕。 您可以要求：

   * 演演算法模型
   * 資料來源
   * 衍生訊號
   * 目的地對應
   * 演演算法、規則型和已上線的特徵
   * 区段
   * 特徵和區段資料夾ID

   此 [!DNL Audience Manager] API會將大量資料寫入回 [!UICONTROL Request] 工作表。

>[!NOTE]
>
>在您的結果中， `createTime` 和 `updateTime` 欄會以指數標籤法傳回資料。 基礎日期/時間戳記會以UNIX UTC時間記錄。 目前，工作表無法傳回可讀格式的日期/時間戳記。

如果大量更新傳回錯誤或失敗，請參閱 [大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md).
