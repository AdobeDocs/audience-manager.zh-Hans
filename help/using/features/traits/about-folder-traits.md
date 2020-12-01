---
description: 通过文件夹特征，您可以自动将驻留在同一文件夹内的特征和所有子文件夹聚合到目标区段中。
keywords: segment size estimator;sse
seo-description: 通过文件夹特征，您可以自动将驻留在同一文件夹内的特征和所有子文件夹聚合到目标区段中。
seo-title: 关于的文件夹特征
solution: Audience Manager
title: 关于的文件夹特征
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---


# 文件夹特征：关于 {#folder-traits-about}

[!UICONTROL Folder traits] 允许您自动将位于同一文件夹和所有子文件夹内的特征聚合到目标区段中。

## 使用文件夹特征{#benefits}的优势

[!UICONTROL folder trait]包含父文件夹及其关联子文件夹中的所有特征。 这样，您就可以在不同文件夹级别自动细分和目标用户。 例如，假设您有如下文件夹结构：

`*` 电子设备（父项）

    `*`笔记本电脑（子）

        `*`品牌（孙子）

[!UICONTROL Folder traits] 在自动创建的文件夹(基 [!DNL Electronics] [!UICONTROL Folder Trait] 于父文件夹的名称)中确定这些文件夹中的所有用户。而且，当您向下移动文件结构时，此过程会重复。 在这种情况下，文件夹特征会捕获自动创建的笔记本电脑[!UICONTROL Folder Trait]中“笔记本电脑和品牌”文件夹中的所有用户。

[!UICONTROL Folder traits] 可在段表达式中选择。选择[!UICONTROL folder trait]等效于选择该文件夹及其具有[!UICONTROL OR]分组的子文件夹中的所有特征。

![](assets/folder-traits-compare-border.jpg)

## 文件夹特征实现——最近和频率{#folder-traits-realization}

文件夹特征的频率计数是其文件夹及其子文件夹中特征的实现总数。 下图显示了Automobile文件夹中的特征A、B和C。 请考虑每个特征具有以下实现：

* 特征A:5
* 特征B:1
* 特征C:1

在这种情况下，[!DNL Automobile Folder Trait]具有7个实现。

![](assets/folder_traits_rollup_border.png)

## 文件夹特征报告{#folder-traits-reporting}

[!UICONTROL Folder traits] 从以下文件夹结构中的特征捕获所有用户。如果将某个特征从文件夹移到另一个文件夹，则所做的更改会像特征规则更改一样传播到我们的[数据收集服务器](../../reference/system-components/components-data-collection.md)。 报告在下一报告运行中更新，以反映跨报告日期范围(1、7、14、30、60、90)的此更改。 前几天的旧报告号不会更改。

## 基于角色的访问控制(RBAC)权限{#role-based-access-controls}

对于使用[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])的公司，具有相应[!UICONTROL RBAC]权限的用户能够更改与[!UICONTROL folder trait]关联的数据源。 用户必须属于具有以下任一项的组：

* `READ` 和特 `WRITE` 征数据源的组权限。
* `VIEW_ALL_TRAITS` 和特 `EDIT_ALL_TRAITS` 征数据源的通配符权限。

了解如何在我们的[管理文档](../../features/administration/administration-overview.md#create-group)中分配[!UICONTROL RBAC]权限。

## 限制和其他注意事项{#limits}

| 项目 | 描述 |
|---|---|
| 特征类型 | [!UICONTROL Onboarded traits] 并 [!UICONTROL algorithmic traits] 为频率的实现贡献最 [!UICONTROL folder trait]多1个实现。 |
| 在文件夹之间移动特征 | 将某个特征从文件夹移到另一个将取消该特征与第一个文件夹特征的限定，并将其限定为第二个[!UICONTROL folder trait]。 这意味着，如果您从文件夹删除或移动特征，则使用文件夹特征作为区段表达式，将不会将特征填充中的用户从区段中分段。 <br> 在将Adobe Analytics区段或报表包映射到您的Experience Cloud组织时，Audience Manager会自动创建新的对应只读区段和特征。您不能编辑或更改这些特征的存储位置(来自Audience Manager)。 但是，您对映射的Adobe Analytics区段或报表包执行的任何更改都会反映在Audience Manager中。 |
| 系统变量 | [!UICONTROL Folder traits] 无法在事件调用中使用该参 `d_sid` 数。 |
| 报表 | [!UICONTROL Folder traits] 是自动计算特征，不显示在 **[!UICONTROL Overlap Reports]**&#x200B;中。 |