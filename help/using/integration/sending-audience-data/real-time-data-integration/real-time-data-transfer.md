---
description: 实时入站数据摄取流程使用用户浏览器发出的一系列HTTP请求将数据传递到Audience Manager。
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: 实时入站数据摄取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
TQID: https://experienceleague.adobe.com/ps6Iks-zvDnIIEagSND0LEnW18K6odtuwIJOsBfp2v0
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 169
ht-degree: 1%

---

# 实时入站数据摄取 {#real-time-inbound-data-ingestion}

实时入站数据摄取流程使用用户浏览器发出的一系列`HTTP`请求将数据传递到Audience Manager。

<!-- c_rt_inbound_real_time.xml -->

入站数据的格式应是称为信号的键值对。 通常，每个信号都映射到通过用户界面或[!DNL API]创建或管理的区段。

## URL字符串参数和语法 {#url-string-syntax}

入站数据传输的[!DNL URL]应包含如下所述的变量。 在设置实时数据传输之前，请记得在[ UI中](../../../features/traits/create-onboarded-rule-based-traits.md)创建特征[和](../../../features/traits/trait-storage.md#create-trait-storage-folder)文件夹结构[!DNL Audience Manager]。

>[!NOTE]
>
>将斜体化的内容替换为实际参数值。

| 参数 | 描述 |
|---|---|
| `<KEY>` | 键值对中的唯一标识符（例如，性别、颜色、价格）。 |
| `<VAL>` | 属于键定义的数据集的变量（例如，gender=male，color=green，price=100） |

### URL语法

在实时入站数据摄取过程中，格式正确的[!DNL URL]字符串使用以下语法：

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
