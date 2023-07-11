---
description: 通过“管理”菜单下的选项，可创建Audience Manager用户并将其分配给组。 您还可以查看限制（特征、区段、目标和模型）。
keywords: rbac；RBAC；基于角色；基于角色；基于角色的访问控制
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 2%

---

# [!UICONTROL Administration] （RBAC控制） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 用户帐户管理正在转移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html). 要开始用户迁移，我们要求所有Audience Manager客户立即采取本文中所述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，本文档中的用户管理部分将消失。

>[!IMPORTANT]
>
> 在可以使用之前 [!DNL RBAC]，此功能必须由Adobe为您的组织启用。 请联系您的帐户团队以请求 [!DNL RBAC] 激活，或联系客户关怀团队。


下的选项 [!UICONTROL Administration] 菜单可让您创建Audience Manager用户并将其分配给组。 您还可以查看限制（特征、区段、目标和模型）。

企业客户使用 [!DNL Audience Manager] 需要有一个数据管理平台来处理其所有数据，但必须能够控制不同数据元素对特定业务部门的可见性。 您可以使用组权限(也称为 [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC])。

[!DNL Audience Manager] 使用组分配权限。 未在用户级别分配权限。 组权限与对象相关联([!UICONTROL traits]、区段等) 以及您可以对这些对象执行的操作（编辑、查看等）。 这些控件也可以通过Audience ManagerREST API使用。 参见 [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)， [组管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)、和 [权限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) api方法。

## 创建用户 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 用户帐户管理正在转移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html). 要开始用户迁移，我们要求所有Audience Manager客户立即采取本文中所述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，本文档的用户管理部分将消失。
> 
在中创建用户 [!DNL Audience Manager] 和指定用户详细信息、登录状态以及将用户分配给组。

1. 单击 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 单击 ![](assets/icon_add.png) 以显示 [!UICONTROL Create New User] 页面。
1. 下 **[!UICONTROL User Details]**，填写以下字段：
   * **[!UICONTROL Username]：** 指定Audience Manager的唯一用户名。
   * **[!UICONTROL First Name]：** 指定用户的名字。
   * **[!UICONTROL Last Name]：** 指定用户的姓氏。
   * **[!UICONTROL Email Address]：** 指定用户的电子邮件地址。 [!DNL Audience Manager] 不向用户发送定期通知。 [!DNL Audience Manager] 管理员可以访问用户的电子邮件地址，并且可以根据需要手动向用户发送电子邮件。 例如，如果用户忘记了密码，则使用此字段中指定的电子邮件地址来发送临时密码和重置密码的说明。
   * **[!UICONTROL Phone Number]：** 指定用户的电话号码。
   * **[!UICONTROL Is Admin]：** 指定此用户是否为 [!DNL Audience Manager] 管理员。 管理员用户可以管理用户（创建、编辑等） 和组（创建、分配权限等）。 非管理员用户只能控制自己的用户配置文件，包括编辑其电子邮件地址和重置其密码。 有关更多信息，请参阅 [编辑帐户设置](../../features/administration/edit-account-settings.md).
1. 下 **[!UICONTROL Login]**&#x200B;中，选择所需的状态：
   * **[!UICONTROL Active]：**  活动用户可以访问 [!DNL Audience Manager] 并具有组成员资格授予的权限。
   * **[!UICONTROL Deactivated]：**  已停用用户无法访问 [!DNL Audience Manager] 并且没有任何权限。 如果取消激活用户，则其用户信息将保留在 [!DNL Audience Manager] 如果必要的话，你可以简单地重新激活它们。 如果删除用户，则必须在用户需要使用时重新创建用户 [!DNL Audience Manager] 将来再来一次。
   * **[!UICONTROL Expired]：** 用户的密码超过90天。
   * **[!UICONTROL Pending]：** 用户具有临时密码，例如在密码重置后或作为全新帐户，并且用户尚未设置永久密码。
   * **[!UICONTROL Locked Out]：** 5次不正确的登录尝试将锁定用户。
