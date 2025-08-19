---
description: Audience Manager标签管理组件包括客户端门户、Adobe Tag Manager(已弃用，取而代之的是Adobe Experience Platform Launch)、DIL、Akamai和控制数据库。
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management组件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# Tag Management组件{#tag-management-components}

Audience Manager标签管理组件包括客户端门户、Adobe Tag Manager(已弃用，取而代之的是Adobe Experience Platform Tags)、DIL、Akamai和控制数据库。

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

客户端门户是用于标记和数据管理的主要用户界面(UI)。 客户可使用该门户处理标记、构建特征和区段、设置目标以及通过报表监控促销活动效果。

## DIL/TIM容器 {#dil-tim}

[!UICONTROL DIL]容器有助于将[!DNL Audience Manager]数据收集代码部署到您的网站。 [!UICONTROL TIM]是已弃用的标记插入管理器。 [!DNL Audience Manager]不再使用它。 您而是使用[!DNL Audience Manager]Adobe Experience Platform Tags[中的](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html)扩展来配置和生成您放置在库存页面上的容器代码。

## 数据集成库 (DIL) {#dil}

[数据信息库](../../dil/dil-overview.md) (DIL)是一个自包含的API模块，用于从您的网站收集数据。 [!UICONTROL DIL]有助于消除为数据收集、集成、读取Cookie值和恢复页面数据编写特殊代码的需要。 [!UICONTROL DIL]自动执行这些操作。 此外，[!UICONTROL DIL]是紧凑的。 它是一个自包含的代码库，可帮助减少收集信息所需的代码量。 最后，[!UICONTROL DIL]帮助您将[!DNL Audience Manager]与[!DNL Adobe] Experience Cloud中的其他产品集成。

## Akamai {#akamai}

[!DNL Audience Manager]使用[Akamai](https://www.akamai.com/us/en/about/)从我们自己的标签管理平台（称为[!UICONTROL TIM (Tag Insertion Manager)]）托管和交付容器代码。 但是，使用[!UICONTROL TIM]的代码部署已逐步退出，取而代之的是[!DNL Adobe Experience Platform Tags]。

## 控制数据库 {#control-database}

控制数据库：

* 处理来自门户的客户端输入（例如，创建特征和目标）。
* 将数据发送到Akamai，其中包括用于构建容器模板和目标发布iFrame的数据。
* 返回UI报表系统的数据。
