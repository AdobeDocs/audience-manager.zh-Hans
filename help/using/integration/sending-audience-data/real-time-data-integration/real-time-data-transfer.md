---
description: 实时入站数据获取过程使用用户浏览器中的一系列HTTP请求将数据传递到Audience Manager。
seo-description: 实时入站数据获取过程使用用户浏览器中的一系列HTTP请求将数据传递到Audience Manager。
seo-title: 实时入站数据摄取
solution: Audience Manager
title: 实时入站数据摄取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 8%

---

# 实时入站数据摄取 {#real-time-inbound-data-ingestion}

实时入站数据获取过程使用用户浏览器中的一系列`HTTP`请求将数据传递到Audience Manager。

<!-- c_rt_inbound_real_time.xml -->

入站数据应格式化为称为信号的键值对。 通常，每个信号都映射到通过用户界面或[!DNL API]创建或管理的区段。

## URL字符串参数和语法{#url-string-syntax}

入站数据传输的[!DNL URL]应包含以下描述的变量。 在设置实时数据传输之前，请记住在[!DNL Audience Manager] UI中[创建traits](../../../features/traits/create-onboarded-rule-based-traits.md)和[文件夹结构](../../../features/traits/trait-storage.md#create-trait-storage-folder)。

>[!NOTE]
>
>将斜体内容替换为实际参数值。

| 参数 | 描述 |
|---|---|
| `<KEY>` | 键值对中的唯一标识符（例如性别、颜色、价格）。 |
| `<VAL>` | 属于由键定义的数据集的变量（例如，性别=男性，颜色=绿色，价格=100） |

### URL语法

在实时入站数据获取过程中，格式正确的[!DNL URL]字符串使用以下语法：

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
