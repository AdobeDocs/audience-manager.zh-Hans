---
description: 基于人员的目标提供了多个实施策略，具体取决于您的客户数据的结构。 本文概述了根据您的方案，您需要为基于人员的目标关注的实施步骤。
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: 实施指南
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---

# 实施指南 {#implementation-guidance}

>[!IMPORTANT]
>本文包含產品檔案，旨在引導您完成此功能的設定和使用。 本文不包含任何法律建議。 请咨询您的法律顾问，以获取法律指导。

[!DNL People-Based Destinations] 提供了多个实施策略，具体取决于您的客户数据的构建方式。 本文概述了您需要关注的 [!DNL People-Based Destinations] 实施步骤，具体取决于您的方案。

## 概述 {#overview}

配置将引导您完成 Audience Manager 的 [!DNL People-Based Destinations] 多个部分，并根据 Audience Manager 中已有的客户数据类型以及您要执行的定位受众类型等不同的设置和数据加入方法。

>[!IMPORTANT]
> 配置 [!DNL People-Based Destinations] 之前，请务必仔细而完整地阅读本文。 阅读此指南后，您应当清楚地了解将启用 [!DNL People-Based Destinations] 的方案。

在使用之前，您必須先釐清六個實作層面 [!DNL People-Based Destinations]. 本文章將幫助您瞭解您目前的設定，以便您可以正確遵循情境的實作步驟。

![pbd — 實作](assets/pbd-implementation.png)

## 1.定義使用案例 {#defining-your-use-case}

開始實作之前 [!DNL People-Based Destinations]，您必須清楚定義要使用此功能的使用案例。 您可以使用 [!DNL People-Based Destinations] 根據對象活動，以兩種方式鎖定對象：

**A)根據您合併的線上和離線使用者活動的對象鎖定目標**. 在此案例中，您想要結合Audience Manager的現有受眾資料與內部資料 [!DNL CRM] 系統，並將產生的受眾區段傳送至 [!DNL People-Based Destinations]. 以下範例說明此情境：

貴公司是一家航空公司，擁有不同的客戶層級（銅級、銀級和金級），而您希望透過社交平台為每個層級提供個人化優惠。 您可以使用Audience Manager來分析網站上的客戶活動。 不過，並非所有客戶都使用航空公司的行動應用程式，其中有些客戶尚未登入公司網站。 您的客戶資料大多僅限於會籍ID和電子郵件地址。

若要在社群媒體和類似的以人物為基礎的頻道中鎖定這些對象，您可以將 [雜湊電子郵件地址](people-based-destinations-prerequisites.md) Audience Manager，並將其與您現有的線上活動特徵結合，以建立新的受眾區段。 接下來，您可以使用這些區段來透過鎖定您的對象 [!DNL People-Based Destinations].

**B）受众定位专门基于您的离线用户活动** 。 在此方案中，您 [!DNL CRM] 的系统包含您的客户电子邮件地址和其他客户属性，但客户根本没有与您的网站进行交互，因此您在 Audience Manager 中没有任何客户活动。 以下是说明此方案的示例：

您的公司，电信服务提供商可将客户数据点赞电子邮件地址，并在内部 [!DNL CRM] 购买电信计划。 您想要在社交平台中鎖定現有客戶，以根據其現有訂閱提供升級套件。 若要這麼做，您可以將雜湊的客戶電子郵件地址擷取至Audience Manager，並根據現有客戶訂閱建立區段。 然後，您可以將這些區段傳送至 [!DNL People-Based Destinations] 以個人化優惠方案鎖定您的客戶。

## 2.定義目標電子郵件地址的型別 {#define-target-email}

定义实施策略的第二步是确定要目标的客户电子邮件地址类型。

**A）受众定位基于已验证身份的电子邮件地址** 。 在此方案中，您的用户有多个帐户与多个电子邮件地址关联，您希望仅根据他们在您网站上进行身份验证的电子邮件地址，将其与个性化选件一起目标。

**B）受众定位基于您的所有关联电子邮件地址** 。 在此方案中，您的用户有多个帐户与多个电子邮件地址关联，您希望在所有关联的电子邮件地址中目标它们，而不考虑经过身份验证的活动。

## 3. 识别您拥有的客户 Id （CRM Id）类型 {#identify-customer-id}

在中鎖定受眾 [!DNL People-Based Destinations] 需要您傳送 [SHA256雜湊](people-based-destinations-prerequisites.md) 客戶電子郵件地址的版本。 根據您現有的Audience Manager設定，您可能會發現自己處於以下兩種情況之一：

