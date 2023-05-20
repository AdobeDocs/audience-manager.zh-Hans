---
description: Adobe 通过选择加入功能和 IAB 透明度与同意框架 (TCF) 支持，为您提供用于管理和传达用户所做的隐私选择的方法。本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: 适用于 IAB TCF 的 Audience Manager 插件
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '2367'
ht-degree: 34%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## 概述

您對使用者的隱私權義務中，其中一個重要面向是取得並傳達使用者對其個人資料的使用方式（即「目的」）和使用者（即「公司」）所做的選擇。

Adobe 通过[选择加入功能](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)和 [IAB 透明度与同意框架 (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 支持，为您提供用于管理和传达用户所做的隐私选择的方法。

本文介绍了支持 IAB TCF 的 Audience Manager 用例，以及在 Audience Manager 中实施 IAB TCF 支持的方法。

>[!IMPORTANT]
>
>Audience Manager註冊於 [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) 廠商ID為565。

适用于 IAB TCF 的 Audience Manager 插件利用了[选择加入功能](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html)，而该功能又是 [ Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html) 库的一部分。

## 范围和限制 {#scope-and-limitations}

作为使用 Audience Manager 的出版商或广告商，您可以根据 IAB TCF 向 Audience Manager 传达用户所做的选择。

>[!IMPORTANT]
>
>IAB TCF法規僅適用於位於歐洲經濟區的訪客。

Audience Manager可協助您尊重使用者的隱私權選擇，並提供簡單的方式將這些選擇傳達給與您合作的所有合作夥伴。

目前，Audience Manager 不支持：

* 移动设备工作流程；
* 將同意附加至區段匯出。

## 将 升级至 [!DNL IAB TCF v2.0] {#upgrading}

正在升級其產品的客戶 [!DNL Audience Manager Plug-in for IAB TCF] 實作來源 [!DNL IAB TCF] v1.1至 [!DNL IAB TCF] v2.0，或啟用 [!DNL IAB TCF] v2.0應首次全部遵循以下所述的先決條件及實作指引。

## 先决条件 {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager支援IAB TCF v2.0。
>
>IAB TCF v1.1支援將於2020年8月15日終止。
>
> 如果客戶希望繼續使用適用於IAB TCF的Audience Manager外掛程式進行同意管理，請升級至最新版本的 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 以取得持續支援。
>
> 升級至最新版本後 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 版本，不再支援IAB TCF v1.1同意字串，因此請務必在升級至最新的ECID版本前更新CMP。

您必須符合下列先決條件，才能使用含Audience Manager的IAB TCFAudience Manager外掛程式：

1. 您必须使用 Adobe Experience Platform Identity Service (ECID) 版本 5 或更高版本。[下载](https://github.com/Adobe-Marketing-Cloud/id-service/releases) ECID 的最新版本。
2. 您必須使用Audience Manager [!DNL Data Integration Library] (DIL) 9.0版或更新版本，可下載自 [此處](https://github.com/Adobe-Marketing-Cloud/dil/releases). 请阅读 [Audience Manager 中的 DIL 文档](../../dil/dil-overview.md)。我們建議使用 [Adobe Audience Manager標籤擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 以最簡單的DIL實作Audience Manager。
3. 或者，如果您使用 [!DNL Server-Side Forwarding] (SSF)若要將資料匯入Audience Manager，您必須升級至AppMeasurement的最新版本。 使用 [Analytics 代码管理器](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html)下载 AppMeasurement。
4. 您必須使用與IAB TCF v2.0整合且已向IAB TCF註冊的同意管理平台(CMP) （商業版或個人版）。 请参阅[在 IAB 框架内注册的 CMP](https://iabeurope.eu/cmp-list/)。

>[!WARNING]
>
>如果您使用不支援IAB TCF v.2.0的同意管理平台(CMP)，Audience Manager會自動傳送 `gdpr=0` 引數進行ID同步，即使您的訪客位於歐盟也是如此。 若要判斷您的GDPR驗證是否作用中，建議您向同意管理平台(CMP)確認其支援IAB TCF v2.0。

## 建议和实施方式 {#recommendations}

要在 Audience Manager 中启用 IAB TCF 支持，请阅读我们关于[如何通过选择加入来设置 IAB](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html) 的文档。

最簡單的方法是使用 [Adobe Experience Platform標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 新增 [!DNL ECID Opt-in] 在您的屬性上。 閱讀檔案： [ECID選擇加入擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) 以瞭解如何設定標籤擴充功能。

## 使用 IAB 框架时的用户选择工作流程 {#user-choice-workflow}

在访问 Web 资产时，用户可以选择出版商以及与之合作的第三方供应商如何使用其数据。

使用者以下列形式提供他們的選擇 *同意* 和 *合法利益* 以供IAB使用 *協力廠商的產品* 已註冊至全域廠商清單。

下图是向首次访问网站的访客显示的 CMP 对话框的一个示例。请记住，根据客户实施情况，此对话框可能会大不相同。

![CMP 对话框](assets/cmp-example.png)

IAB TCF v2.0中包含的各種用途和許可權的詳細資訊，請參閱 [IAB歐洲透明度與同意框架原則](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

使用者可針對用途和廠商的組合授予其同意或合法利益（如有）。 例如，使用者可以針對在裝置上儲存資訊、開發和改進產品授予同意，並且針對CMP顯示的所有第三方廠商授予同意。

或者，在另一個範例中，他們可以針對所有目的授予其同意或合法利益，但只向CMP顯示的幾個廠商授予同意或合法利益。

一旦使用者選取其隱私權選擇，該使用者選擇就會記錄在IAB TC字串中。 IAB TC字串會儲存已核准用途和廠商的組合，以及其他中繼資料資訊(請參閱 [IAB頁面](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) 以取得詳細資訊)。

在IAB TCF中註冊的每個廠商都會評估IAB TC字串，並根據使用者的隱私權選擇做出決策。 請記住，使用者的隱私權選擇在註冊IAB TCF的所有廠商中有效。

## Audience Manager所需的目的 {#aam-standard-purposes}

Audience Manager會針對以下用途評估儲存在IAB TC字串中的使用者選擇，這些用途定義於 [IAB歐洲透明度與同意框架原則](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **用途1**：儲存和/或存取裝置上的資訊；
* **用途10**：開發和改善產品；
* **特殊用途1**：確保安全性、防止詐騙和除錯。

>[!IMPORTANT]
>
>Audience Manager需要目的1和10的同意，加上廠商同意，才能部署Cookie，並初始化或執行ID同步。
>
>每 [IAB法規](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)，特殊目的1 （確保安全性、防止詐騙和除錯）一律同意，且使用者無法反對其操作。

## Audience Manager 的行为取决于用户是否授予同意 {#aam-behavior-consent}

根據IAB TC字串是否包含兩個用途的使用者同意（儲存和/或存取裝置上的資訊，以及開發和改善產品），Audience Manager的運作方式會有所不同。

我們也會檢查您在Audience Manager中使用之所有目的地的使用者同意，前提是這些目的地已向IAB TCF註冊。

| 当用户&#x200B;*表示同意*&#x200B;时，Audience Manager： | 当用户&#x200B;*拒绝同意*&#x200B;时，Audience Manager： |
|---|---|
| <ul><li>执行您请求的所有 Audience Manager 用例。</li><li>在ID同步中向第三方傳達同意(透過 `gdpr = 1` 和同意字串做為 `gdpr_consent` （在ID同步呼叫上）。</li><li>评估并遵循通过广告服务器像素传递的同意。</li><li>执行合作伙伴启动的 ID 同步。</li></ul> | <ul><li>在您的实例中不存储任何新的用户数据。这包括合作伙伴 ID、信号、特征或像素数据。</li><li>不启动第三方 ID 同步。</li><li>不执行合作伙伴启动的 ID 同步。</li><li>選擇退出使用者以進一步收集資料。</li></ul> |

## 出版商用例 {#publisher-use-case}

若實作適用於IAB TCF的Audience Manager外掛程式，您便不需要透過Adobe或其他第三方廠商的其他機制，維護您Web屬性的自訂同意管理程式碼。 下面的图像和步骤中介绍了相关用例。我们将从图像左侧开始介绍：

1. 用户访问您的某个 Web 资产。只要您使用最新版的 ECID 和 DIL 库（请参阅[先决条件](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)），就会触发选择加入流程。
2. Audience Manager 检查 IAB 流程是否适用 (`isIabContext=true`)。请参阅[建议和实施方式](aam-iab-plugin.md#recommendations)。
3. Audience Manager會檢查GDPR是否適用(`gdpr = 1`)以及您的Web屬性上是否有已向IAB TCF註冊的CMP。 例如，這適用於從歐盟造訪的使用者。 請注意，您身為發佈商，有責任設定GDPR標幟。
4. 如果GDPR適用，Audience Manager會檢查傳入的IAB TC字串 `gdpr_consent` 引數，以獲得必要的同意。 Audience Manager需要同意才能儲存和/或存取裝置上的資訊([IAB TCF用途1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))，開發和改良產品([IAB TCF用途10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes))以及Audience Manager廠商對於儲存、處理或啟用資料的同意。
5. 如果IAB TC字串存在且包含必要的同意，Audience Manager會將IAB TC字串傳遞至 [資料收集伺服器](../../reference/system-components/components-data-collection.md) (DCS)。
6. Audience Manager會透過設定 [demdex Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) ，然後會起始並執行第三方ID同步。
7. 或者，如果在步驟4中傳遞的IAB TC字串不包含所有必要的許可權，則Audience Manager不會收集、處理或啟用任何使用者資料，也不會執行或起始ID同步。 此外，它會從您合作的目的地選擇退出使用者。

>[!IMPORTANT]
>
>如果您正與需要IAB TCF引數的Audience Manager目的地合作夥伴合作，但您的網站上沒有支援IAB TCF的CMP，則Audience Manager會傳送 `gdpr=0` 在ID同步中。 這表示GDPR不適用於這些使用者。
>
> 如果不希望如此，您應該在Audience Manager中啟用IAB TCF功能，將適當的IAB TC字串傳送給目的地合作夥伴。



![出版商用例](assets/publisher-use-case.png)

## 广告商用例 {#advertiser-use-case}

Audience Manager 根据 IAB TCF 评估并遵循在[像素调用](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)中传递的同意。

畫素可由Audience Manager客戶放置在其合作夥伴頁面上，或放置於廣告伺服器中以包含在廣告回應中。 对于第一种情况，您的合作伙伴必须以编程方式检索同意参数并将其添加到像素，然后才能触发。对于第二种情况，广告服务器会将从供应方平台 (SSP) 或出版商广告服务器接收的同意参数附加到所有像素，这种情况较为常见，详细描述如下。

Audience Manager 在像素调用中使用两个参数传递用户同意：

* `gdpr` 可以为 0（GDPR 不适用）或 1（GDPR 适用）；
* `gdpr_consent` 是 URL 安全的 base64 编码 GDPR 同意字符串（请参阅[规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)）。对展示像素的示例调用（其中包含这两个参数）如下所示：

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

下面的图像和步骤中介绍了相关用例。我们将从图像左侧开始介绍：

1. 通过广告服务器向您的用户提供一次展示。這會轉譯為 [畫素呼叫](../../integration/media-data-integration/impression-data-pixels.md) 至我們的資料收集伺服器(DCS)。
2. Audience Manager 检查 GDPR 标记是否适用。如果不適用，Audience Manager會將傳入的資料儲存在 `gdpr` 和 `gdpr_consent` 畫素呼叫中的變數。
3. 如果IAB TC字串存在且包含必要的許可權，Audience Manager會將傳入的資料儲存在 `gdpr` 和 `gdpr_consent` 畫素呼叫中的變數。
4. 如果IAB TC字串遺失或缺少必要的許可權，Audience Manager會捨棄傳入的資料 `gdpr` 和 `gdpr_consent` 畫素呼叫中的變數。

![广告商用例](assets/advertiser-use-case.png)

## 支持 IAB TCF 的激活合作伙伴 {#aam-activation-partners}

適用於IAB TCF的Audience Manager外掛程式可讓您將IAB TC字串轉送給啟用合作夥伴，同時尊重使用者的隱私權選擇。 有关哪些激活合作伙伴支持 IAB TCF 的信息，请参阅我们[基于设备的目标列表](/help/using/features/destinations/device-based-destinations-list.md)。

## 將同意附加至傳送至URL目的地的URL

Audience Manager與IAB TCF v2.0整合可支援將同意附加至傳送給的資訊 [URL目的地](../../features/destinations/create-url-destination.md) 與IAB TCF v2.0整合的客戶。不過，此過程不會透過Audience Manager自動完成，以避免破壞特定URL格式。

希望將同意附加至傳送至的資料的客戶 [!DNL URL destinations] 必須手動新增 `${GDPR}` 和 `${GDPR_CONSENT_XXXX}` 將巨集轉換為其URL格式，取代 `XXXX` ，並使用目的地合作夥伴ID。

示例: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

另請參閱 [定義的巨集目的地](../../features/destinations/destination-macros.md) 以取得有關支援的目的地巨集的詳細資訊。

## 跨裝置同意管理

如果您的網站訪客未提供適當的許可權，適用於IAB TCF的Audience Manager外掛程式會自動選擇退出請求中呈現的ID。 如果請求包含 [跨裝置ID (CRM ID)](../../reference/ids-in-aam.md)，Audience Manager會選擇退出ID，以及連結至該ID的最後一個裝置 [跨裝置ID (CRM ID)](../../reference/ids-in-aam.md).

## 测试 IAB 实施 {#test-iab-implementation}

若要測試您是否已正確實作適用於IAB TCF的Audience Manager外掛程式，請閱讀 [驗證選擇加入服務的使用案例4](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## Audience Manager 中的 IAB 和选择退出。优先级顺序。 {#iab-and-optout}

用户可以选择的另一个隐私选项是选择退出所有数据收集。Adobe 在[隐私选择](https://www.adobe.com/cn/privacy/opt-out.html#customeruse)页面中为用户提供了相应的操作方法。

Audience Manager 在[我们文档中的单独文章](data-privacy-requests.md#opt-out-requests)中介绍了选择退出请求。

>[!IMPORTANT]
>
>拒絕同意後退出所有資料收集的使用者，無法再次加入。

>[!NOTE]
>
>**优先级顺序** - 如果用户使用全局选择退出工具选择退出数据收集（如上面的链接所述），则此选项优先于选择加入和 IAB 验证。

## 其他资源 {#additional-resources}

* [Adobe Experience Platform Identity Service 选择加入](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 欧洲 GDPR 透明度与同意框架](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 欧洲 GDPR 透明度与同意框架技术规范](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 插件 - 视频演示](https://helpx.adobe.com/cn/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
