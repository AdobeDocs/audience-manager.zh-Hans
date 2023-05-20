---
description: 使用設定檔連結裝置圖表進行區段重新定位和個人化區段資格的Recommendations和使用案例。
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: 配置文件关联设备图用例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 8%

---

# 配置文件关联设备图用例 {#profile-link-device-graph-use-cases}

Recommendations和使用案例，用於區段重新定位和個人化的區段資格，具有 [!UICONTROL Profile Link Device Graph].

## 推荐 {#recommendations}

考慮 [!UICONTROL Profile Link] 適用於下列行銷活動的裝置圖表：

* 跨其數位屬性進行高階驗證。 使用 [外部裝置圖表選項](merge-rule-definitions.md#device-options) 如果您的已驗證使用者數量很少。
* 需要精確鎖定已知對象。 此 [!UICONTROL Profile Link Device Graph] 使用第一方已驗證的資料建置。
* 跨已驗證和未驗證狀態即時鎖定已知對象。

![](assets/merge-rule-triangle2.png)

## 跨裝置目標定位 {#cross-device-personalization}

假設John擁有三部裝置，並經常用來搜尋假日套餐優惠：他的筆記型電腦([!DNL Device 1])，他的智慧型手機([!DNL Device 2])，以及他的平板電腦([!DNL Device 3])。 不過，John會使用裝置搜尋套件交易的不同專案：

* 他用筆記型電腦搜尋機票；
* 他用智慧手機搜尋旅館；
* 他使用平板電腦搜尋導覽。

即使John並未在上述三個裝置上進行驗證，請使用 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** 規則，假日套件提供者可以將這些裝置與John已驗證的設定檔建立關聯，假設他是最後驗證所有三個裝置的人員。

![last-device-graph](assets/last-device-graph.png)

由於Audience Manager會針對區段來限定參與設定檔合併的每個裝置設定檔，因此所有三個裝置設定檔都會分段。 此 [!UICONTROL Profile Link Device Graph] 允許Audience Manager檢視所有三個裝置的行為，並讓每個裝置符合沒有單一裝置設定檔本身符合的區段。

此 [!UICONTROL Profile Merge Rule] 可讓行銷人員根據使用者活動（而非個別裝置活動），為所有人擁有的所有裝置提供一致的體驗。

![跨裝置個人化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部设备图用例](external-graph-use-cases.md)
>* [配置文件合并规则的一般用例](merge-rule-targeting-options.md)
>* [設定檔合併規則常見問題集](../../faq/faq-profile-merge.md)

