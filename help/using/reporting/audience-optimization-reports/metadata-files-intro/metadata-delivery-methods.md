---
description: 发送或更新元数据文件，方法是将它们发送到受众管理器帐户的特殊Amazon S3目录。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本节。
seo-description: 发送或更新元数据文件，方法是将它们发送到受众管理器帐户的特殊Amazon S3目录。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本节。
seo-title: 元数据文件的投放方法
solution: Audience Manager
title: 元数据文件的投放方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 62147fc719a59d2b2c7b444bce853334b03816c6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# 元数据文件的投放方法{#delivery-methods-for-metadata-files}

通过将元数据文件发送到受众管理器帐户的 [!DNL Amazon S3] 特殊目录来发送或更新元数据文件。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本节。

>[!IMPORTANT]
>
> 请与受众经理顾问或客户关怀联系，开始为您的元数 [!DNL Amazon S3] 据文件设置目录。

## 投放路径语法和示例 {#syntax}

数据以单独的命名空间存储在目录中，供每位客 [!DNL Amazon S3] 户使用。 文件路径遵循下面显示的语法。 注意，尖括号 `<>` 表示变量占位符。 其他元素是常量，不会更改。

**语法：**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**示例：**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

下表定义了文件投放路径中的每个元素。


| 文件参数 | 描述 |
---------|----------|
| `.../log_ingestion/` | 这是目录存储路径的开始。 设置完毕后，您将获得完整路径。 |
| `pid=<AAM ID>` | 此键值对包含您的受众经理客户ID。 |
| `dpid=<d_src>` | 此键值对包含在事件调用中传入的数据源ID。 数据源ID是将文件中的所有内容与其所属的实际数据相关联的值。 </br> 例如，假设您有一个ID为123的创意产品，并且名为“Advertiser Creative A”。 由于事件调用仅通过ID，您需要在元数据文件中包含“广告商创意A”。 活动和创意属于数据源。 数据源ID是将这些内容关联在一起的，它使我们能够准确地将文件内容与事件调用中发送的ID关联。 请参 [阅事件调用ID如何确定文件名、内容和投放路径](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)。 |
| `<yyyymmdd_0_child ID>` | 这是文件名。 请参 [阅元数据文件的命名约定](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。 |

## 文件处理时间和更新 {#processing-times}

每天以定期间隔处理元数据文件四次。

要更新元数据记录，只需发送包含新信息的文件。 您无需每次发送完整更新。