1. 下 **[!UICONTROL Assigned Groups]**，从下拉列表中选择想要为其分配此用户的组。
有关组和权限的更多信息，请参阅 [创建组](../../features/administration/administration-overview.md#create-group).
1. 单击 **[!UICONTROL Save]**.

## 创建一个 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 用户帐户管理正在转移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html). 要开始用户迁移，我们建议所有Audience Manager客户立即采取本文中所述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，此部分将消失。

A *群组* 是对共享访问权限的用户集合 [!UICONTROL destination]， [!UICONTROL segment]、和 [!UICONTROL trait] 对象。 您可以将组限制为仅单个对象，也可以授予他们对不同对象组合的广泛访问权限。

<!-- t_create_groups.xml -->

要创建组，请执行以下操作：

1. 单击 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 单击  ![](assets/icon_add.png) 以打开 [!UICONTROL Group Settings] 页面。
3. 在 [!UICONTROL Group Details]:
   * 命名组。
   * 提供简要的组描述。
4. In [!UICONTROL Group Members]，单击以下位置中的用户： **[!UICONTROL Add Users]** 选项以将它们添加到组中。
5. In [!UICONTROL Group Permissions]，选择一个 [特征](../../features/traits/trait-details-page.md)， [区段](../../features/segments/segments-purpose.md)，或 [目标](../../features/destinations/destinations.md) 起始日期 **[!UICONTROL Add Object]**.
这将打开选定对象的权限窗口。
6. 选中您希望群组成员拥有的权限对应的复选框。
7. *（可选）* 分配 [通配符权限](../../features/administration/administration-overview.md#wild-card-permissions) 加入群组。
8. 单击 **[!UICONTROL Save Group]**.

## 了解 [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 用户帐户管理正在转移到 [Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html). 要开始用户迁移，我们建议所有Audience Manager客户立即采取本文中所述的必要措施： [Audience Manager用户迁移到Admin Console](admin-console-migration.md).
> 
> 在迁移完所有客户后，此部分将消失。

简化组权限管理 [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 让组成员自动访问与关联的每个数据源 [!UICONTROL segment]， [!UICONTROL destination]，或 [!UICONTROL trait]. 相比之下，常规权限仅允许您分配特定的 [!UICONTROL data sources] 这些物件中的一个。 而且，当您添加新时 [!UICONTROL data sources]，组成员无权访问这些新源。

您必须打开组权限并分配这些新权限 [!UICONTROL data sources] 加入群组。 [!UICONTROL Wild Card Permissions] 可让您避免使用本手册 [!UICONTROL data source] 更新过程。 组具有 [!UICONTROL Wild Card Permissions] 获取对新增内容的访问权限 [!UICONTROL data sources] 未经明确授权。

![](assets/wild-card.png)

请阅读下文，了解每种体验的 [!UICONTROL wildcard permission] 表示：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS`  — 用户可以选择 [!UICONTROL traits] 作为的基准 [!UICONTROL models].
* `EDIT_ALL_TRAITS`  — 用户可以编辑所有 [!UICONTROL traits] 在其公司帐户中设置。
* `VIEW_ALL_TRAITS`  — 用户可以查看全部 [!UICONTROL traits] 在其公司帐户中设置。
* `DELETE_ALL_TRAITS`  — 用户可以删除所有 [!UICONTROL traits] 在其公司帐户中设置。
* `CREATE_ALL_ALGO_TRAITS`  — 用户可以创建 [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS`  — 用户可以添加任意 [!UICONTROL traits] 属于其公司 [!UICONTROL segments].
* `CREATE_ALL_TRAITS`  — 用户可以创建 [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS`  — 用户具有查看权限 [!UICONTROL models] 属于他们的公司。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS`  — 用户可以查看所有 [!UICONTROL derived signals] 属于他们的公司。
* `CREATE_DERIVED_SIGNALS`  — 用户可以创建 [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS`  — 用户可以编辑所有 [!UICONTROL derived signals] 属于他们的公司。
* `DELETE_DERIVED_SIGNALS`  — 用户可以删除任何 [!UICONTROL derived signals] 属于他们的公司。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS`  — 用户可以编辑所有 [!UICONTROL destinations] 在其公司帐户中设置。
* `CREATE_DESTINATIONS`  — 用户可以创建 [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS`  — 用户可以查看所有 [!UICONTROL destinations] 在其公司帐户中设置。
* `DELETE_ALL_DESTINATIONS`  — 用户可以删除所有 [!UICONTROL destinations] 在其公司帐户中设置。

**[!UICONTROL Tags]**

* `VIEW_TAGS`  — 用户可对其执行任何操作（查看、创建、编辑、删除） [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS`  — 用户可对其执行任何操作（查看、创建、编辑、删除） [!UICONTROL Audience Lab] 测试组。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS`  — 用户可以创建区段。
* `DELETE_ALL_SEGMENTS`  — 用户可以删除在其公司帐户内设置的所有区段。
* `MAP_ALL_TO_DESTINATIONS`  — 用户可以将属于其公司的任何区段映射到目标。
* `EDIT_ALL_SEGMENTS`  — 用户可以编辑在其公司帐户内设置的所有区段。
* `MAP_ALL_SEGMENTS_TO_MODELS`  — 用户可以选择区段作为模型的基线。
* `VIEW_ALL_SEGMENTS`  — 用户可以查看在其公司帐户内设置的所有区段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS`  — 用户可以查看在中捕获的所有信号 [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## 用例 {#use-cases}

### 监控用户访问 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可以帮助您监控用户登录状态，让您清楚地了解谁可以访问您的Audience Manager实例。

根据您的业务要求，您可以根据需要启用和禁用用户帐户。

![监控用户访问](assets/monitor-user-access.png)

### 确保对敏感数据的访问保护 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

您可以配置 [!UICONTROL Role-Based Access Control] 在 [!UICONTROL trait]、区段和 [!UICONTROL destination] 级别，代表每个用户组。

此功能可帮助您管理用户查看、创建、读取、写入和编辑特定数据集的方式，甚至限制用户访问不应向他们提供的数据集。

![访问保护](assets/access-protection.png)
