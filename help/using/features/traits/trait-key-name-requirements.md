---
description: 本文描述关键值对中的键变量所使用的命名约定。
seo-description: 本文描述关键值对中的键变量所使用的命名约定。
seo-title: 关键变量的名称要求
solution: Audience Manager
title: 关键变量的名称要求
uuid: fa72e732-895d-4cf6-bea0-66b404 c2 b059
translation-type: tm+mt
source-git-commit: bdbc2525a13eb04898b0a844ba478cde07e83252

---


# Name Requirements for Key Variables {#name-requirements-for-key-variables}

本文描述关键值对中的键变量所使用的命名约定。

## 键的命名要求

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], the name of a key variable in a key-value pair can consist of any number of digits followed by 1 (or more) letters, a dash, an underscore, and additional digits.

* Valid key names: `price123`, `123price`, `price-123`, `c_price123`.

* Invalid key names: `123`, `price!123`.

## Prefixing Key Variables with `c_`

`c_`*如果在事件调用URL上发送数据的参数使用该语法，则始终* 需要前缀。