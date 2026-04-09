---
description: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 98%

---

# 我们不是 Audience Manager 客户，但却在我们的网站上看到 Audience Manager Javascript 调用

## 问题

我们未使用 Adobe Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用。

为什么会出现这种情况？

## 回答

您可能正在对资产运行 [Experience Cloud 身份标识服务](https://experienceleague.adobe.com/docs/id-service/using/home.html)。如果是这样的话，那么看到 Audience Manager Javascript 调用不一定意味着您正在运行 Audience Manager，而是意味着 Audience Manager 正在为身份标识服务提供支持。

Audience Manager 服务器调用通常用于[同步客户 ID](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html)。
