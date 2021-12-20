---
description: 通过“管理”菜单下的选项，可以创建Audience Manager用户并将其分配给群组。 您还可以查看限制（特征、区段、目标和模型）。
keywords: RBAC；基于角色；基于角色；基于角色的访问控制
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: 8ef6e8eb4351c24b55703b1788c68c580f199fc8
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 2%

---

# [!UICONTROL Administration] （RBAC控制） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 用户帐户管理正在迁移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html). 要开始Audience Manager迁移，我们要求所有用户客户立即采取本文中描述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，本文档的用户管理部分将消失。


下的选项 [!UICONTROL Administration] 菜单，您可以创建Audience Manager用户并将其分配给群组。 您还可以查看限制（特征、区段、目标和模型）。

使用 [!DNL Audience Manager] 需要一个数据管理平台来管理其所有数据，但必须能够控制不同数据元素对特定业务部门的可见性。 您可以使用群组权限(也称为 [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC])。

[!DNL Audience Manager] 使用群组来分配权限。 未在用户级别分配权限。 群组权限与对象关联([!UICONTROL traits]、区段等) 以及可对这些对象执行的操作（编辑、查看等）。 这些控件也可通过Audience ManagerREST API使用。 请参阅 [用户管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [群组管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)和 [权限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## 创建用户 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 用户帐户管理正在迁移到 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 要开始Audience Manager迁移，我们要求所有用户客户立即采取本文中描述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，本文档的用户管理部分将消失。
在中创建用户 [!DNL Audience Manager] 和指定用户详细信息、登录状态，并将用户分配给群组。

1. 单击 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 单击 ![](assets/icon_add.png) 以显示 [!UICONTROL Create New User] 页面。
1. 在 **[!UICONTROL User Details]**，填写以下字段：
   * **[!UICONTROL Username]:** 为Audience Manager指定唯一用户名。
   * **[!UICONTROL First Name]:** 指定用户的名字。
   * **[!UICONTROL Last Name]:** 指定用户的姓氏。
   * **[!UICONTROL Email Address]:** 指定用户的电子邮件地址。 [!DNL Audience Manager] 不会向用户发送常规通知。 [!DNL Audience Manager] 管理员有权访问用户的电子邮件地址，并可以根据需要手动向用户发送电子邮件。 例如，如果用户忘记了其密码，则使用此字段中指定的电子邮件地址发送临时密码和重置密码的说明。
   * **[!UICONTROL Phone Number]:** 指定用户的电话号码。
   * **[!UICONTROL Is Admin]:** 指定此用户是否为 [!DNL Audience Manager] 管理员。 管理员用户可以管理用户（创建、编辑等） 和群组（创建、分配权限等）。 非管理员用户只能控制自己的用户配置文件，包括编辑其电子邮件地址和重置自己的密码。 有关更多信息，请参阅 [编辑帐户设置](../../features/administration/edit-account-settings.md).
1. 在 **[!UICONTROL Login]**，选择所需的状态：
   * **[!UICONTROL Active]:**  活动用户可以访问 [!DNL Audience Manager] 和拥有组成员资格授予的权限。
   * **[!UICONTROL Deactivated]:**  已停用的用户无法访问 [!DNL Audience Manager] 和没有任何权限。 如果停用用户，则其用户信息会保留在 [!DNL Audience Manager] 如有必要，您可以轻松重新激活它们。 如果删除了用户，则必须重新创建用户（如果用户需要使用） [!DNL Audience Manager] 今后再来。
   * **[!UICONTROL Expired]:** 用户的密码早于90天。
   * **[!UICONTROL Pending]:** 用户具有临时密码，例如在密码重置后或作为全新帐户，并且他们尚未设置永久密码。
   * **[!UICONTROL Locked Out]:** 5次错误的登录尝试将锁定用户。
1. 在 **[!UICONTROL Assigned Groups]**，从下拉列表中，选择要将此用户分配到的所需群组。
有关组和权限的更多信息，请参阅 [创建群组](../../features/administration/administration-overview.md#create-group).
1. 单击 **[!UICONTROL Save]**.

## 创建一个 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 用户帐户管理正在迁移到 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 为了开始用户迁移，我们建议所有Audience Manager客户立即采取本文所述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，此部分将消失。

A *群组* 是共享访问权限的用户集合 [!UICONTROL destination], [!UICONTROL segment]和 [!UICONTROL trait] 对象。 您可以仅将组限制为单个对象，或者允许组广泛访问不同对象的组合。

<!-- t_create_groups.xml -->

要创建群组，请执行以下操作：

1. 单击 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 单击  ![](assets/icon_add.png) 打开 [!UICONTROL Group Settings] 页面。
3. 在 [!UICONTROL Group Details]:
   * 命名群组。
   * 提供简短的群组描述。
4. 在 [!UICONTROL Group Members]，单击 **[!UICONTROL Add Users]** 用于将其添加到群组的选项。
5. 在 [!UICONTROL Group Permissions]，选择 [特征](../../features/traits/trait-details-page.md), [区段](../../features/segments/segments-purpose.md)或 [目标](../../features/destinations/destinations.md) 从 **[!UICONTROL Add Object]**.
此时将打开选定对象的权限窗口。
6. 选中您希望群组成员拥有的权限对应的复选框。
7. *（可选）* 分配 [通配符权限](../../features/administration/administration-overview.md#wild-card-permissions) 组。
8. 单击 **[!UICONTROL Save Group]**.

## 了解 [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 用户帐户管理正在迁移到 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 为了开始用户迁移，我们建议所有Audience Manager客户立即采取本文所述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，此部分将消失。

通过 [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 为群组成员自动访问与 [!UICONTROL segment], [!UICONTROL destination]或 [!UICONTROL trait]. 相比之下，常规权限仅允许您分配特定 [!UICONTROL data sources] 对象中的一个。 而且，当您添加 [!UICONTROL data sources]，群组成员将无法访问这些新源。

您必须打开群组权限并分配这些新权限 [!UICONTROL data sources] 组。 [!UICONTROL Wild Card Permissions] 让您避免使用本手册 [!UICONTROL data source] 更新过程。 组 [!UICONTROL Wild Card Permissions] 获取新 [!UICONTROL data sources] 没有明确的授权。

![](assets/wild-card.png)

请阅读下文，了解每个 [!UICONTROL wildcard permission] 表示：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS`  — 用户可以选择 [!UICONTROL traits] 作为 [!UICONTROL models].
* `EDIT_ALL_TRAITS`  — 用户可以编辑所有 [!UICONTROL traits] 在公司帐户中设置。
* `VIEW_ALL_TRAITS`  — 用户可以查看所有 [!UICONTROL traits] 在公司帐户中设置。
* `DELETE_ALL_TRAITS`  — 用户可以删除所有 [!UICONTROL traits] 在公司帐户中设置。
* `CREATE_ALL_ALGO_TRAITS`  — 用户可以创建 [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS`  — 用户可以添加 [!UICONTROL traits] 属于 [!UICONTROL segments].
* `CREATE_ALL_TRAITS`  — 用户可以创建 [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS`  — 用户有权查看 [!UICONTROL models] 属于他们的公司。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS`  — 用户可以查看 [!UICONTROL derived signals] 属于他们的公司。
* `CREATE_DERIVED_SIGNALS`  — 用户可以创建 [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS`  — 用户可以编辑 [!UICONTROL derived signals] 属于他们的公司。
* `DELETE_DERIVED_SIGNALS`  — 用户可以删除 [!UICONTROL derived signals] 属于他们的公司。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS`  — 用户可以编辑 [!UICONTROL destinations] 在公司帐户中设置。
* `CREATE_DESTINATIONS`  — 用户可以创建 [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS`  — 用户可以查看 [!UICONTROL destinations] 在公司帐户中设置。
* `DELETE_ALL_DESTINATIONS`  — 用户可以删除 [!UICONTROL destinations] 在公司帐户中设置。

**[!UICONTROL Tags]**

* `VIEW_TAGS`  — 用户可以对其执行所有操作（查看、创建、编辑、删除） [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS`  — 用户可以对其执行所有操作（查看、创建、编辑、删除） [!UICONTROL Audience Lab] 测试组。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS`  — 用户可以创建区段。
* `DELETE_ALL_SEGMENTS`  — 用户可以删除在其公司帐户中设置的所有区段。
* `MAP_ALL_TO_DESTINATIONS`  — 用户可以将属于其公司的任何区段映射到目标。
* `EDIT_ALL_SEGMENTS`  — 用户可以编辑其公司帐户中设置的所有区段。
* `MAP_ALL_SEGMENTS_TO_MODELS`  — 用户可以选择区段作为模型的基线。
* `VIEW_ALL_SEGMENTS`  — 用户可以查看在其公司帐户中设置的所有区段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS`  — 用户可以查看 [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## 用例 {#use-cases}

### 监控用户访问 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可以帮助您监控用户登录状态，从而清楚地了解谁可以访问您的Audience Manager实例。

根据您的业务要求，您可以根据需要启用和禁用用户帐户。

![monitor-user-access](assets/monitor-user-access.png)

### 确保对敏感数据的访问保护 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

您可以配置 [!UICONTROL Role-Based Access Control] at [!UICONTROL trait]、区段和 [!UICONTROL destination] 级别。

此功能可帮助您管理用户查看、创建、读取、写入和编辑特定数据集的方式，甚至限制用户访问他们不应使用的数据集。

![访问保护](assets/access-protection.png)
