---
description: Audience Manager对您可以为帐户创建的特征、区段、目标和算法模型的数量设置最大限制。 无论是在用户界面中创建还是通过API方法以编程方式创建，这些项目都会受到限制。 使用限制有助于保护Audience Manager免受可能尝试破坏我们API或用户界面的自动化流程的影响。
seo-description: Audience Manager对您可以为帐户创建的特征、区段、目标和算法模型的数量设置最大限制。 无论是在用户界面中创建还是通过API方法以编程方式创建，这些项目都会受到限制。 使用限制有助于保护Audience Manager免受可能尝试破坏我们API或用户界面的自动化流程的影响。
seo-title: 使用限制
solution: Audience Manager
title: 使用限制
keywords: ID映射、ID映射、Cookie映射
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: 使用和账单
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 7%

---

# 使用限制 {#usage-limits}

Audience Manager对您可以为帐户创建的特征、区段、目标和算法模型的数量设置最大限制。 无论是在用户界面中创建还是通过[!DNL API]方法以编程方式创建，这些项目都会受到限制。 使用限制有助于保护Audience Manager免受可能会破坏我们的[!DNL API]s或用户界面的自动化进程的影响。

## ID 映射限制 {#id-mapping-limits}

下表列出了设备ID的[ ID映射](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)限制。 当ID达到以下任何限制时，Audience Manager会通过删除最早存储的ID映射并添加新映射来根据FIFO（先入先出）逻辑添加新的ID映射。 有关Audience Manager支持的ID的详细信息，请参阅Audience Manager中的[ ID索引](../../reference/ids-in-aam.md)。

| ID映射 | 最大限制 |
|-----------|-------------- |
| 将设备广告ID([DAID](../../reference/ids-in-aam.md))更改为跨设备ID([DPUUID](../../reference/ids-in-aam.md)) | 100个设备广告ID([DAID](../../reference/ids-in-aam.md))到1个跨设备ID([DPUUID](../../reference/ids-in-aam.md)) |
| 跨设备ID([DPUUID](../../reference/ids-in-aam.md))到设备广告ID([DAID](../../reference/ids-in-aam.md)) | 每个[DPID](../../reference/ids-in-aam.md)具有10个跨设备ID([DPUUID](../../reference/ids-in-aam.md))到1个设备广告ID([DAID](../../reference/ids-in-aam.md)) |
| 从Cookie/浏览器ID到Cookie/浏览器ID | 1000个Cookie/浏览器ID转换为1个Cookie/浏览器ID |

## 项目限制{#item-limits}

这些表按项目类型列出当前限制。 如果某个项目达到特定限制，则无法创建新特征、区段、目标或[!UICONTROL Algorithmic Models]。 如果达到限制，则必须先删除旧项目，然后才能创建新项目。

### 特征限制

| 特征类型 | 最大限制 |
| -------------------------- | ------------------------------------- |
| 总特征 | 十万 |
| 特征资格总数 | 15万。 有关特征资格的更多信息，请参阅[特征资格参考](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)中的特征资格限制。 |
| 算法 | 50 |
| 基于规则 | 十万 |
| 已载入 | 十万 |
| 文件夹特征 | 零点二万 |

### 区段限制

| 区段类型 | 最大限制 |
| -------------- | ------------- |
| 总区段 | 两万 |

### 目标限制

| 目标类型 | 最大限制 |
| ------------------ | ------------- |
| 目标总数 | 1,000 |
| Cookie | 零点一万 |
| URL | 零点一万 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 算法模型限制

| 项目 | 最大限制 |
| -------- | ----- |
| 活动 [!UICONTROL Look-Alike Models] | 20.Audience Manager仅针对该限制计算&#x200B;*active*&#x200B;算法模型。 |
| [!UICONTROL Look-Alike Models] 最大受众大小 | 2500万。  请注意，此限制无法提高。 您可以通过为模型选择较少的数据源或选择较短的回顾窗口来减少受众大小。 |
| [!UICONTROL Look-Alike Model]的已排除特征的最大数量 | 500.请参阅算法建模](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)中的[特征排除。 |
| 最大值 [!UICONTROL Predictive Audiences Models] | 10 |
| [!UICONTROL Predictive Audiences Models]的基线角色的最大数量 | 50 |

### 文件夹限制

| 项目 | 最大限制 |
| ------------- | ------------------ |
| 特征文件夹 | 两千。  您的文件夹结构最多可以有5个深度级别。 |

### 派生的信号限制

| 项目 | 最大限制 |
| --------------- | ------------- |
| 派生的信号 | 50,000. |

### 公司用户帐户限制

| 项目 | 最大限制 |
| ----------- | ------------- |
| 公司的用户帐户最大数量 | 1,000. |

## 监视器使用情况{#monitor-usage}

您可以转到&#x200B;**[!UICONTROL Administration > Limits]**&#x200B;查看帐户的使用情况和限制。 访问需要管理员权限。

![使用限制图像](assets/usage-limits.png)

## 增加项目限制{#increase-item-limits}

此处列出的默认限制应能为您的业务需求提供足够的容量。 如果贵组织始终达到这些限制，请联系您的客户代表以讨论提高金额的问题。
