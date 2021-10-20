---
description: Audience Manager标签管理组件包括客户端门户、Adobe Tag Manager(弃用而使用Adobe Experience Platform Launch)、DIL、Akamai和控制数据库。
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: 标记管理组件
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# 标记管理组件{#tag-management-components}

Audience Manager标签管理组件包括客户端门户、Adobe Tag Manager(弃用以支持Adobe Experience Platform标签)、DIL、Akamai和控制数据库。

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

客户端门户是用于标签和数据管理的主要用户界面(UI)。 客户可使用门户处理标记、构建特征和区段、设置目标，以及使用报表监控营销活动效果。

## DIL/TIM容器 {#dil-tim}

的 [!UICONTROL DIL] 容器可部署 [!DNL Audience Manager] 数据收集代码到您的网站。 [!UICONTROL TIM] 是已弃用的标签插入管理器。 不再使用 [!DNL Audience Manager]. 您而是使用 [!DNL Audience Manager] 扩展 [Adobe Experience Platform标记](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 配置并生成您放置在清单页面上的容器代码。

## 数据集成库 (DIL) {#dil}

的 [数据信息库](../../dil/dil-overview.md) (DIL)是从您的网站收集数据的自包含API模块。 [!UICONTROL DIL] 有助于消除为数据收集、集成、读取Cookie值和恢复页面数据编写特殊代码的需求。 [!UICONTROL DIL] 会自动执行这些操作。 此外， [!UICONTROL DIL] 紧凑。 它是一个自包含的代码库，有助于减少收集信息所需的代码量。 最后， [!UICONTROL DIL] 帮助您集成 [!DNL Audience Manager] 的其他产品 [!DNL Adobe] Experience Cloud。

## Akamai {#akamai}

[!DNL Audience Manager] 使用 [Akamai](https://www.akamai.com/us/en/about/) 从我们自己的标签管理平台(称为 [!UICONTROL TIM (Tag Insertion Manager)]. 但是，代码部署 [!UICONTROL TIM] 已逐步淘汰 [!DNL Adobe Experience Platform Tags].

## 控制数据库 {#control-database}

控制数据库：

* 处理来自门户的客户端输入（例如，创建特征和目标）。
* 将数据传输到Akamai，其中包括用于构建容器模板的数据以及目标发布iFrame。
* 返回UI报表系统的数据。
