---
description: Audience Manager为您可以为帐户创建的特征、细分、目标和算法模型设置最大限制。无论是在用户界面中创建还是通过API方法编程，限制都适用于这些项目。使用限制可帮助Audience Manager从可能试图危及我们API或用户界面的自动化流程中进行保护。
seo-description: Audience Manager为您可以为帐户创建的特征、细分、目标和算法模型设置最大限制。无论是在用户界面中创建还是通过API方法编程，限制都适用于这些项目。使用限制可帮助Audience Manager从可能试图危及我们API或用户界面的自动化流程中进行保护。
seo-title: 使用限制
solution: Audience Manager
title: 使用限制
keywords: ID映射、ID映射、cookie映射
uuid: 50ca4647-3b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


# 使用限制 {#usage-limits}

Audience Manager为您可以为帐户创建的特征、细分、目标和算法模型设置最大限制。无论是在用户界面中创建还是通过 [!DNL API] 方法编程，限制都适用于这些项目。使用限制可帮助Audience Manager从可能试图危害我们 [!DNL API]或用户界面的自动化流程中受益。

## ID 映射限制 {#id-mapping-limits}

下表列出设备ID [的ID映射](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) 限制。在ID达到以下任何限制后，Audience [!DNL FIFO] Manager将通过删除最旧存储的ID映射，并添加新的ID映射来添加新的ID映射，并添加新的ID映射。有关Audience [Manager支持的ID的详细信息，请参阅Audience Manager](../../reference/ids-in-aam.md) 中的ID索引。

| ID映射 | 最大限制 |
|-----------|-------------- |
| 设备广告ID(DAID)到跨设备ID(CRM ID) | 100台设备广告ID(DAID)到个跨设备ID(CRM ID) |
| 跨设备ID(CRM ID)到设备广告ID(DAID) | 10个跨设备ID(CRM ID)到设备广告ID(DAID) |
| cookie/浏览器ID到cookie/浏览器ID | 1000cookie/浏览器ID至个cookie/浏览器ID |

## 项目限制 {#item-limits}

表按项目类型列出当前限制。您不能创建新的特征、区段、目标，或者 [!UICONTROL Algorithmic Models] 如果您达到其中某个项目的特定限制。如果您达到限制，则必须先删除旧项目，然后再创建新项目。

### 特征限制

| 特征类型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 总特征 | 100,000 |
| 特征资格资格 | 150,000. 有关特征资格资格的更多信息，请参阅特征资格参考中 [的特征资格限制](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit)。 |
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
| 模型被排除特征的最大数量 | 500. 请参阅 [算法建模中的特征排除](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)。 |

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

## 监视使用情况 {#monitor-usage}

您可以通过转 **[!UICONTROL Administration > Limits]**&#x200B;至帐户了解帐户的使用情况和限制。访问权限需要管理员权限。

![使用限制图像](assets/usage-limits.png)

## 增加项目限制 {#increase-item-limits}

此处列出的默认限制应为您的业务需求提供足够的容量。如果您的组织持续达到这些限制，请联系您的客户代表以讨论增加。