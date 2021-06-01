---
description: 使用全局数据源导入设备广告ID。
seo-description: 使用全局数据源导入设备广告ID。
seo-title: 全局数据源
solution: Audience Manager
title: 全局数据源
feature: 数据源
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 6%

---

# 全局数据源 {#global-data-sources}

## 概述

所有Audience Manager客户都可以访问全局数据源，并包含由设备制造商（如[!DNL Apple]、[!DNL Samsung]、[!DNL Microsoft]、[!DNL Roku]和[!DNL Android]设备制造商）生成的设备广告ID。 这些 ID 是设备制造商出于广告宣传的目的而提供的。Audience Manager客户可以使用全局数据源来同步设备ID，并导入或导出这些映射中无键的数据。

下表介绍了受Audience Manager支持的全局数据源。

| 数据源ID | 描述 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - ID **[!DNL GAID]** 表示运行操作系统 [!DNL Android] 的设备。 |
| 20915 | **[!DNL Apple ID For Advertising]** - ID **[!DNL IDFA]** 表示运行操作系统 [!DNL iOS] 的设备。 |
| 121963 | **[!DNL Roku ID for Advertising]** - ID **[!DNL RIDA]** 表示流 [!DNL Roku] 设备。 |
| 389146 | **[!DNL Microsoft Advertising ID]** - ID **[!DNL MAID]** 表示运行操作系统 [!DNL Windows 10] 的设备。 |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - ID **[!DNL TIFA]** 表示智 [!DNL Samsung] 能电视。 |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** 表示正在运行的设备  [!DNL Amazon Fire OS] |

## 从全局数据源导入数据

您可以通过[实时数据传输](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md)和[批量数据传输](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)从全局数据源导入设备ID。

>[!IMPORTANT]
>
>使用全局设备ID向Audience Manager发送数据时，请确保为相关设备ID使用相应的数据源。 示例：要导入[!DNL Apple IDFA]的数据，请使用数据源ID 20915。

## 限制

在运行[!DNL iOS]和[!DNL Android]操作系统的设备上，只有本机应用程序才能检索和使用设备广告ID([!UICONTROL DAID]s)。 在移动设备浏览器中运行的Web应用程序无权访问设备广告ID。

## 全局设备ID验证

Audience Manager将根据其格式，验证由客户导入的设备广告ID([!UICONTROL DAID])，以确保这些ID符合设备制造商列出的标准格式。 请参阅[Audience Manager](../reference/ids-in-aam.md)中的ID索引，以了解设备广告ID到全局数据源的详细映射以及每个ID的正确格式。 确保根据设备类型以正确的格式导入设备ID。 Audience Manager拒绝不符合正确格式的设备ID，并返回一条错误消息，指示该ID被拒绝。

* 批量数据传输的错误消息如下所述：[载入状态报表术语和定义](../reporting/onboarding-status-report.md#report-terms-conditions)。
* 实时数据传输的错误消息如下所述：[DCS错误代码、消息和示例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。

## 设备ID过期策略

Audience Manager在处于不活动状态120天后会自动丢弃设备广告ID，这与[AAM UUID](../faq/faq-privacy.md)类似。

## 请求新的全局数据源

要请求将新的全局数据源添加到Audience Manager，请联系Adobe咨询或Adobe客户关怀团队并提供有关所需数据源的详细信息：

* 请求平台的名称（例如[!UICONTROL Apple IDFA]）；
* 管理平台的公司/组织的名称（例如[!UICONTROL Apple Inc.]）；
* 指向设备广告ID命名空间技术规范的链接（例如[AdSupport文档](https://developer.apple.com/documentation/adsupport)）。
