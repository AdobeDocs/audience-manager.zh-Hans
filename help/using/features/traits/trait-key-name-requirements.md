---
description: 本文介绍了键值对中的键变量使用的命名约定。
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: 关键变量的名称要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 0%

---

# 关键变量的名称要求 {#name-requirements-for-key-variables}

本文介绍了键值对中的键变量使用的命名约定。

## 键的命名要求

<!-- c_tb_key_name_requirements.xml -->

在[!UICONTROL Expression Builder]中，键值对中的键变量名称可以包含任意数量的数字，后跟1（或多个）字母、短划线、下划线和其他数字。

* 有效的键名： `price123`、`123price`、`price-123`、`c_price123`。

* 无效键名： `123`，`price!123`。

## 为键变量添加前缀`c_`

如果在事件调用URL上发送数据的参数使用该语法，则`c_`前缀为&#x200B;*始终*。
