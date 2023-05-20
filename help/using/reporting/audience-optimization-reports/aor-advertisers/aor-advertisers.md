---
description: 廣告商的Audience Optimization可協助您識別在付費媒體行銷活動中Audience Manager區段的潛在效用機會。 這些報表結合記錄層級促銷活動績效資料與Audience Manager區段量度，以提供以區段為中心的最佳化和有效管道組合資訊。
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: 适用于广告商的 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 1%

---

# [!UICONTROL Audience Optimization] 適用於廣告商{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 廣告商適用的可協助您識別在付費媒體行銷活動中Audience Manager區段的潛在效用機會。 這些報表結合記錄層級行銷活動績效資料與Audience Manager [!UICONTROL segment] 提供相關量度，以提供區段導向的最佳化及有效的管道組合資訊。

## 資料擷取方法 {#data-ingestion-methods}

您可以將資料傳送至 [!DNL Audience Manager] 以便透過上述任一種方法用於這些報表。 有時候，客戶會透過兩種方法傳送資料。 這有助於確保您的報表包含有關訪客最全面且準確的資訊。 若要使用 [!UICONTROL Audience Optimization] 報告，您的事件呼叫必須包括 *全部* 中所列引數的 [中繼資料檔案的概述與對應](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 說明檔案。 您可以透過下列方法傳送資料。

* 畫素呼叫：將必要的中繼資料引數傳遞至 [!DNL Audience Manager] 另請參閱 [透過畫素呼叫擷取行銷活動的點按資料](../../../integration/media-data-integration/click-data-pixels.md) 和 [透過畫素呼叫擷取行銷活動的曝光資料](../../../integration/media-data-integration/impression-data-pixels.md).

* 資料檔案：如果您想要使用這些報表來分析您自己的資料，或來自未整合之來源的資料 [!DNL Audience Manager]，您需要為該資料建立和上傳資料和中繼資料檔案。 如需詳細資訊，請參閱 [Audience Optimization報表的資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 和 [Audience Optimization報表的資料和中繼資料檔案](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

您可以檢視的報表型別取決於 [!UICONTROL RBAC] 指派給您的群組。 另請參閱 [管理](../../../features/administration/administration-overview.md) 和 [建立群組](../../../features/administration/administration-overview.md#create-group) 以取得詳細資訊。

[!UICONTROL RBAC] 群組必須設定一些資料來源，才能檢視 [!UICONTROL Audience Optimization] 報表。 您的 [!DNL Audience Manager] 顧問將設定這些 [!UICONTROL data sources] 敬請參考使用。 更多內容 [!UICONTROL data sources] 在每個 [!UICONTROL RBAC] 使用者群組，這些群組成員可存取的資料越多。 您的顧問至少會設定其中一個 [!UICONTROL data sources]：

* 广告商 [!UICONTROL data source ]
* 品牌 [!UICONTROL data source]
* 平台 [!UICONTROL data source]

屬於多個使用者的使用者 [!UICONTROL RBAC] 使用者群組可在每個群組的檢視之間切換。 顯示的資料將會更新以符合所選群組。 如果您的公司不使用 [!UICONTROL RBAC]，所有使用者都將擁有管理員許可權，並可存取所有 [!UICONTROL data sources] （轉換群組）。

## 轉換群組 {#conversion-groups}

在 [!UICONTROL Audience Optimization] 報表、 **[!UICONTROL Conversion Groups]** 同義詞 [!UICONTROL data sources] 至少包含一個轉換特徵。 [!UICONTROL Data sources] 不包含至少一個轉換特徵的專案不會出現在 [!UICONTROL Audience Optimization] 報表。 您可以在下列位置檢視轉換群組的轉換特徵： [回報的轉換特徵](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 報告。
