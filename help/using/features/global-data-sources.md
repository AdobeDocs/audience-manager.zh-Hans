---
description: 使用全局数据源导入设备广告ID。
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: 全局数据源
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# 全局数据源 {#global-data-sources}

## 概述

所有Audience Manager客户均可访问全局数据源，其中包含了设备制造商（如[!DNL Apple]、[!DNL Samsung]、[!DNL Microsoft]、[!DNL Roku]和[!DNL Android]设备制造商）生成的设备广告ID。 这些 ID 是设备制造商出于广告宣传的目的而提供的。Audience Manager客户可以使用全局数据源来同步设备ID，并导入或导出这些映射中断开映射的数据。

下表介绍了Audience Manager支持的全局数据源。

| 数据Source ID | 描述 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** ID表示运行[!DNL Android]操作系统的设备。 |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** ID表示运行[!DNL iOS]操作系统的设备。 |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** ID代表[!DNL Roku]个流设备。 |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** ID表示运行[!DNL Windows 10]操作系统的设备。 |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID代表[!DNL Samsung]个智能电视。 |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]**&#x200B;表示运行[!DNL Amazon Fire OS]的设备 |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]**&#x200B;表示运行[!DNL LG webOS]操作系统的设备。 |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]**&#x200B;表示运行Vizio智能电视操作系统的设备。 |

## 从全局数据源导入数据

您可以通过[实时数据传输](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md)和[批量数据传输](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)，从全局数据源导入设备ID。

>[!IMPORTANT]
>
>使用全局设备ID向Audience Manager发送数据时，请确保为相关设备ID使用相应的数据源。 示例：要导入[!DNL Apple IDFA]的数据，请使用数据源ID 20915。

## 限制

在运行[!DNL iOS]和[!DNL Android]操作系统的设备上，只有本机应用程序才能检索和使用设备广告ID ([!UICONTROL DAID])。 在移动浏览器中运行的Web应用程序无权访问设备广告ID。

## 全局设备ID验证

Audience Manager将根据其格式，验证由客户导入的设备广告ID ([!UICONTROL DAID])，以确保这些ID符合设备制造商列出的标准格式。 有关设备广告ID到全局数据源的详细映射以及每个ID的正确Audience Manager，请参阅[设备广告ID索引](../reference/ids-in-aam.md)。 确保根据设备类型以正确的格式导入设备ID。 Audience Manager会拒绝不符合适当格式的设备ID，并返回一条错误消息，指示该ID已被拒绝。

* 此处概述了批量数据传输的错误消息传递：[载入状态报告术语和定义](../reporting/onboarding-status-report.md#report-terms-conditions)。
* 此处概述了实时数据传送的错误消息：[DCS错误代码、消息和示例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。

## 设备ID过期策略

Audience Manager在处于非活动状态120天后自动丢弃设备广告ID，类似于[AAM UUID](../faq/faq-privacy.md)。

## 请求新的全局数据源

要请求将新的全局数据源添加到Audience Manager，请与Adobe Consulting或Adobe客户关怀团队联系，并提供有关所需数据源的详细信息：

* 请求的平台的名称（例如，[!UICONTROL Apple IDFA]）；
* 管理平台的公司/组织的名称（例如，[!UICONTROL Apple Inc.]）；
* 指向设备广告ID命名空间的技术规范的链接（例如，[AdSupport文档](https://developer.apple.com/documentation/adsupport)）。
