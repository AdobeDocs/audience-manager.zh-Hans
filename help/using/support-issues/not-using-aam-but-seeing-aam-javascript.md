---
description: 我们不使用受众管理器，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
seo-description: 我们没有使用，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
seo-title: 我们不使用受众管理器，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
solution: Audience Manager
title: 我们不使用受众管理器，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
translation-type: tm+mt
source-git-commit: 1f5c1a91f0b5df5291d3143d297e25128b5bb716

---


# 我们不是受众经理客户，但可以在我们的站点上查看受众经理Javascript调用

## 问题

我们不使用Adobe受众管理器，但在Javascript调试器中看到受众管理器Javascript调用。

为什么会这样？

## 回答

您可能正在您的财 [产上运行Experience Cloud Identity](https://docs.adobe.com/content/help/en/id-service/using/home.html) Service。 如果您是受众管理器，则此受众管理器引用不一定引用运行的属性。 而是意味着受众管理器为此服务提供动力。

受众管理器服务器调用通常用于同 [步客户ID](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)。
