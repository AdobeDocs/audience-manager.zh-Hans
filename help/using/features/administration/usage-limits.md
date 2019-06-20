---
description: Audience Manager为您可以为帐户创建的特征、细分、目标和算法模型设置最大限制。无论是在用户界面中创建还是通过API方法编程，限制都适用于这些项目。使用限制可帮助Audience Manager从可能试图危及我们API或用户界面的自动化流程中进行保护。
seo-description: Audience Manager为您可以为帐户创建的特征、细分、目标和算法模型设置最大限制。无论是在用户界面中创建还是通过API方法编程，限制都适用于这些项目。使用限制可帮助Audience Manager从可能试图危及我们API或用户界面的自动化流程中进行保护。
seo-title: 使用限制
solution: Audience Manager
title: 使用限制
topic: DIL API
uuid: 50ca4647-3b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: a9550d71bbc6adf939539df05cd38a9d22ef261b

---


# Usage Limits {#usage-limits}

Audience Manager为您可以为帐户创建的特征、细分、目标和算法模型设置最大限制。Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## ID 映射限制 {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adds the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

| ID映射 | 最大限制 |
|-----------|-------------- |
| 设备广告ID(DAID)到跨设备ID(CRM ID) | 100台设备广告ID(DAID)到个跨设备ID(CRM ID) |
| 跨设备ID(CRM ID)到设备广告ID(DAID) | 10个跨设备ID(CRM ID)到设备广告ID(DAID) |
| cookie/浏览器ID到cookie/浏览器ID | 1000cookie/浏览器ID至个cookie/浏览器ID |

## Item Limits {#item-limits}

表按项目类型列出当前限制。You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. 如果您达到限制，则必须先删除旧项目，然后再创建新项目。

### 特征限制

| 特征类型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 总特征 | 100,000 |
| 特征资格资格 | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
| 算法算法 | 50 |
| 基于规则 | 100,000 |
| 载入的 | 100,000 |
| 文件夹特征 | 2,000 |

### 细分限制

| 区段类型 | 最大限制 |
| -------------- | ------------- |
| 总区段 | 20,000 |

### 目标限制

| 目标类型 | 最大限制 |
| ------------------ | ------------- |
| 目标总数 | 1,000 |
| Cookie | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 算法模型限制

| 项目 | 最大限制 |
| -------- | ----- |
| 活动算法模型 | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| 算法模型最大受众规模 | 25,000,000.  请注意，此限制无法增加。您可以通过为模型选择较少的数据源或选择较短的回顾窗口来降低受众大小。 |
| 模型被排除特征的最大数量 | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### 文件夹限制

| 项目 | 最大限制 |
| ------------- | ------------------ |
| 特征文件夹 | 2,000.  您的文件夹结构最高可达个级别。 |

### 派生信号限制

| 项目 | 最大限制 |
| --------------- | ------------- |
| 派生信号 | 50,000. |

### 公司用户帐户限制

| 项目 | 最大限制 |
| ----------- | ------------- |
| 公司的最大用户数 | 1,000. |

## Monitor Usage {#monitor-usage}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. 访问权限需要管理员权限。

![使用限制图像](assets/usage-limits.png)

## Increase Item Limits {#increase-item-limits}

此处列出的默认限制应为您的业务需求提供足够的容量。如果您的组织持续达到这些限制，请联系您的客户代表以讨论增加。