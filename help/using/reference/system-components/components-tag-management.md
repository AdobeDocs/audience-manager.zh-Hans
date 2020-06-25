---
description: Audience Manager标签管理组件包括客户端门户、Adobe标签管理器(已弃用，支持Adobe动态标签管理器和Adobe Experience Platform启动)、DIL、Akamai和控制数据库。
seo-description: Audience Manager标签管理组件包括客户端门户、Adobe标签管理器(已弃用，支持Adobe动态标签管理器和Adobe Experience Platform启动)、DIL、Akamai和控制数据库。
seo-title: 标记管理组件
solution: Audience Manager
title: 标记管理组件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 5%

---


# 标记管理组件{#tag-management-components}

Audience Manager标签管理组件包括客户端门户、Adobe标签管理器(已弃用，支持Adobe动态标签管理器和Adobe Experience Platform启动)、DIL、Akamai和控制数据库。

<!-- 

c_comptag.xml

 -->

Audience Manager包含以下组件：

* [客户端门户](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [数据信息库(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制数据库](../../reference/system-components/components-tag-management.md#control-database)

## 客户端门户 {#client-portal}

客户端门户是标记和数据管理的主用户界面(UI)。 客户使用门户处理标记、构建特征和细分、设置目标并通过报告监控活动效果。

## DIL/TIM容器 {#dil-tim}

该容器 [!UICONTROL DIL] 有助于将 [!DNL Audience Manager] 数据收集代码部署到您的网站。 [!UICONTROL TIM] 是已弃用的标记插入管理器。 它不再被使用 [!DNL Audience Manager]。 而是使用 [动态标签管理](https://docs.adobe.com/content/help/zh-Hans/dtm/using/dtm-home.html) 或Adobe Experience Platform启 [!DNL Audience Manager] 动中的扩 [展来配置和生](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 成容器代码，将这些代码放在库存的页面上。 容器 [!UICONTROL DTM] 与协作， [!UICONTROL Data Information Library (DIL)] 从您的站点收集数据并将其发送到 [!DNL Audience Manager]。

## 数据集成库 (DIL) {#dil}

数 [据信息库](../../dil/dil-overview.md) (DIL)是一个自包含的API模块，用于从您的网站收集数据。 [!UICONTROL DIL] 有助于消除为数据收集、集成、读取cookie值和恢复页面数据编写特殊代码的需求。 [!UICONTROL DIL] 自动执行这些操作。 此外， [!UICONTROL DIL] 还小巧。 它是一个自包含的代码库，有助于减少收集信息所需的代码量。 最后，帮 [!UICONTROL DIL] 助您在Experience Cloud [!DNL Audience Manager] 中与其他产品进行 [!DNL Adobe] 集成。

## Akamai {#akamai}

[!DNL Audience Manager] 使 [用Akamai](https://www.akamai.com/html/about/index.html) 托管和提供来自我们自己的标签管理平台（称为“标签管理”）的容器 [!UICONTROL TIM (Tag Insertion Manager)]代码。 但是，已逐 [!UICONTROL TIM] 步取消代码部署，支持 [!DNL Adobe Dynamic Tag Management] 和 [!DNL Adobe Experience Platform Launch]。

## 控制数据库 {#control-database}

控制数据库：

* 处理来自门户的客户端输入（例如，创建特征和目标）。
* 将数据传输到Akamai,Akamai包括用于构建容器模板和目标发布iFrame的数据。
* 返回UI报告系统的数据。

