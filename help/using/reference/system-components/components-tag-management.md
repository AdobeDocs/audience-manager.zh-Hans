---
description: Audience manager标签管理组件包括客户端门户、Adobe标签管理器（已弃用，而Adobe Dynamic Tag Manager和Adobe Launch是弃用的）、DIL、Akamai和控制数据库。
seo-description: Audience manager标签管理组件包括客户端门户、Adobe标签管理器（已弃用，而Adobe Dynamic Tag Manager和Adobe Launch是弃用的）、DIL、Akamai和控制数据库。
seo-title: 标签管理组件
solution: Audience Manager
title: 标签管理组件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# 标签管理组件{#tag-management-components}

Audience manager标签管理组件包括客户端门户、Adobe标签管理器（已弃用，而Adobe Dynamic Tag Manager和Adobe Launch是弃用的）、DIL、Akamai和控制数据库。

<!-- 

c_comptag.xml

 -->

Audience manager包含以下组件：

* [客户端门户](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [数据信息库(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制数据库](../../reference/system-components/components-tag-management.md#control-database)

## 客户端门户 {#client-portal}

客户端门户是用于标签和数据管理的主要用户界面(UI)。 客户使用门户使用标记、构建特征和区段、设置目标以及通过报告监控营销活动效果。

## DIL/TIM容器 {#dil-tim}

容器 [!UICONTROL DIL] 有助于将数据 [!DNL Audience Manager] 收集代码部署到您的网站。 [!UICONTROL TIM] 是已弃用的标记插入管理器。 它不再被使用 [!DNL Audience Manager]。 而是使用 [Adobe Launch](https://marketing.adobe.com/resources/help/en_US/dtm/)[!DNL Audience Manager][](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 中的动态标签管理或扩展来配置和生成您放在库存页面上的容器代码。 容 [!UICONTROL DTM] 器与一起从站 [!UICONTROL Data Information Library (DIL)] 点收集数据并将其发送到 [!DNL Audience Manager]。

## 数据集成库 (DIL) {#dil}

数 [据信息库](../../dil/dil-overview.md) (DIL)是一个自包含的API模块，用于从您的网站收集数据。 [!UICONTROL DIL] 有助于消除为数据收集、集成、读取Cookie值和恢复页面数据而编写特殊代码的需求。 [!UICONTROL DIL] 自动执行这些操作。 此外， [!UICONTROL DIL] 还紧凑。 它是一个自包含的代码库，有助于减少收集信息所需的代码量。 最后，帮 [!UICONTROL DIL] 助您与 [!DNL Audience Manager] Experience cloud中的其他产品 [!DNL Adobe] 集成。

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [Akamai](https://www.akamai.com/html/about/index.html) ，通过我们自己的标签管理平台（称为“Akamai”）托管和交付容器代码 [!UICONTROL TIM (Tag Insertion Manager)]。 但是，已逐步取消 [!UICONTROL TIM] 与的代码部署，以支持 [!UICONTROL Adobe Dynamic Tag Management] 和 [!UICONTROL Adobe Launch]。

## 控制数据库 {#control-database}

控制数据库：

* 处理来自门户的客户端输入（例如，创建特征和目标）。
* 将数据传输到Akamai,Akamai包括用于构建容器模板和目标发布iFrame的数据。
* 返回UI报表系统的数据。

