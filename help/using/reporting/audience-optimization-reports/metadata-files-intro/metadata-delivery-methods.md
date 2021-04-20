---
description: 通过将元数据文件发送到您的Audience Manager帐户的特殊Amazon S3目录，发送或更新这些元数据文件。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本节。
seo-description: 通过将元数据文件发送到您的Audience Manager帐户的特殊Amazon S3目录，发送或更新这些元数据文件。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本节。
seo-title: 元数据文件的传输方法
solution: Audience Manager
title: 元数据文件的传输方法
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 5%

---

# 元数据文件的传输方法{#delivery-methods-for-metadata-files}

通过将元数据文件发送到您的Audience Manager帐户的特殊[!DNL Amazon S3]目录，即可发送或更新元数据文件。 有关投放/目录路径、文件处理时间和更新的信息，请参阅本节。

>[!IMPORTANT]
>
> 请与您的Audience Manager顾问或客户关怀部门联系，开始为您的元数据文件设置[!DNL Amazon S3]目录。

## 投放路径语法和示例{#syntax}

数据存储在[!DNL Amazon S3]目录中每个客户的单独命名空间中。 文件路径遵循下面显示的语法。 注意，尖括号`<>`表示变量占位符。 其他元素是常量，不会更改。

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
---------|----------|
| `.../log_ingestion/` | 这是目录存储路径的开始。 设置完毕后，您将获得完整路径。 |
| `pid=<AAM ID>` | 此键值对包含您的Audience Manager客户ID。 |
| `dpid=<d_src>` | 此键值对包含在事件调用中传入的数据源ID。 数据源ID是将文件中的所有内容与其所属的实际数据关联起来的值。 </br> 例如，假设您有一个ID为123的创意，并且名为“Advertiser Creative A”。 由于事件调用仅通过ID，您需要在元数据文件中包含“广告商创意A”。活动和创意属于数据源。 数据源ID是将这些内容关联在一起的原因，它使我们能够准确地将文件内容与通过事件调用发送的ID关联。 请参阅[事件调用ID如何确定文件名、内容和投放路径](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)。 |
| `<yyyymmdd_0_child ID>` | 这是文件名。 请参阅[元数据文件的命名约定](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)。 |

## 文件处理时间和更新{#processing-times}

每天处理四次元数据文件，间隔为定期。

要更新元数据记录，只需发送包含新信息的文件。 您无需每次发送完整更新。
