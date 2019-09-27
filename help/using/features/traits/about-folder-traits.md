---
description: 文件夹特征允许您将位于同一文件夹内的特征和所有子文件夹自动汇总到目标区段中。
keywords: 细分尺寸估计器
seo-description: 文件夹特征允许您将位于同一文件夹内的特征和所有子文件夹自动汇总到目标区段中。
seo-title: 关于文件夹特征
solution: Audience Manager
title: 关于文件夹特征
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

---


# 文件夹特征：关于 {#folder-traits-about}

[!UICONTROL Folder traits] 允许您自动将位于同一文件夹和所有子文件夹内的特征聚合到目标区段中。

## 使用文件夹特征的优势 {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. 这样，您就可以自动细分和定位不同文件夹级别的用户。 例如，假设您有如下的文件夹结构：

`*` Electronics (parent)

    `*` Laptops (child)

        品`*` 牌（孙子）

[!UICONTROL Folder traits] 在自动创建的文件夹(基于父文件夹的名 [!DNL Electronics] 称)中确 [!UICONTROL Folder Trait] 定这些文件夹中的所有用户的资格。 而且，当您向下移动文件结构时，此过程会重复。 在这种情况下，文件夹特征会捕获自动创建的笔记本电脑中“笔记本电脑”和“品牌”文件夹中的所有用户 [!UICONTROL Folder Trait]。

[!UICONTROL Folder traits] 在段表达式中可选。 选择 [!UICONTROL folder trait] 与选择该文件夹及其子文件夹中具有分组的所有特征等效 [!UICONTROL OR] 的。

![](assets/folder-traits-compare-border.jpg)

## 文件夹特征实现——最近和频率 {#folder-traits-realization}

文件夹特征的频率计数是其文件夹及其子文件夹中特征的实现总数。 下图显示了Automobile文件夹中的特征A、B和C。 请考虑每个特征具有以下实现：

* 特征A:5
* 特征B:1
* 特征C:1

在这种情况下， [!DNL Automobile Folder Trait] 有7个实现。

![](assets/folder_traits_rollup_border.png)

## 文件夹特征报告 {#folder-traits-reporting}

[!UICONTROL Folder traits] 从以下文件夹结构中的特征捕获所有用户。 如果将某个特征从文件夹移到另一个文件夹，则该更改会像特征规则更改 [一样传播到我们的数据收集服](../../reference/system-components/components-data-collection.md) 务器。 下次运行报告时的报告更新以反映报告日期范围(1、7、14、30、60、90)内的这一变化。 以前几天的旧报告编号不会更改。

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using  (), your users with the appropriate  permissions are able to change the data source associated to the . [!UICONTROL Role-Based Access Controls][!UICONTROL RBAC][!UICONTROL RBAC][!UICONTROL folder trait]A user must belong to a group with either of the following:

* `READ` and  group permissions to a trait data source.`WRITE`
* `VIEW_ALL_TRAITS` and  wild card permissions for trait data sources.`EDIT_ALL_TRAITS`

Learn how to assign  permissions in our administration documentation.[!UICONTROL RBAC][](../../features/administration/administration-overview.md#create-group)

## Limits and Other Considerations {#limits}

| 项目 | 描述 |
|---|---|
| 特征类型 | [!UICONTROL Onboarded traits] 并 [!UICONTROL algorithmic traits] 且为频率的实现贡献最 [!UICONTROL folder trait]多1倍。 |
| 在文件夹之间移动特征 | 将某个特征从文件夹移到另一个特征将从第一个文件夹特征中取消该特征的限定，并将其限定为第二个特征 [!UICONTROL folder trait]。 This means that if you delete or move a trait from the folder, the users in the trait's population will be unsegmented from the segments using the folder trait as a segment expression. <br> When mapping Adobe Analytics segments or report suites to your Experience Cloud organization, Audience Manager automatically creates new, corresponding, read-only segments and traits. 您不能从Audience manager编辑或更改这些特征的存储位置。 However, any change that you perform on your mapped Adobe Analytics segments or report suites reflects in Audience Manager. |
| 系统变量 | [!UICONTROL Folder traits] 无法在使用参数的事件调用中实 `d_sid` 现。 |
| 报表 | [!UICONTROL Folder traits] 是自动计算的特征，不显示在中 **[!UICONTROL Overlap Reports]**。 |