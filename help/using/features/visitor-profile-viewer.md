---
description: 使用「訪客資料檢視器」可顯示目前瀏覽器之使用者資料目前的狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其SID、名稱、有關如何實現訪客特徵（第一方或第三方）的詳細資訊、實現日期和實現頻率。 對於每個區段，您可以檢視其SID、名稱和區段會籍日期。 您也可以檢視其他Audience Manager設定檔ID (UUID)的訪客設定檔。 訪客資料檢視器有助於進行疑難排解。
keywords: 位置；位置引數
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: 访客配置文件查看器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---

# 访客配置文件查看器 {#visitor-profile-viewer}

使用 [!UICONTROL Visitor Profile Viewer] 顯示目前瀏覽器的使用者個人資料目前狀態，包括其特徵和區段。 對於每個特徵，您可以檢視其 [!UICONTROL SID]、名稱、訪客特徵實現方式（第一方或第三方）的相關詳細資訊、實現日期和實現頻率。 對於每個區段，您可以檢視其 [!UICONTROL SID]、名稱和區段會籍日期。 您也可以檢視其他Audience Manager設定檔ID的訪客設定檔([!UICONTROL UUID])。 此 [!UICONTROL Visitor Profile Viewer] 有助於疑難排解。

>[!NOTE]
>
>* 存取需要 [!UICONTROL Administrator] 許可權。
>* 使用者介面中會延遲24小時才顯示已實現區段和已上線特徵的資訊。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 单击 **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *（可選）* 按一下特徵名稱，將該特徵顯示在 [!UICONTROL Trait Builder].

   如需詳細資訊，請參閱 [特徵](../features/traits/trait-details-page.md).

1. *（可選）* 按一下區段名稱，將該區段顯示在 [!UICONTROL Segment Builder].

   如需詳細資訊，請參閱 [區段](../features/segments/segments-purpose.md).

1. *（條件式）* 在 **[!UICONTROL UUID]** 方塊中，指定另一個Audience Manager設定檔ID，然後按一下 **[!UICONTROL Refresh]** 以檢視該使用者的特徵和區段。
