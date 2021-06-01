---
description: 利用文件夹特征，可自动将位于同一文件夹和所有子文件夹内的特征聚合到可定位的区段中。
keywords: 区段大小估算器；SSE
seo-description: 利用文件夹特征，可自动将位于同一文件夹和所有子文件夹内的特征聚合到可定位的区段中。
seo-title: 文件夹特征关于
solution: Audience Manager
title: 文件夹特征关于
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: 特征
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# 文件夹特征：关于 {#folder-traits-about}

[!UICONTROL Folder traits] 允许您自动将位于同一文件夹和所有子文件夹中的特征聚合到可定位的区段中。

## 使用文件夹特征的好处 {#benefits}

[!UICONTROL folder trait]包含父文件夹及其关联的子文件夹中的所有特征。 这样，您就可以自动在不同文件夹级别对用户进行分段和定位。 例如，假设您的文件夹结构如下所示：

`*` 电子产品（父项）

    `*`笔记本电脑（子）

        `*`品牌（孙子）

[!UICONTROL Folder traits] 在自动创建的文件夹中(基于父 [!DNL Electronics] [!UICONTROL Folder Trait] 文件夹的名称)确定这些文件夹中的所有用户。而且，当您向下移动文件结构时，此过程会重复自己。 在这种情况下，文件夹特征会捕获自动创建的笔记本电脑[!UICONTROL Folder Trait]中Laptops和Brands文件夹中的所有用户。

[!UICONTROL Folder traits] 可在区段表达式中进行选择。选择[!UICONTROL folder trait]等同于选择该文件夹及其具有[!UICONTROL OR]分组的子文件夹中的所有特征。

![](assets/folder-traits-compare-border.jpg)

## 文件夹特征实现 — 回访间隔和频度{#folder-traits-realization}

文件夹特征的频率计数是其文件夹及其子文件夹中特征实现总数。 下图显示了特征A、B和C，它们位于Automic文件夹中。 请考虑每个特征都具有以下实现：

* 特征A:5
* 特征B:1
* 特征C:1

在这种情况下，[!DNL Automobile Folder Trait]具有7个实现。

![](assets/folder_traits_rollup_border.png)

## 文件夹特征报表{#folder-traits-reporting}

[!UICONTROL Folder traits] 在用户下面的文件夹结构中，从特征中捕获所有用户。如果将特征从文件夹移动到其他文件夹，则所做的更改会像特征规则更改一样传播到我们的[数据收集服务器](../../reference/system-components/components-data-collection.md)。 下次运行报表时，会更新报表，以反映报表日期范围(1、7、14、30、60、90)内的此更改。 前几天的旧报表数量不会更改。

## 基于角色的访问控制(RBAC)权限{#role-based-access-controls}

对于使用[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])的公司，具有相应[!UICONTROL RBAC]权限的用户能够更改与[!UICONTROL folder trait]关联的数据源。 用户必须属于具有以下任一情况的组：

* `READ` 和特 `WRITE` 征数据源的群组权限。
* `VIEW_ALL_TRAITS` 和特 `EDIT_ALL_TRAITS` 征数据源的通配符权限。

在我们的[管理文档](../../features/administration/administration-overview.md#create-group)中了解如何分配[!UICONTROL RBAC]权限。

## 限制和其他注意事项 {#limits}

| 项目 | 描述 |
|---|---|
| 特征类型 | [!UICONTROL Onboarded traits] 并 [!UICONTROL algorithmic traits] 为频度贡献最多1 [!UICONTROL folder trait]个实现。 |
| 在文件夹之间移动特征 | 将一个特征从文件夹移动到另一个特征将使该特征从第一个文件夹特征中取消资格，并使其符合第二个[!UICONTROL folder trait]。 这意味着如果您从文件夹删除或移动特征，则使用文件夹特征作为区段表达式，将从区段中取消分段特征群体中的用户。 <br> 将Adobe Analytics区段或报表包映射到Experience Cloud组织时，Audience Manager会自动创建新的对应只读区段和特征。您无法从Audience Manager中编辑或更改这些特征的存储位置。 但是，您对映射的Adobe Analytics区段或报表包执行的任何更改都会反映在Audience Manager中。 |
| 系统变量 | [!UICONTROL Folder traits] 无法在事件调用中使用参数实 `d_sid` 现。 |
| 报表 | [!UICONTROL Folder traits] 是自动计算特征，不会显示在 **[!UICONTROL Overlap Reports]**&#x200B;中。 |
