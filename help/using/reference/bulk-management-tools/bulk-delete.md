---
description: 大量刪除可讓您透過單一操作移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目的地。 請依照這些指示提出大量刪除請求。
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: 批量删除
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# 批量删除{#bulk-delete}

大量刪除可讓您透過單一操作移除多個區段、特徵、資料夾、衍生訊號、資料來源、模型和目的地。 請依照這些指示提出大量刪除請求。

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC群組許可權](../../features/administration/administration-overview.md) 指派於 [!DNL Audience Manager] UI遵循以下規範： [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>如果您有對應至目的地的區段，則大量刪除目的地對應將會失敗。 在嘗試大量刪除目的地之前，請在使用者介面中從該目的地移除您的區段。 此外，特徵和區段資料夾必須空白，您才能將其刪除。

若要刪除多個專案，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Headers]** 定位並複製您要新增之專案的「建立標題」。
2. 按一下 **[!UICONTROL Delete]** 標籤。
3. 將刪除標題貼入更新工作表的第一列。
4. 在標頭下方的欄中，貼上或輸入您要刪除之物件的ID。
5. 提供必要的 [登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 並按一下 **[!UICONTROL Submit]**.

   工作表會建立 [!UICONTROL Results] 欄。 此 [!UICONTROL Results] 欄會傳回一則訊息，指出該專案是否已刪除，或是錯誤訊息。
在輸入資料之前，您的大量更新工作表應該看起來類似下列：

![](assets/delete.png)

如果大量更新傳回錯誤或失敗，請參閱 [大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md).
