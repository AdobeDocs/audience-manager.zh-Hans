---
description: 利用文件夹特征，您可以自动将同一文件夹内驻留的特征和所有子文件夹聚集到可搜索的区段中。
keywords: 细分大小估计器；sse
seo-description: 利用文件夹特征，您可以自动将同一文件夹内驻留的特征和所有子文件夹聚集到可搜索的区段中。
seo-title: 文件夹特征
solution: Audience Manager
title: 文件夹特征
uuid: e561f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# 文件夹特征：关于关于 {#folder-traits-about}

[!UICONTROL Folder traits] 可自动将同一文件夹内驻留的特征和所有子文件夹聚集到可搜索的区段中。

## 使用文件夹特征的好处 {#benefits}

A [!UICONTROL folder trait] 包含父级文件夹中的所有特征及其关联的子文件夹。这使您能够自动细分和定位不同文件夹级别的用户。例如，假设您有一个文件夹结构：

`*` Electronics(parent)

`*` 笔记本电脑(儿童)

`*` 品牌(孙孙)

[!UICONTROL Folder traits] 确定自动创建的 [!DNL Electronics][!UICONTROL Folder Trait] 文件夹中的所有用户的资格(基于父文件夹的名称)。此外，当您向下移动文件结构时，此过程也会重复。在这种情况下，文件夹特征会捕获自动创建的便携式计算机中Lapps和Brands文件夹中的所有用户 [!UICONTROL Folder Trait]。

[!UICONTROL Folder traits] 可在区段表达式中进行选择。选择a [!UICONTROL folder trait] 等效于选择该文件夹及其子文件夹中带有 [!UICONTROL OR] 分组的所有特征。

![](assets/folder-traits-compare-border.jpg)

## 文件夹特征实现-最近缩进和频率 {#folder-traits-realization}

文件夹特征的频率是指在其文件夹及其子文件夹中特征的真实性总和。下图显示了在汽车文件夹中实时显示的特征A、B和C。请考虑，每个特征都具有如下真实性：

* 特征A：5
* 特征B：1
* 特征C：1

在这种情况下 [!DNL ]，汽车 [!UICONTROL Folder Trait] 有七项革新。

![](assets/folder_traits_rollup_border.png)

## 特征报告文件夹特征报告 {#folder-traits-reporting}

[!UICONTROL Folder traits] 从其下面的文件夹结构中的特征中捕获所有用户。如果您将特征从文件夹移动到另一个文件夹，更改将像特征规则更改一样传播到 [我们的数据收集服务器](../../reference/system-components/components-data-collection.md) 。下一个报告中的报告更新可反映报表日期范围内的此更改(1、7、14、30、60、90)。过去几天的旧报告编号不会更改。

## 基于角色的访问控制(CLUAC)权限 {#role-based-access-controls}

对于使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])的公司，具有相应 [!UICONTROL RBAC] 权限的用户可以更改与此关联的数据源 [!UICONTROL folder trait]。用户必须属于以下任一组：

* `READ``WRITE` 和组权限。
* `VIEW_ALL_TRAITS` 以及 `EDIT_ALL_TRAITS` 特征数据源的通配符权限。

了解如何在 [!UICONTROL RBAC][管理文档](../../features/administration/administration-overview.md#create-group)中分配权限。

## 限制和其他注意事项 {#limits}

| 项目 | 描述 |
|---|---|
| 特征类型 | [!UICONTROL Onboarded traits][!UICONTROL algorithmic traits] 并贡献最大的一个频率 [!UICONTROL folder trait]。 |
| 在文件夹之间移动特征 | 将特征从文件夹移动到另一个文件夹将不符合第一个文件夹特征的资格，并符合第二 [!UICONTROL folder trait]个特征。这意味着如果您从文件夹删除或移动特征，则特征的人群中的用户将使用文件夹特征作为区段表达式从区段中取消分段。<br> 将Adobe Analytics区段或报表包映射到Experience Cloud组织时，Audience Manager会自动创建新的、对应的、只读的细分和特征。您无法从Audience Manager编辑或更改这些特征的存储位置。但是，在Audience Manager中对映射的Adobe Analytics区段或报表包执行的任何更改都会反映出来。 |
| 系统变量 | [!UICONTROL Folder traits] 无法在使用 `d_sid` 参数的事件调用中进行识别。 |
| 报表 | [!UICONTROL Folder traits] 是实例化的特征，不会出现在 **[!UICONTROL Overlap Reports]**&#x200B;中。 |