---
description: Audience Manager设置您可以为帐户创建的特征、区段、目标和算法模型的最大数量限制。 限制适用于这些项目，无论是在用户界面中创建，还是通过API方法以编程方式创建。 使用限制有助于保护Audience Manager免受可能试图危害我们的API或用户界面的自动进程的攻击。
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: 使用限制
keywords: ID映射、ID映射、Cookie映射
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 3%

---

# 使用限制 {#usage-limits}

Audience Manager设置您可以为帐户创建的特征、区段、目标和算法模型的最大数量限制。 限制适用于这些项目，无论是在用户界面中创建，还是通过[!DNL API]方法以编程方式创建。 使用限制有助于保护Audience Manager免受可能试图危害[!DNL API]或用户界面的自动进程的攻击。

## ID映射限制 {#id-mapping-limits}

下表列出了设备ID的[ID映射](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)限制。 一旦ID达到以下任何限制，Audience Manager就会根据FIFO（先进先出）逻辑添加新的ID映射，方法是删除最早的存储的ID映射，然后添加新的ID映射。 有关Audience Manager支持的ID的详细信息，请参阅Audience Manager中的[ID索引](../../reference/ids-in-aam.md)。

| ID映射 | 最大限制 |
|-----------|-------------- |
| 设备Advertising ID ([DAID](../../reference/ids-in-aam.md))到跨设备ID ([DPUUID](../../reference/ids-in-aam.md)) | 100个设备Advertising ID ([DAID](../../reference/ids-in-aam.md))到1个跨设备ID ([DPUUID](../../reference/ids-in-aam.md)) |
| 跨设备ID ([DPUUID](../../reference/ids-in-aam.md))到设备Advertising ID ([DAID](../../reference/ids-in-aam.md)) | 每个[DPID](../../reference/ids-in-aam.md)有10个跨设备ID ([DPUUID](../../reference/ids-in-aam.md))到1个设备Advertising ID ([DAID](../../reference/ids-in-aam.md)) |
| Cookie/浏览器ID到Cookie/浏览器ID | 1,000个Cookie/浏览器ID替换为1个Cookie/浏览器ID |

## 项目限制 {#item-limits}

该表按项目类型列出当前限制。 如果达到这些项目之一的特定限制，则无法创建新特征、区段、目标或[!UICONTROL Algorithmic Models]。 如果您达到了限制，则必须先删除旧项目，然后才能创建新项目。

### 特征限制

| 特征类型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 特征总数 | 100,000 |
| 特征资格总数 | 15万。 有关特征资格的详细信息，请参阅[特征资格参考](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)中的特征资格限制。 |
| 算法 | 50 |
| 基于规则 | 100,000 |
| 已载入 | 100,000 |
| 文件夹特征 | 2,000 |

### 区段限制

| 区段类型 | 最大限制 |
| -------------- | ------------- |
| 区段总数 | 20,000 |

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
| 活动[!UICONTROL Look-Alike Models] | 20.Audience Manager仅将&#x200B;*活动*&#x200B;算法模型计入此限制。 |
| [!UICONTROL Look-Alike Models]最大受众规模 | 2500万。  请注意，此限制不能增加。 您可以通过为模型选择更少的数据源或选择更短的回顾时间范围来减少受众规模。 |
| [!UICONTROL Look-Alike Model]排除的特征的最大数量 | 500.请参阅算法建模中的[特征排除](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)。 |
| 最大[!UICONTROL Predictive Audiences Models] | 10 |
| [!UICONTROL Predictive Audiences Models]的最大基线角色数 | 50 |

### 文件夹限制

| 项目 | 最大限制 |
| ------------- | ------------------ |
| 特征文件夹 | 2000  您的文件夹结构最多可以深5级。 |

### 派生的信号限制

| 项目 | 最大限制 |
| --------------- | ------------- |
| 派生的信号 | 五万。 |

### 公司用户帐户限制

| 项目 | 最大限制 |
| ----------- | ------------- |
| 公司的最大用户帐户数 | 1000 |

## 监视器使用情况 {#monitor-usage}

您可以通过转到&#x200B;**[!UICONTROL Administration > Limits]**&#x200B;查看帐户的使用情况和限制。 访问需要管理员权限。

![使用限制图像](assets/usage-limits.png)

## 增加项目限制 {#increase-item-limits}

此处列出的默认限制应可提供足够的容量来满足您的业务需求。 如果贵组织始终达到这些限制，请联系客户代表讨论提高客户忠诚度的事宜。
