---
description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP 地址模糊处理
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 16%

---

# IP 地址模糊处理 {#ip-obfuscation}

使用此功能來模糊化Audience Manager中收集的IP位址。

## 概述和方法 {#overview-and-methodology}

由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。

### IP模糊化方法

Adobe Audience Manager遵循「設計隱私權」原則，允許客戶透過UI啟用IP模糊化功能（針對全球各地理區域或特定國家/地區皆可）。 啟用此設定時，將IP位址擷取到Audience Manager中時，會立即捨棄該IP位址的最後八位元（最後一部分）。 Audience Manager會在處理前（包括任何選擇性地理查閱或記錄IP位址之前）捨棄此IP位址部分。 例如：

* 模糊化之前： `255.255.255.255`
* 模糊化之後： `255.255.255.0`

另請參閱收集我們的IP位址和IP位址模糊化 [資料隱私權區段](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP位址模糊化需求 {#ip-obfuscation-requirements}

IP位址模糊化僅適用於Audience Manager管理員帳戶。 另請參閱 [建立使用者](/help/using/features/administration/administration-overview.md#create-users) 以瞭解如何為使用者指派管理員許可權。

>[!NOTE]
>
> 由於Audience Manager處理了大量的資料，IP模糊化變更最多可能從您更新設定起需要4小時才會生效。

## 設定IP位址模糊化 {#configure-ip-obfuscation}

請依照下列步驟設定IP位址模糊化。

1. 使用管理員帳戶登入Audience Manager，並前往 **管理>隱私權**.
2. 選擇您要使用的IP模糊化型別。
   1. **模糊化所有IP位址：** 選取此選項可讓Audience Manager模糊化所有訪客IP位址的最後一個八位元，無論其來源地區為何。
   2. **模糊化特定國家的IP位址：** 選取此選項，可讓Audience Manager模糊化特定國家/地區的訪客IP位址的最後八位元。 使用 **國家/地區清單** 或對應的 **搜尋** 欄位以尋找要啟用IP模糊化的國家/地區，然後按一下+圖示以將其新增至 **已選取進行模糊化** 清單。 一旦您將所有必要國家/地區新增至 **已選取進行模糊化** 清單，按一下 **儲存**.

![](assets/ip-obfuscation.png)

## 停用IP位址模糊化 {#disable-ip-obfuscation}

若要全域停用IP位址模糊化，請前往 **管理>隱私權**，選取 **不要模糊化IP位址**，然後按一下 **儲存**.

若要針對特定國家/地區停用IP位址模糊化功能，請在 **已選取進行模糊化** 清單，然後按一下它們對應的 **X** 圖示。 按一下 **儲存** 完成時。

## 相关概念 {#related-concepts}

* [数据隐私](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP位址模糊化影片示範
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
