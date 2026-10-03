---
description: 本文介绍了键值对中的键变量使用的命名约定。
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: 关键变量的名称要求
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: 'https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b89b323a-1e91-40b1-8d20-96b5b726d55a
    internal-label: Audience management
subfeature_v2:
  - id: b1ecf375-97f8-4f5a-a937-6129552209be
    internal-label: Traits
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '108'
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
