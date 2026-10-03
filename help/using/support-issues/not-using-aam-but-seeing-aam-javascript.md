---
description: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: 'https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
    internal-label: Administration
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
    internal-label: Support
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 88%
---
# 我们不是 Audience Manager 客户，但却在我们的网站上看到 Audience Manager Javascript 调用

## 问题

我们未使用 Adobe Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用。

为什么会出现这种情况？

## 回答

您可能正在对资产运行 [Experience Cloud 身份标识服务](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hans)。 如果是这样的话，那么看到 Audience Manager Javascript 调用不一定意味着您正在运行 Audience Manager， 而是意味着 Audience Manager 正在为身份标识服务提供支持。

Audience Manager 服务器调用通常用于[同步客户 ID](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=zh-Hans)。
