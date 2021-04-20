---
description: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
seo-description: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
seo-title: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
solution: Audience Manager
title: 我们未使用 Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用，这是为什么？
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 100%

---

# 我们不是 Audience Manager 客户，但却在我们的网站上看到 Audience Manager Javascript 调用

## 问题

我们未使用 Adobe Audience Manager，但却在 Javascript 调试器中看到 Audience Manager Javascript 调用。

为什么会出现这种情况？

## 回答

您可能正在对资产运行 [Experience Cloud Identity Service](https://docs.adobe.com/content/help/zh-Hans/id-service/using/home.html)。如果是这样的话，那么看到 Audience Manager Javascript 调用不一定意味着您正在运行 Audience Manager，而是意味着 Audience Manager 正在为 Identity Service 提供支持。

Audience Manager 服务器调用通常用于[同步客户 ID](https://docs.adobe.com/content/help/zh-Hans/id-service/using/id-service-api/methods/setcustomerids.html)。
