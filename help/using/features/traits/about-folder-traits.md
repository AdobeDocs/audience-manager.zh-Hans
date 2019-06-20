---
description: 利用文件夹特征，您可以自动将同一文件夹内驻留的特征和所有子文件夹聚集到可搜索的区段中。
keywords: 细分大小估计器；sse
seo-description: 利用文件夹特征，您可以自动将同一文件夹内驻留的特征和所有子文件夹聚集到可搜索的区段中。
seo-title: 文件夹特征
solution: Audience Manager
title: 文件夹特征
uuid: e561f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] 可自动将同一文件夹内驻留的特征和所有子文件夹聚集到可搜索的区段中。

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. 这使您能够自动细分和定位不同文件夹级别的用户。例如，假设您有一个文件夹结构：

`*` Electronics(parent)

`*` 笔记本电脑(儿童)

`*` 品牌(孙孙)

[!UICONTROL Folder traits] 确定自动创建的 [!DNL Electronics][!UICONTROL Folder Trait] 文件夹中的所有用户的资格(基于父文件夹的名称)。此外，当您向下移动文件结构时，此过程也会重复。In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] 可在区段表达式中进行选择。Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

文件夹特征的频率是指在其文件夹及其子文件夹中特征的真实性总和。下图显示了在汽车文件夹中实时显示的特征A、B和C。请考虑，每个特征都具有如下真实性：

* 特征A：5
* 特征B：1
* 特征C：1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] 从其下面的文件夹结构中的特征中捕获所有用户。If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. 下一个报告中的报告更新将反映在报表日期范围内的此更改(1、7、14、30、60、90、终身)。过去几天的旧报告编号不会更改。

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. 用户必须属于以下任一组：

* `READ``WRITE` 和组权限。
* `VIEW_ALL_TRAITS` 以及 `EDIT_ALL_TRAITS` 特征数据源的通配符权限。

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| 项目 | 描述 |
|---|---|
| 特征类型 | [!UICONTROL Onboarded traits][!UICONTROL algorithmic traits] 并贡献最大的一个频率 [!UICONTROL folder trait]。 |
| 在文件夹之间移动特征 | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. 这意味着如果您从文件夹删除或移动特征，则特征的人群中的用户将使用文件夹特征作为区段表达式从区段中取消分段。 |
| 系统变量 | [!UICONTROL Folder traits] 无法在使用 `d_sid` 参数的事件调用中进行识别。 |
| 报表 | [!UICONTROL Folder traits] 是实例化的特征，不会出现在 **[!UICONTROL Overlap Reports]** 中。 |