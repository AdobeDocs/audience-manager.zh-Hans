---
description: 取消細分說明取消資格並從區段中移除裝置設定檔的程式。 您能否從區段移除裝置設定檔，取決於用來建立設定檔合併規則的裝置選項。
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: 配置文件合并规则和设备取消分段过程
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 5%

---

# 配置文件合并规则和设备取消分段过程 {#profile-merge-rules-and-device-un-segmentation-processes}

取消細分說明取消資格並從區段中移除裝置設定檔的程式。 您能否從區段移除裝置設定檔取決於用來建立 [!UICONTROL Profile Merge Rule].

## 可用的裝置選項 {#device-options}

提醒您， [!UICONTROL Device Options] 可從以下網址取得： [!UICONTROL Profile Merge Rules Setup] 區段(當您建立或編輯 [!UICONTROL Profile Merge Rule].

## 目前的裝置設定檔選項和裝置取消細分 {#current-device-profile-options}

**[!UICONTROL Device Profile]** 是的預設裝置設定檔選項 [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] 符合下列條件時，可以從區段中移除裝置設定檔： [!UICONTROL Profile Merge Rule] 使用 **[!UICONTROL Device Profile]** 選項。 在這些情況下，取消細分會在下列情況發生：

* 裝置設定檔已停用120天。 每週資料清理程式會從您的區段中移除非使用中裝置設定檔。
* 裝置不再符合區段的資格，因為裝置設定檔的更新或變更會取消其資格。 當區段資格標準變更，或您套用 [!DNL AND NOT] 區段規則的運運算元，或指定 [造訪間隔和頻率](../segments/recency-and-frequency.md) 使用小於/等於設定的條件。 使用案例的說明請參閱 [即時跨裝置隱藏](instant-cross-device-suppression.md) 說明檔案。

![僅限裝置](assets/device-only.png)

## 沒有裝置選項和裝置取消細分 {#no-device-option}

[!DNL Audience Manager] 可移除區段中的跨裝置ID，當 [!UICONTROL Profile Merge Rule] 使用 **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** 選項。 在這些情況下，當跨裝置ID不再符合區段資格時，就會發生取消分段，因為跨裝置設定檔的更新或變更會取消其資格。 當區段資格標準變更，或您套用 [!UICONTROL AND NOT] 區段規則的運運算元，或指定 [造訪間隔和頻率](../segments/recency-and-frequency.md) 使用小於/等於設定的條件。 使用案例的說明請參閱 [即時跨裝置隱藏](instant-cross-device-suppression.md) 說明檔案。

![](assets/current-no-device.png)

## 裝置圖表選項和裝置取消細分 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] 符合下列條件時，可以從區段中移除多個裝置設定檔： [!UICONTROL Profile Merge Rule] 會使用裝置圖表選項。 當裝置的合併設定檔從裝置圖表不再符合區段資格時，就會發生取消分段，因為更新或變更此合併設定檔會使它不再符合區段的資格。 當區段資格標準變更，或您套用 [!UICONTROL AND NOT] 區段規則的運運算元，或指定 [造訪間隔和頻率](../segments/recency-and-frequency.md) 使用小於/等於設定的條件。 使用案例的說明請參閱 [即時跨裝置隱藏](instant-cross-device-suppression.md) 說明檔案。

>[!NOTE]
>
>**區段評估和取消資格的100個裝置限制**.
>透過使用裝置圖表的「設定檔合併規則」評估區段時，Audience Manager可合併最多100部裝置。 Audience Manager會評估目前的裝置，以及透過連結至目前裝置的最多99個裝置。 [已驗證的設定檔](../../reference/visitor-authentication-states.md) （跨裝置ID）。 如果發出取消細分訊號，則會從目的地的區段中移除目前的裝置和其他裝置。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [即时跨设备抑制](instant-cross-device-suppression.md)

