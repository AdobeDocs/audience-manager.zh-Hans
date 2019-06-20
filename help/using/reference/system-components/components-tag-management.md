---
description: Audience Manager标签管理组件包括客户门户、Adobe Tag Manager(弃用于Adobe动态标签管理器和Adobe Launch)、DIL、Akamai和控制数据库。
seo-description: Audience Manager标签管理组件包括客户门户、Adobe Tag Manager(弃用于Adobe动态标签管理器和Adobe Launch)、DIL、Akamai和控制数据库。
seo-title: 标签管理组件
solution: Audience Manager
title: 标签管理组件
uuid: e5059478-6ba7-4e1a-afec-e41 ad7 a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

Audience Manager标签管理组件包括客户门户、Adobe Tag Manager(弃用于Adobe动态标签管理器和Adobe Launch)、DIL、Akamai和控制数据库。

<!-- 

c_comptag.xml

 -->

Audience Manager包含以下组件：

* [Client Portal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM容器](../../reference/system-components/components-tag-management.md#dil-tim)
* [数据信息库(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [控制数据库](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

客户端门户是用于标签和数据管理的主要用户界面(UI)。客户使用门户来处理标记、构建特征和细分、设置目的地以及通过报告监控营销活动效果。

## DIL/TIM Container {#dil-tim}

[!UICONTROL DIL] 容器有助于将 [!DNL Audience Manager] 数据收集代码部署到您的网站。[!UICONTROL TIM] 是已弃用的标签插入管理器。It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] The container work with the to [!UICONTROL Data Information Library (DIL)] collect data from your site and send it [!DNL Audience Manager]to.

## 数据集成库 (DIL) {#dil}

[数据信息库](../../dil/dil-overview.md) (DIL)是一个独立的API模块，可从您的网站收集数据。[!UICONTROL DIL] 帮助消除了为数据收集、集成、读取cookie值和恢复页面数据编写特殊代码的需求。[!UICONTROL DIL] 自动执行这些操作。[!UICONTROL DIL] 此外，还要紧凑。它是一个自助代码库，可帮助减少收集信息所需的代码量。Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [Akamai](https://www.akamai.com/html/about/index.html) 从我们自己的标签管理平台中托管和交付容器代码 [!UICONTROL TIM (Tag Insertion Manager)]。However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

控制数据库：

* 处理门户中的客户端输入(例如，创建特征和目标)。
* 将数据传输到Akamai，Akamai包含用于构建容器模板和目标发布iFrame的数据。
* 返回UI报告系统的数据。

