---
description: 通过文件夹特征，您可以将位于同一文件夹和所有子文件夹中的特征自动聚合到可定位的区段中。
keywords: 区段大小估算器；sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: 文件夹特征关于
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# 文件夹特征：关于 {#folder-traits-about}

[!UICONTROL Folder traits]允许您自动将驻留在同一文件夹和所有子文件夹中的特征聚合到可定位的区段中。

## 使用文件夹特征的好处 {#benefits}

[!UICONTROL folder trait]包含父文件夹及其关联的子文件夹中的所有特征。 这样，您就可以在不同的文件夹级别自动对用户进行分段和定位。 例如，假设您的文件夹结构如下所示：

`*`电子（父）

    `*`台笔记本电脑（子）

        `*`个品牌（孙子）

[!UICONTROL Folder traits]在自动创建的[!DNL Electronics] [!UICONTROL Folder Trait]中限定这些文件夹中的所有用户（基于父文件夹的名称）。 而且，当您在文件结构中向下移动时，此过程会重复执行。 在这种情况下，文件夹特征会捕获自动创建的Laptops [!UICONTROL Folder Trait]中Laptops和Brands文件夹中的所有用户。

[!UICONTROL Folder traits]在区段表达式中是可选的。 选择[!UICONTROL folder trait]等同于选择该文件夹及其子文件夹中包含[!UICONTROL OR]分组的所有特征。

![](assets/folder-traits-compare-border.jpg)

## 文件夹特征实现 — 回访间隔和频度 {#folder-traits-realization}

文件夹特征的频率计数是其文件夹及其子文件夹中特征的实现总和。 下图显示了位于Automobile文件夹中的特征A、B和C。 假定每个特征都具有以下实现方式：

* 特征A：5个
* 特征B：1
* 特征C：1

在这种情况下，[!DNL Automobile Folder Trait]有7个实现。

![](assets/folder_traits_rollup_border.png)

## 文件夹特征报表 {#folder-traits-reporting}

[!UICONTROL Folder traits]从用户下方的文件夹结构中的特征中捕获所有用户。 如果将某个特征从文件夹移动到另一个文件夹，则该更改会像特征规则更改一样传播到我们的[数据收集服务器](../../reference/system-components/components-data-collection.md)。 下次报表运行中的报表将进行更新，以反映报表日期范围(1、7、14、30、60、90)内的此更改。 过去日期的旧报表编号不会更改。

## 基于角色的访问控制(RBAC)权限 {#role-based-access-controls}

对于使用[!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])的公司，具有适当[!UICONTROL RBAC]权限的用户可以更改与[!UICONTROL folder trait]关联的数据源。 用户必须属于具有以下任一条件的组：

* `READ`和`WRITE`对特征数据源的组权限。
* 特征数据源的`VIEW_ALL_TRAITS`和`EDIT_ALL_TRAITS`通配符权限。

在[管理文档](../../features/administration/administration-overview.md#create-group)中了解如何分配[!UICONTROL RBAC]权限。

## 限制和其他注意事项 {#limits}

| 项目 | 描述 |
|---|---|
| 特征类型 | [!UICONTROL Onboarded traits]和[!UICONTROL algorithmic traits]对[!UICONTROL folder trait]的频率最多有1个实现贡献。 |
| 在文件夹之间移动特征 | 将特征从文件夹移动到另一个文件夹会取消该特征从第一个文件夹特征的资格，并为其授予第二个[!UICONTROL folder trait]的资格。 这意味着如果从文件夹中删除或移动特征，则特征群体中的用户将使用文件夹特征作为区段表达式从区段中取消分段。 <br>将Adobe Analytics区段或报表包映射到您的Experience Cloud组织时，Audience Manager会自动创建对应的新只读区段和特征。 您无法从Audience Manager中编辑或更改这些特征的存储位置。 但是，您对映射的Adobe Analytics区段或报表包执行的任何更改都会反映在Audience Manager中。 |
| 系统变量 | 无法使用`d_sid`参数在事件调用中实现[!UICONTROL Folder traits]。 |
| 报表 | [!UICONTROL Folder traits]是自动计算的特征，不会出现在&#x200B;**[!UICONTROL Overlap Reports]**&#x200B;中。 |