**A)您的Audience Manager客戶ID ([DPUUID](../../reference/ids-in-aam.md))為小寫、雜湊電子郵件地址**. 在此案例中，您可以使用這些現有的ID在中鎖定您的對象 [!DNL People-Based Destinations].

**B)您的Audience Manager客戶ID ([DPUUID](../../reference/ids-in-aam.md))並非小寫、雜湊電子郵件地址**. 在此案例中，您現有的客戶ID無法傳送至 [!DNL People-Based Destinations]. 使用 [!DNL People-Based Destinations]，您必須在現有客戶ID與小寫、雜湊版本的客戶電子郵件地址之間執行ID同步。 您可以透過以下方式執行此操作： [檔案式ID同步](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 或透過使用 [宣告ID](../declared-ids.md).

## 4.特徵資格 {#trait-qualification}

若要在中準確鎖定您的對象 [!DNL People-Based Destinations]，您的使用者需要符合規則型或已上線特徵的資格，具體取決於您要執行的對象目標定位型別。

**A)即時確認客戶ID和裝置ID是否符合規則型特徵**. 此選項適用於來自的使用案例A [1. 定義使用案例](people-based-destinations-workflow.md#defining-your-use-case). 如果您的計畫是根據線上和離線活動來鎖定對象，那麼您很可能已經符合對象的資格， [規則型特徵](../traits/trait-and-segment-qualification-reference.md).

**B)透過傳入資料檔案針對您的客戶ID加入特徵**. 此選項適用於來自的使用案例B [1. 定义用例 ](people-based-destinations-workflow.md#defining-your-use-case) 。 定位基于纯粹离线活动的受众时，您需要通过 [ 入站数据文件 ](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 为载入特征授予客户 id。

## 5.建立或標示資料來源及內建雜湊電子郵件地址 {#create-label-data-sources}

根據您在Audience Manager中擁有的客戶ID型別(請參閱 [3. 識別您擁有的客戶ID (CRM ID)型別](people-based-destinations-workflow.md#identify-customer-id)，您會發現自己處於下列其中一個情況：

**A)標籤現有資料來源**. 此選項適用於Audience Manager客戶ID ([DPUUID](../../reference/ids-in-aam.md))為小寫、雜湊電子郵件地址。 在此情況下，您需要做的是將儲存ID的資料來源標示為 [!DNL PII] 資料來源。 有关数据源设置的详细信息，请参阅 [ Data 来源设置 ](../datasources-list-and-settings.md) 。 您必須確認未勾選「無法繫結至個人識別資訊」選項。

**B)建立新的資料來源**. 此選項適用於Audience Manager客戶ID ([DPUUID](../../reference/ids-in-aam.md))不是雜湊電子郵件地址。 在這種情況下，您需要建立新的跨裝置資料來源，並針對該來源加入雜湊電子郵件地址。 您可以透過兩種方式達成此目的：

* 使用基于文件的 ID 同步。有关 ID 同步文件外观的详细信息，请参阅 [ID 同步文件的名称和内容要求](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)。使用此方法時，您可以鎖定來自以下專案的所有雜湊電子郵件地址： [!DNL CRM] 資料庫。
* 使用 [宣告ID](../declared-ids.md) 在傳入已驗證的客戶ID時，宣告雜湊的電子郵件地址。 使用此方法時，代表您Audience Manager僅會鎖定已線上驗證的使用者之雜湊電子郵件地址。 以人物為基礎的管道中所定位的電子郵件地址，只是宣告ID事件呼叫中的目標電子郵件地址。 与客户 ID 关联的其他电子邮件地址不会实时激活。

## 6.使用設定檔合併規則進行分段 {#use-profile-merge-rules}

根據您的使用案例(請參閱 [1. 定義使用案例](people-based-destinations-workflow.md#defining-your-use-case))，則有兩種使用方式 [!DNL Profile Merge Rules] 用於區段。

**A）使用现有[!DNL Profile Merge Rules]** 的。 此选项适用于第一个用例（受众定位基于组合在线和离线用户活动）。 在此方案中，您已在 Audience Manager 中现有客户活动，并且您已至少定义了一个在分段中使用的配置文件合并规则。 在这种情况下，您无需创建任何新 [!DNL Profile Merge Rules] 的。

**B)建立新的、 [!DNL All Cross-Device Profiles] 合併規則**. 此選項適用於第二個使用案例（對象目標定位僅以離線使用者活動為基礎）。 在此案例中，您會將離線客戶資料從 [!DNL CRM] Audience Manager中，並想要從該資料建立區段。 若要這麼做， [!DNL People-Based Destinations] 引入新的第四個設定檔合併規則，稱為 **[!DNL All Cross-Device Profiles]**. 這是您在分段純粹的離線資料時需要使用的規則。
