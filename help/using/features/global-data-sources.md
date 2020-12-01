---
description: 使用全局数据源导入设备广告ID。
seo-description: 使用全局数据源导入设备广告ID。
seo-title: 全局数据源
solution: Audience Manager
title: 全局数据源
feature: Data Sources
translation-type: tm+mt
source-git-commit: cb84f95d52c2e851cb0c016cb25f408f2d79d01b
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 6%

---


# 全局数据源 {#global-data-sources}

## 概述

所有Audience Manager客户都可以访问全局数据源，并包含由设备制造商（如[!DNL Apple]、[!DNL Samsung]、[!DNL Microsoft]、[!DNL Roku]和[!DNL Android]设备制造商）生成的设备广告ID。 这些 ID 是设备制造商出于广告宣传的目的而提供的。Audience Manager客户可以使用全局数据源来同步设备ID并导入或导出键出这些映射的数据。

下表描述了Audience Manager支持的全局数据源。

| 数据源ID | 描述 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** ID表示运行操作系 [!DNL Android] 统的设备。 |
| 20915 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** ID表示运行操作系 [!DNL iOS] 统的设备。 |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** ID表示 [!DNL Roku] 流设备。 |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** ID表示运行操作系 [!DNL Windows 10] 统的设备。 |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** ID代表 [!DNL Samsung] 智能电视。 |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** 表示正在运行的设备  [!DNL Amazon Fire OS] |

## 从全局数据源导入数据

您可以通过[实时数据传输](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md)和[批量数据传输](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)从全局数据源导入设备ID。

>[!IMPORTANT]
>
>使用全局设备ID向Audience Manager发送数据时，请确保为相关设备ID使用相应的数据源。 示例：要导入[!DNL Apple IDFA]的数据，请使用数据源ID 20915。

## 限制

在运行[!DNL iOS]和[!DNL Android]操作系统的设备上，只有本机应用程序才能检索和使用设备广告ID([!UICONTROL DAID]s)。 在移动浏览器中运行的Web 应用程序无权访问设备广告ID。

## 全局设备ID验证

Audience Manager根据客户的格式验证客户导入的设备广告ID([!UICONTROL DAID])，以确保其符合设备制造商概述的标准格式。 有关设备广告ID到全局数据源的详细映射以及每个ID的正确格式，请参阅Audience Manager](../reference/ids-in-aam.md)中的[ ID索引。 请确保根据设备类型以正确的格式导入设备ID。 Audience Manager拒绝不符合正确格式的设备ID，并返回一条错误消息以指示该ID被拒绝。

* 批处理数据传输的错误消息在下面进行了概述：[入门状态报告术语和定义](../reporting/onboarding-status-report.md#report-terms-conditions)。
* 实时数据传输的错误消息概述如下：[DCS错误代码、消息和示例](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)。

## 设备ID过期策略

Audience Manager在120天不活动后自动丢弃设备广告ID，与[AAM UUID](../faq/faq-privacy.md)类似。

## 请求新的全局数据源

要请求将新的全球数据源添加到Audience Manager，请与Adobe咨询或Adobe客户关怀部门联系，并提供有关所需数据源的详细信息：

* 所请求平台的名称（例如[!UICONTROL Apple IDFA]）;
* 管理平台的公司/组织的名称（例如[!UICONTROL Apple Inc.]）;
* 指向设备广告ID命名空间技术规范的链接（例如[AdSupport文档](https://developer.apple.com/documentation/adsupport)）。