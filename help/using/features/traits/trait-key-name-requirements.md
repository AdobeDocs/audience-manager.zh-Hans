---
description: 本文描述键值对中键变量使用的命名约定。
seo-description: 本文描述键值对中键变量使用的命名约定。
seo-title: 关键变量的名称要求
solution: Audience Manager
title: 关键变量的名称要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# 关键变量的名称要求 {#name-requirements-for-key-variables}

本文描述键值对中键变量使用的命名约定。

## 密钥的命名要求

<!-- c_tb_key_name_requirements.xml -->

在 [!UICONTROL Expression Builder]中，键值对中的键变量名称可以由任意数字组成，后跟1个（或多个）字母、短划线、下划线和附加数字。

* 有效密钥名： `price123`, `123price`, `price-123`, `c_price123`.

* 键名无效： `123`, `price!123`。

## 为关键变量添加前缀 `c_`

如果 `c_` 在事件 ** 调用URL上发送数据的参数使用该语法，则前缀始终是必需的。