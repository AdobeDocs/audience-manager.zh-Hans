---
description: 实时入站数据获取过程使用用户浏览器发出的一系列HTTP请求将数据传递给Audience Manager。
seo-description: 实时入站数据获取过程使用用户浏览器发出的一系列HTTP请求将数据传递给Audience Manager。
seo-title: 实时入站数据摄取
solution: Audience Manager
title: 实时入站数据摄取
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---


# 实时入站数据摄取 {#real-time-inbound-data-ingestion}

实时入站数据获取过程使用来自 `HTTP` 用户浏览器的一系列请求将数据传递给Audience Manager。

<!-- c_rt_inbound_real_time.xml -->

入站数据应格式化为称为信号的键值对。 通常，每个信号被映射到通过用户界面或管理的区段 [!DNL API]。

## URL字符串参数和语法 {#url-string-syntax}

入站 [!DNL URL] 数据传输的变量应包含下述变量。 在设 [置实时](../../../features/traits/create-onboarded-rule-based-traits.md) 数据传输之前， [请记住](../../../features/traits/trait-storage.md#create-trait-storage-folder) 在UI中创建特征 [!DNL Audience Manager] 和文件夹结构。

>[!NOTE]
>
>将斜体内容替换为实际参数值。

| 参数 | 描述 |
|---|---|
| `<KEY>` | 键值对中的唯一标识符（例如性别、颜色、价格）。 |
| `<VAL>` | 属于由键定义的数据集的变量（例如，性别=男性、颜色=绿色、价格=100） |

### URL语法

在实时入站数据获取过程中，格式正确的字符串 [!DNL URL] 使用以下语法：

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
