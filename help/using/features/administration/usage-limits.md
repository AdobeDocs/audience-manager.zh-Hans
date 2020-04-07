---
description: 受众管理器设置可为帐户创建的特征、区段、目标和算法模型的最大数量限制。 无论是在用户界面中创建还是通过API方法以编程方式创建，这些限制都适用于这些项目。 使用限制有助于保护受众管理器免受可能破坏我们的API或用户界面的自动化进程的影响。
seo-description: 受众管理器设置可为帐户创建的特征、区段、目标和算法模型的最大数量限制。 无论是在用户界面中创建还是通过API方法以编程方式创建，这些限制都适用于这些项目。 使用限制有助于保护受众管理器免受可能破坏我们的API或用户界面的自动化进程的影响。
seo-title: 使用限制
solution: Audience Manager
title: 使用限制
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# 使用限制 {#usage-limits}

受众管理器设置可为帐户创建的特征、区段、目标和算法模型的最大数量限制。 无论是在用户界面中创建还是通过方法以编程方式创建，限制都适用于这些 [!DNL API] 项目。 使用限制有助于保护受众管理器免受可能破坏我们或用户界面 [!DNL API]的自动化进程的影响。

## ID 映射限制 {#id-mapping-limits}

下表列表了设 [备ID的](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) ID映射限制。 一旦ID达到以下任何限制，受众管理器将删除最旧的存储ID映射并添加新的映射，从而根据 [!DNL FIFO] （先入后出）逻辑添加新的ID映射。 有关受众 [管理器支持的ID的详细信息](../../reference/ids-in-aam.md) ，请参阅受众管理器中的ID索引。

| ID映射 | 最大限制 |
|-----------|-------------- |
| 设备广告ID([DAID](../../reference/ids-in-aam.md))到跨设备ID([DPUUID](../../reference/ids-in-aam.md)) | 100个设备广告ID([DAID](../../reference/ids-in-aam.md))到1个跨设备ID([DPUUID](../../reference/ids-in-aam.md)) |
| 跨设备ID([DPUUID](../../reference/ids-in-aam.md))到设备广告ID([DAID](../../reference/ids-in-aam.md)) | 每个DPID有10个跨设[备ID(DPUUID](../../reference/ids-in-aam.md))到1个设备广告ID([DAID](../../reference/ids-in-aam.md)) [（每个DPID）](../../reference/ids-in-aam.md) |
| Cookie/浏览器ID至Cookie/浏览器ID | 1000个cookie/浏览器ID至1个cookie/浏览器ID |

## 项目限制 {#item-limits}

这些表按项目类型列表当前限制。 您不能创建新特征、区段、目标，或 [!UICONTROL Algorithmic Models] 者如果您达到其中一个项目的特定限制。 如果达到限制，则必须先删除旧项目，然后才能创建新项目。

### 特征限制

| 特征类型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 总特征 | 100,000 |
| 特征资格总数 | 150,000. 有关特征资格的详细信息，请参阅特征资格参考中的 [特征资格限制](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)。 |
| 算法 | 50 |
| 基于规则 | 100,000 |
| 已载入 | 100,000 |
| 文件夹特征 | 2,000 |

### 细分限制

| 区段类型 | 最大限制 |
| -------------- | ------------- |
| 细分总数 | 20,000 |

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
| 算法模型最大受众大小 | 25,000,000.  请注意，此限制不能增加。 通过为模型选择较少的数据源或选择较短的回顾窗口，可以减小受众大小。 |
| 模型被排除的特征的最大数量 | 500.请参 [阅算法建模中的特征排除](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)。 |

### 文件夹限制

| 项目 | 最大限制 |
| ------------- | ------------------ |
| 特征文件夹 | 2,000.  您的文件夹结构最多可以有5个级别。 |

### 派生的信号限制

| 项目 | 最大限制 |
| --------------- | ------------- |
| 派生信号 | 50,000. |

### 公司用户帐户限制

| 项目 | 最大限制 |
| ----------- | ------------- |
| 公司的最大用户帐户数 | 1,000. |

## 监视使用情况 {#monitor-usage}

您可以转到，查看帐户的使用情况和限制 **[!UICONTROL Administration > Limits]**。 访问需要管理员权限。

![使用限制图像](assets/usage-limits.png)

## 增加项目限制 {#increase-item-limits}

此处列出的默认限制应为您的业务需求提供足够的容量。 如果您的组织始终达到这些限制，请与您的客户代表联系以讨论增加额。