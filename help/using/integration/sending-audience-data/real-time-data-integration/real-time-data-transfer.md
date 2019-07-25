---
description: 实时入站数据采集过程使用用户浏览器中的一系列HTTP请求将数据传递给Audience Manager。
seo-description: 实时入站数据采集过程使用用户浏览器中的一系列HTTP请求将数据传递给Audience Manager。
seo-title: 实时入站数据摄取
solution: Audience Manager
title: 实时入站数据摄取
uuid: 43cb0eBC-6c36-4391-bbfb-6b203 d63 c69 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

入站数据应格式化为称为信号的键值对。Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>将斜体内容替换为实际参数值。

| 参数 | 描述 |
|---|---|
| `<KEY>` | 密钥值对中的唯一标识符(例如，性别、颜色、价格)。 |
| `<VAL>` | 属于由键定义的数据集的变量(例如，性别=男性，color= green，price=100) |

### URL语法

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
