---
description: 本文描述键值对中键变量使用的命名约定。
seo-description: 本文描述键值对中键变量使用的命名约定。
seo-title: 关键变量的名称要求
solution: Audience Manager
title: 关键变量的名称要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: 4bf32099e964c421d943d9925c74dd0d4d6ee576
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 12%

---


# 关键变量的名称要求 {#name-requirements-for-key-variables}

本文描述键值对中键变量使用的命名约定。

## 密钥的命名要求

<!-- c_tb_key_name_requirements.xml -->

在 [!UICONTROL Expression Builder]中，键值对中键变量的名称可以由任意数位数字组成，后跟1个（或多个）字母、短划线、下划线和附加数字。

* 有效密钥名： `price123`、 `123price`、 `price-123`、 `c_price123`。

* 密钥名称无效： `123`, `price!123`o.

## 用c_为关键变量前缀

如果 `c_` 在事件 *调用* URL上发送数据的参数使用该语法，则前缀始终是必需的。