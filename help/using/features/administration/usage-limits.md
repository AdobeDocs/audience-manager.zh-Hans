---
description: Audience Manager对您可以为帐户创建的特征、区段、目标和算法模型数量设置最大限制。 无论是在用户界面中创建还是通过API方法以编程方式创建，这些限制都适用于这些项。 使用限制有助于保护Audience Manager免受可能会破坏我们API或用户界面的自动化流程的影响。
seo-description: Audience Manager对您可以为帐户创建的特征、区段、目标和算法模型数量设置最大限制。 无论是在用户界面中创建还是通过API方法以编程方式创建，这些限制都适用于这些项。 使用限制有助于保护Audience Manager免受可能会破坏我们API或用户界面的自动化流程的影响。
seo-title: 使用限制
solution: Audience Manager
title: 使用限制
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 6%

---


# 使用限制 {#usage-limits}

Audience Manager对您可以为帐户创建的特征、区段、目标和算法模型数量设置最大限制。 无论是在用户界面中创建还是通过[!DNL API]方法以编程方式创建，这些限制都适用于这些项。 使用限制有助于保护Audience Manager免受可能会危及我们的[!DNL API]或用户界面的自动化进程的影响。

## ID 映射限制 {#id-mapping-limits}

下表列表了设备ID的[ID映射](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)限制。 一旦ID达到以下任何限制，Audience Manager将根据FIFO（先入先出）逻辑，删除最旧存储的ID映射，并添加新ID映射，从而添加新ID映射。 有关Audience Manager支持的ID的详细信息，请参阅[ ID的索引](../../reference/ids-in-aam.md)。

| ID映射 | 最大限制 |
|-----------|-------------- |
| 设备广告ID([DAID](../../reference/ids-in-aam.md))到跨设备ID([DPUUID](../../reference/ids-in-aam.md)) | 100个设备广告ID([DAID](../../reference/ids-in-aam.md))到1个跨设备ID([DPUUID](../../reference/ids-in-aam.md)) |
| 跨设备ID([DPUUID](../../reference/ids-in-aam.md))到设备广告ID([DAID](../../reference/ids-in-aam.md)) | 每个[DPID](../../reference/ids-in-aam.md)有10个跨设备ID([DPUUID](../../reference/ids-in-aam.md))到1个设备广告ID([DAID](../../reference/ids-in-aam.md)) |
| Cookie/浏览器ID到Cookie/浏览器ID | 1000个cookie/浏览器ID到1个cookie/浏览器ID |

## 项目限制{#item-limits}

这些表按项目类型列表当前限制。 如果达到其中一个项目的特定限制，则无法创建新特征、区段、目标或[!UICONTROL Algorithmic Models]。 如果达到限制，则必须先删除旧项目，然后才能创建新项目。

### 特征限制

| 特征类型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 总特征 | 十万 |
| 特征资格总数 | 15万。 有关特征资格的详细信息，请参阅[特征资格参考](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)中的特征资格限制。 |
| 算法 | 50 |
| 基于规则 | 十万 |
| 已载入 | 十万 |
| 文件夹特征 | 2,000 |

### 细分限制

| 区段类型 | 最大限制 |
| -------------- | ------------- |
| 区段总数 | 2万 |

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
| 活动 [!UICONTROL Look-Alike Models] | 20.Audience Manager仅按此限制计算&#x200B;*active*&#x200B;算法模型。 |
| [!UICONTROL Look-Alike Models] 最大受众大小 | 2500万。  请注意，此限制无法增加。 您可以通过为模型选择较少的数据源或选择较短的回顾窗口来减少受众大小。 |
| [!UICONTROL Look-Alike Model]的被排除特征的最大数量 | 500.请参见算法建模中的[特征排除](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)。 |
| 最低[!UICONTROL Predictive Audiences Models] | 10 |
| [!UICONTROL Predictive Audiences Models]的最大基准角色数 | 50 |

### 文件夹限制

| 项目 | 最大限制 |
| ------------- | ------------------ |
| 特征文件夹 | 2000。  您的文件夹结构可以最大深度为5级。 |

### 派生信号限制

| 项目 | 最大限制 |
| --------------- | ------------- |
| 派生的信号 | 50,000. |

### 公司用户帐户限制

| 项目 | 最大限制 |
| ----------- | ------------- |
| 公司的最大用户帐户数 | 1,000. |

## 监视器使用情况{#monitor-usage}

您可以通过转到&#x200B;**[!UICONTROL Administration > Limits]**&#x200B;来查看帐户的使用情况和限制。 访问需要管理员权限。

![使用限制图像](assets/usage-limits.png)

## 增加项目限制{#increase-item-limits}

此处列出的默认限制应提供足够的容量来满足您的业务需求。 如果您的组织始终达到这些限制，请与客户代表联系以讨论增加额。