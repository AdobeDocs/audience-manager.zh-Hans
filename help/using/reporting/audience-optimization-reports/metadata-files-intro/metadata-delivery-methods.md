---
description: 通过向 Audience Manager 帐户的特殊 Amazon S3 目录发送或更新元数据文件。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本部分。
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: 元数据文件的传输方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 3%

---

# 元数据文件的传输方法{#delivery-methods-for-metadata-files}

发送或更新元数据文件，方法是将其发送到 Audience Manager 帐户的特殊 [!DNL Amazon S3] 目录。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本部分。

>[!IMPORTANT]
>
> 请联系您的 Audience Manager 顾问或客户服务，以开始并为您的元数据文件设置 [!DNL Amazon S3] 目录。

## 提交路径语法和示例 {#syntax}

对于目录中 [!DNL Amazon S3] 的每个客户，数据都存储在单独的命名空间中。 文件路径遵循如下所示的语法。 注意，尖括号 `<>` 表示变量占位符。 其他元素是常量，不会发生变化。

**语法：**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**示例:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

下表定义了文件投放路径中的每个元素。


| 文件参数 | 描述 |
|---------|----------|
| `.../log_ingestion/` | 这是目录存储路径的开始。 设置完所有内容后，您将收到完整路径。 |
| `pid=<AAM ID>` | 此键值对包含您的 Audience Manager 客户 ID。 |
| `dpid=<d_src>` | 此键值对包含在事件调用中传递的数据源 ID。 数据源 ID 是将文件中的所有内容与所属的实际数据相联系的值。 </br> 例如，假设您有 ID 为123的创意，名称 &quot;广告商 Creative A&quot;。由于事件调用仅会在 ID 中传递，因此您需要在元数据文件中包含 &quot;广告商 Creative A&quot;。 活动和创意属于数据源。 数据源 ID 将它们结合在一起，可让我们将文件内容准确地关联到在事件调用中发送的 ID。 了解 [ 事件调用 id 是如何确定文件名称、内容和提交路径 ](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names) 的。 |
| `<yyyymmdd_0_child ID>` | 这是文件名。 请参阅 [ 元数据文件 ](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md) 的命名约定。 |

## 文件处理时间和更新 {#processing-times}

元数据文件定期处理一天四次。

要更新您的元数据记录，只需发送包含新信息的文件。 您无需每次都发送完全更新。
