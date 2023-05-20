---
description: 大量建立可讓您透過單一操作建構多個資料來源、衍生訊號、區段、特徵和其他專案。 依照這些指示進行大量建立請求。
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: 批量创建
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# 批量创建{#bulk-create}

大量建立可讓您透過單一操作建構多個資料來源、衍生訊號、區段、特徵和其他專案。 依照這些指示進行大量建立請求。

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[RBAC群組許可權](../../features/administration/administration-overview.md) 指派於 [!DNL Audience Manager] UI遵循以下規範： [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>請勿在大量建立請求中混用物件型別。 每個物件的標題都是唯一的，無法合併。 清除工作表，並針對不同料號提出個別請求。

若要大量建立物件，請開啟 [!UICONTROL Bulk Management Tools] 工作表和：

1. 按一下 **[!UICONTROL Headers]** 定位並複製您要新增之專案的「建立標題」。
2. 按一下 **[!UICONTROL Create]** 標籤。
3. 將建立標題貼到更新工作表的第一列。
4. 根據標題標籤，將您要變更的資料貼上或輸入至對應的欄。
5. 在工作表工具列中，按一下符合您要更新之料號的「建立」按鈕。
此動作會開啟 [!UICONTROL Account Information] 對話方塊。
6. 提供必要的 [登入資訊](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) 並按一下 **[!UICONTROL Submit]**.

工作表會建立 [!UICONTROL Results] 欄。 此 [!UICONTROL Results] 欄會傳回成功操作的JSON回應。 請參閱 [REST API](../../api/rest-api-main/rest-api-main.md) 例如。 在輸入資料之前，您大量建立的工作表應該看起來類似下列範例。 請注意，此處不顯示所有不同的建立選項。 其中包含的資訊可協助您瞭解完整工作表的外觀。

![](assets/cretetraits.png)

如果大量更新傳回錯誤或失敗，請參閱 [大量管理工具的疑難排解](../../reference/bulk-management-tools/bulk-troubleshooting.md).
