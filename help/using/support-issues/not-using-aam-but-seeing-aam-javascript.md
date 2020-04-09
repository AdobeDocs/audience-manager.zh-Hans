---
description: 我们不使用受众管理器，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
seo-description: 我们没有使用，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
seo-title: 我们不使用受众管理器，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
solution: Audience Manager
title: 我们不使用受众管理器，但在Javascript调试器中看到受众管理器Javascript调用——原因何在？
translation-type: tm+mt
source-git-commit: 7206b43562eded19bfb30f8aea3bcad946a3f834

---


# 我们不是受众经理客户，但可以在我们的站点上查看受众经理Javascript调用

## 问题

我们不使用Adobe受众管理器，但在Javascript调试器中看到受众管理器Javascript调用。  为什么会发生这种情况？

## 回答

您可能正在您的属性上运行访客ID服务。 如果您是，获得此AAM引用不一定引用运行受众管理器的属性，但这意味着受众管理器实际上是此服务的动力。

请注意，AAM调用通常用于同步设置客户ID。
