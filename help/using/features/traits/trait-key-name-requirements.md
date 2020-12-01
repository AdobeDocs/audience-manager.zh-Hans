---
description: 本文描述键值对中键变量使用的命名约定。
seo-description: 本文描述键值对中键变量使用的命名约定。
seo-title: 关键变量的名称要求
solution: Audience Manager
title: 关键变量的名称要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 12%

---


# 关键变量的名称要求 {#name-requirements-for-key-variables}

本文描述键值对中键变量使用的命名约定。

## 密钥的命名要求

<!-- c_tb_key_name_requirements.xml -->

在[!UICONTROL Expression Builder]中，键值对中的键变量名称可以由任意数位数字组成，后跟1（或更多）个字母、短划线、下划线和附加数字。

* 有效密钥名：`price123`、`123price`、`price-123`、`c_price123`。

* 密钥名称无效：`123`, `price!123`。

## 用`c_`前缀键变量

如果在事件调用URL上发送数据的参数使用该语法，则`c_`前缀是&#x200B;*always*&#x200B;必需的。