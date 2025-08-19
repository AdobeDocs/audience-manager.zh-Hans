---
description: 通过将元数据文件发送到Audience Manager帐户的特殊Amazon S3目录来发送或更新元数据文件。 有关投放/目录路径、文件处理时间和更新的信息，请参阅此部分。
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: 元数据文件的提交方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# 元数据文件的提交方法{#delivery-methods-for-metadata-files}

通过将元数据文件发送到Audience Manager帐户的特殊[!DNL Amazon S3]目录来发送或更新元数据文件。 有关投放/目录路径、文件处理时间和更新的信息，请参阅此部分。

>[!IMPORTANT]
>
> 请联系您的Audience Manager顾问或客户关怀团队以开始使用并为元数据文件设置[!DNL Amazon S3]目录。

## 投放路径语法和示例 {#syntax}

每个客户的数据存储在[!DNL Amazon S3]目录中的单独命名空间中。 文件路径遵循如下所示的语法。 请注意，尖括号`<>`表示变量占位符。 其他元素为常量，不会更改。

**语法：**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**示例：**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

下表定义了文件投放路径中的这些元素。


| 文件参数 | 描述 |
|---------|----------|
| `.../log_ingestion/` | 这是目录存储路径的开头。 一切设置完成后，您将收到完整路径。 |
| `pid=<AAM ID>` | 此键值对包含您的Audience Manager客户ID。 |
| `dpid=<d_src>` | 此键值对包含事件调用中传入的数据源ID。 数据源ID是将文件中的所有内容与其所属的实际数据绑定的值。 </br>例如，假设您有一个名为“Advertiser Creative A”的ID为123的创意产品。 由于事件调用仅在ID中传递，因此您需要在元数据文件中包含“广告商Creative A”。 营销活动和创意内容属于数据源。 数据源ID可将这些功能联系起来，并让我们将文件内容准确地关联到在事件调用中发送的ID。 请参阅[事件调用ID如何确定文件名、内容和传递路径](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)。 |
| `<yyyymmdd_0_child ID>` | 这是文件名。 请参阅[元数据文件的命名约定](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。 |

## 文件处理时间和更新 {#processing-times}

元数据文件每天处理四次，每次都定期进行。

要更新元数据记录，只需发送包含新信息的文件。 您无需每次都发送完整更新。
