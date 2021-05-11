---
description: Audience Manager标签管理组件包括客户端门户、Adobe Tag Manager(不推荐使用，而推荐使用Adobe Experience Platform Launch)、DIL、Akamai和控制数据库。
seo-description: Audience Manager标签管理组件包括客户端门户、Adobe Tag Manager(不推荐使用，而推荐使用Adobe Experience Platform Launch)、DIL、Akamai和控制数据库。
seo-title: 标记管理组件
solution: Audience Manager
title: 标记管理组件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 系统组件
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 4%

---

# 标记管理组件{#tag-management-components}

Audience Manager标签管理组件包括客户端门户、Adobe Tag Manager(不推荐使用，而推荐使用Adobe Experience Platform Launch)、DIL、Akamai和控制数据库。

<!-- 

c_comptag.xml

 -->

Audience Manager包含以下组件：

* [客户端门户](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [数据信息库(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制数据库](../../reference/system-components/components-tag-management.md#control-database)

## 客户端门户{#client-portal}

客户端门户是标记和数据管理的主用户界面(UI)。 客户使用门户来使用标记、构建特征和细分、设置目标并通过报告监控活动绩效。

## DIL/TIM容器{#dil-tim}

[!UICONTROL DIL]容器帮助将[!DNL Audience Manager]数据收集代码部署到您的网站。 [!UICONTROL TIM] 是已弃用的标记插入管理器。[!DNL Audience Manager]不再使用它。 而是使用[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)中的[!DNL Audience Manager]扩展来配置和生成您放在清单中页面上的容器代码。

## 数据集成库 (DIL) {#dil}

[数据信息库](../../dil/dil-overview.md)(DIL)是一个自包含的API模块，用于从您的网站收集数据。 [!UICONTROL DIL] 有助于消除为数据收集、集成、读取cookie值和恢复页面数据编写特殊代码的需求。[!UICONTROL DIL] 自动执行这些操作。此外，[!UICONTROL DIL]是紧凑的。 它是一个自包含的代码库，有助于减少收集信息所需的代码量。 最后，[!UICONTROL DIL]可帮助您将[!DNL Audience Manager]与[!DNL Adobe]Experience Cloud中的其他产品集成。

## Akamai {#akamai}

[!DNL Audience Manager] 使 [](https://www.akamai.com/us/en/about/) 用Akamaito托管和交付来自我们自己的标签管理平台（称为“”）的容器 [!UICONTROL TIM (Tag Insertion Manager)]代码。但是，已逐步取消[!UICONTROL TIM]的代码部署，转而使用[!DNL Adobe Experience Platform Launch]。

## 控制数据库{#control-database}

控制数据库：

* 处理来自门户的客户端输入（例如，创建特征和目标）。
* 将数据传输到Akamai，Akamai包括用于构建容器模板和目标发布iFrame的数据。
* 返回UI报告系统的数据。
