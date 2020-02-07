---
description: 通过“管理”菜单下的选项，可以创建Audience manager用户并将其分配给用户组。 您还可以查看限制（特征、区段、目标和模型）。
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: 通过“管理”菜单下的选项，可以创建Audience manager用户并将其分配给用户组。 您还可以查看限制（特征、区段、目标和模型）。
seo-title: 管理
solution: Audience Manager
title: 管理
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1bde60711ca53682b6ab936a7297daf66a1bb336

---


# 管理（RBAC控制） {#administration}

![](assets/rbac-controls.png)

菜单下的选项 [!UICONTROL Administration] 允许您创建Audience manager用户并将其分配给用户组。 您还可以查看限制（特征、区段、目标和模型）。

使用一个 [!DNL Audience Manager] 数据管理平台的企业客户需要所有数据，但必须能够控制不同数据元素对特定业务单元的可见性。 您可以使用组权限(也称为())来完 [!UICONTROL Role-Based Access Control] 成此操[!UICONTROL RBAC]作。

[!DNL Audience Manager] 使用用户组分配权限。 权限未在用户级别分配。 组权限与对象（特征、区段等）关联以及可对这些对象执行的操作（编辑、查看等）。 这些控件也可通过Audience Manager REST API使用。 请参 [阅用户管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、 [组管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)和权限 [管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## Create Users {#create-users}

<!-- t_create_users.xml -->

在中创建用 [!DNL Audience Manager] 户并指定用户详细信息、登录状态和将用户分配到用户组。

1. 单击 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 单 ![](assets/icon_add.png) 击以显示 [!UICONTROL Create New User] 页面。
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **** 用户名：为Audience Manager指定唯一的用户名。
   * **** 名字：指定用户的名。
   * **** 姓氏：指定用户的姓。
   * **** 电子邮件地址：指定用户的电子邮件地址。 [!DNL Audience Manager] 不会向用户发送常规通知。 [!DNL Audience Manager] 管理员有权访问用户的电子邮件地址，并可以根据需要手动向用户发送电子邮件。 例如，如果用户忘记了密码，则此字段中指定的电子邮件地址将用于发送临时密码和重置密码的说明。
   * **** 电话号码：指定用户的电话号码。
   * **** 是管理员：指定此用户是否为管理 [!DNL Audience Manager] 员。 管理员用户可以管理用户（创建、编辑等）和用户组（创建、分配权限等）。 非管理员用户只能控制自己的用户配置文件，包括编辑其电子邮件地址和重置自己的密码。 有关详细信息，请参 [阅编辑帐户设置](../../features/administration/edit-account-settings.md)。
1. 在下 **[!UICONTROL Login]**&#x200B;面，选择所需的状态：
   * **** 活动： 活动用户可以访 [!DNL Audience Manager] 问并拥有组成员资格授予的权限。
   * **** 已取消激活： 已停用的用户无 [!DNL Audience Manager] 法访问，也没有任何权限。 如果取消激活用户，则用户信息会保留在中， [!DNL Audience Manager] 并且您可以根据需要简单地重新激活用户。 如果您删除了用户，则必须重新创建这些用户(如果他们以后需要 [!DNL Audience Manager] 再次使用)。
   * **** 已过期：用户的密码早于90天。
   * **** 待定：用户具有临时密码，例如密码重置后或全新帐户，但用户尚未设置永久密码。
   * **** 锁定：5次错误的登录尝试将锁定用户。
1. 在 **[!UICONTROL Assigned Groups]**下面，从下拉列表中，选择要将此用户分配到的所需用户组。
有关用户组和权限的详细信息，请参 [阅创建用户组](../../features/administration/administration-overview.md#create-group)。
1. 单击 **[!UICONTROL Save]**.

## 创建群组 {#create-group}

组 *是对目标* 、区段和特征对象共享访问权限的用户集合。 您可以仅将组限制为单个对象，或允许它们广泛访问不同对象的组合。

<!-- t_create_groups.xml -->

要创建用户组，请执行以下操作：

1. 单击 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. 单 ![](assets/icon_add.png) 击以打开页 [!UICONTROL Group Settings] 面。
1. 在 [!UICONTROL Group Details]:
   * 命名用户组。
   * 提供简短的用户组描述。
1. 在中， [!UICONTROL Group Members]从选项中单击用 **[!UICONTROL Add Users]** 户，将其添加到组中。
1. 在 [!UICONTROL Group Permissions]中，从特 [征](../../features/traits/trait-details-page.md)、段 [、或目](../../features/segments/segments-purpose.md)的地 [](../../features/destinations/destinations.md)**[!UICONTROL Add Object]**。
此操作将打开选定对象的权限窗口。
1. 选中您希望用户组成员具有的权限对应的复选框。
1. *（可选）* 将通配符 [权限分配给组](../../features/administration/administration-overview.md#wild-card-permissions) 。
1. 单击 **[!UICONTROL Save Group]**.

## 了解通配符权限 {#wild-card-permissions}

通过简化组权限管理 [!UICONTROL Wild Card Permissions]。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 为用户组成员提供对与区段、目标或特征关联的每个数据源的自动访问权限。 相比之下，常规权限仅允许您为其中一个对象分配特定数据源。 此外，当您添加新数据源时，组成员无法访问这些新数据源。

您必须打开用户组权限，并将这些新数据源分配给用户组。 [!UICONTROL Wild Card Permissions] 让您避免这个手动数据源更新过程。 具有组 [!UICONTROL Wild Card Permissions] 的用户无需明确授权即可访问新数据源。

![](assets/wild-card.png)

请阅读以下内容，了解每个通配符权限的含义：

**特性**

* `MAP_ALL_TRAITS_TO_MODELS` -用户可以选择特征作为模型的基线。
* `EDIT_ALL_TRAITS` -用户可以编辑在其公司帐户中设置的所有特征。
* `VIEW_ALL_TRAITS` -用户可以查看在其公司帐户中设置的所有特征。
* `DELETE_ALL_TRAITS` -用户可以删除在其公司帐户中设置的所有特征。
* `CREATE_ALL_ALGO_TRAITS` -用户可以创建算法特征。
* `MAP_ALL_TO_SEGMENTS` -用户可以将属于其公司的任何特征添加到区段。
* `CREATE_ALL_TRAITS` -用户可以创建特征。

**报告**

* `PTRREPORTS` -此通配符权限引用的功能已过时，不久将从Audience Manager UI中删除。

**型号**

* `VIEW_MODELS` -用户有权查看属于其公司的模型。

**派生信号**

* `VIEW_DERIVED_SIGNALS` -用户可以查看属于其公司的所有派生信号。
* `CREATE_DERIVED_SIGNALS` -用户可以创建派生信号。
* `EDIT_DERIVED_SIGNALS` -用户可以编辑属于其公司的所有派生信号。
* `DELETE_DERIVED_SIGNALS` -用户可以删除属于其公司的任何派生信号。

**目标**

* `EDIT_ALL_DESTINATIONS` -用户可以编辑在其公司帐户中设置的所有目标。
* `CREATE_DESTINATIONS` -用户可以创建目标。
* `VIEW_ALL_DESTINATIONS` -用户可以查看在其公司帐户中设置的所有目标。
* `DELETE_ALL_DESTINATIONS` -用户可以删除在其公司帐户中设置的所有目标。

**标记**

* `VIEW_TAGS` -用户可以对其标记容器执行所有操作（查看、创建、编辑、删除）。

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` -用户可以对其Audience Lab测试组执行所有操作（查看、创建、编辑、删除）。

**区段**

* `CREATE_ALL_SEGMENTS` -用户可以创建区段。
* `DELETE_ALL_SEGMENTS` -用户可以删除在其公司帐户中设置的所有区段。
* `MAP_ALL_TO_DESTINATIONS` -用户可以将属于其公司的任何区段映射到目标。
* `EDIT_ALL_SEGMENTS` -用户可以编辑在其公司帐户中设置的所有区段。
* `MAP_ALL_SEGMENTS_TO_MODELS` -用户可以选择区段作为模型的基线。
* `VIEW_ALL_SEGMENTS` -用户可以查看在其公司帐户中设置的所有细分。

**信号**

* `VIEW_ALL_SIGNALS` -用户可以查看在数据浏览器中捕获的 [所有信号](/help/using/features/data-explorer/data-explorer-overview.md)。

## 用例 {#use-cases}

### 监视用户访问 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 可以帮助您监控用户登录状态，从而清楚地了解谁可以访问您的Audience Manager实例。

根据您的业务要求，您可以根据需要启用和禁用用户帐户。

![监视用户访问](assets/monitor-user-access.png)

### 确保对敏感数据源的访问保护 {#protect-sensitive-data-sources}

您可以为 [!UICONTROL Role-Based Access Control] 每个用户组配置特征、区段和目标级别。

此功能可帮助您管理用户查看、创建、读取、写入和编辑特定数据集的方式，甚至限制用户访问不应对其可用的数据集。

![访问保护](assets/access-protection.png)
