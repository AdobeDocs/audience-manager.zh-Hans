---
description: 通过“管理”菜单下的选项，您可以创建Audience Manager用户并将其分配给组。您还可以查看限制(特征、区段、目标和模型)。
keywords: rbac；CLUAC；基于角色；基于角色；基于角色的访问控制
seo-description: 通过“管理”菜单下的选项，您可以创建Audience Manager用户并将其分配给组。您还可以查看限制(特征、区段、目标和模型)。
seo-title: 管理
solution: Audience Manager
title: 管理
topic: DIL API
uuid: 498e0316-cf1 b-43e9-88ba-338ee0 daf221
translation-type: tm+mt
source-git-commit: 9801bf6a1a4c2c2e7cc2aa8ab32cb81094368554

---


# Administration (RBAC Controls) {#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] 通过菜单中的选项，您可以创建Audience Manager用户并将其分配给组。您还可以查看限制(特征、区段、目标和模型)。

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] 使用组分配权限。权限不是在用户级别分配的。组权限绑定到对象(特征、区段等)以及可对这些对象执行的操作(编辑、视图等)。这些控件也可通过Audience Manager REST API获得。See [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), and [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API methods.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **用户名：** 为Audience Manager指定唯一用户名。
   * **名字：** 指定用户的名字。
   * **姓氏：** 指定用户的姓氏。
   * **电子邮件地址：** 指定用户的电子邮件地址。[!DNL Audience Manager] 不会向用户发送定期通知。[!DNL Audience Manager] 管理员可以访问用户的电子邮件地址，并可以根据需要手动通过电子邮件发送用户。例如，如果用户忘记密码，则在此字段中指定的电子邮件地址用于发送临时口令和说明重置口令。
   * **电话号码：** 指定用户的电话号码。
   * **管理员：** 指定此用户是否为 [!DNL Audience Manager] 管理员。管理员用户可以管理用户(创建、编辑等)和组(创建、分配权限等)。非管理员用户只能控制自己的用户配置文件，包括编辑其电子邮件地址和重置自己的口令。For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **活动：** 活动用户可以访问 [!DNL Audience Manager] 并具有按组成员关系授予的权限。
   * **取消激活：** 禁用的用户无法访问 [!DNL Audience Manager] ，并且没有任何权限。If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **已过期：** 用户的口令超过90天。
   * **待定：** 用户有一个临时密码，无论密码重置后还是作为新帐户，他们还没有设置永久口令。
   * **已锁定：** 个错误的登录尝试将锁定用户。
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#create-group).
1. 单击 **[!UICONTROL Save]**.

## 创建群组 {#create-group}

*组* 是共享访问目标、区段和特征对象权限的用户集合。您可以将组限制为仅限单个对象，也可以使其广泛访问不同对象组合。

<!-- t_create_groups.xml -->

要创建用户组，请执行以下操作：

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1. 在 [!UICONTROL Group Details]:
   * 命名用户组。
   * 提供简短的用户组描述。
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
这将打开选定对象的权限窗口。
1. 选中您希望用户组成员具有的权限对应的复选框。
1. *(可选)* 将 [通配符权限分配](../../features/administration/administration-overview.md#wild-card-permissions) 给用户组。
1. 单击 **[!UICONTROL Save Group]**.

## Understanding Wild Card Permissions {#wild-card-permissions}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 使组成员能够自动访问与某个区段、目标或特征相关联的每个数据源。通过比较，常规权限仅允许您将特定数据源分配给其中一个对象。而且，添加新数据源时，组成员无法访问这些新源。

您必须打开用户组权限，然后将这些新数据源分配给用户组。[!UICONTROL Wild Card Permissions] 可避免手动数据源更新过程。Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

阅读下面的内容以了解每个通配符权限的含义：

**特性**

* `MAP_ALL_TRAITS_TO_MODELS` - 需要澄清？
* `EDIT_ALL_TRAITS` - 用户可以编辑属于其公司的所有特征(PID)
* `VIEW_ALL_TRAITS` - 用户可以查看属于其公司的所有特征(PID)
* `DELETE_ALL_TRAITS` - 用户可以删除属于其公司(PID)的所有特征。
* `CREATE_ALL_ALGO_TRAITS` - 需要阐明
* `MAP_ALL_TO_SEGMENTS` - 用户可以将属于其公司的任何特征添加到区段中。
* `CREATE_ALL_TRAITS` - 用户可以创建特征。

**报表**

* `PTRREPORTS` - 此通配符权限引用过时的功能，不久将从Audience Manager UI中删除。

**型号**

* `VIEW_MODELS` - 用户有权查看属于其公司的模型。

**派生信号**

* `VIEW_DERIVED_SIGNALS` - 用户可以查看属于其公司的所有派生信号。
* `CREATE_DERIVED_SIGNALS` - 用户可以创建派生信号。
* `EDIT_DERIVED_SIGNALS` - 用户可以编辑属于其公司的所有派生信号。
* `DELETE_DERIVED_SIGNALS` - 用户可以删除属于其公司的任何派生信号。

**目标**

* `EDIT_ALL_DESTINATIONS` - 用户可以编辑其公司帐户中设置的所有目标。
* `CREATE_DESTINATIONS` - 用户可以创建目标。
* `VIEW_ALL_DESTINATIONS` - 用户可以查看在其公司帐户中设置的所有目标。
* `DELETE_ALL_DESTINATIONS` - 用户可以删除在其公司帐户中设置的所有目标。

**标记**

* `VIEW_TAGS` - 用户可以在其标记容器上执行所有(查看、创建、编辑、删除)操作。

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - 用户可以在其Audience Lab测试组上执行所有(查看、创建、编辑、删除)操作。

**区段**

* `CREATE_ALL_SEGMENTS` - 用户可以创建区段。
* `DELETE_ALL_SEGMENTS` - 用户可以删除在其公司帐户中设置的所有区段。
* `MAP_ALL_TO_DESTINATIONS` - 用户可以将属于其公司的任何区段映射到目标。
* `EDIT_ALL_SEGMENTS` - 用户可以编辑在其公司帐户内设置的所有区段。
* `MAP_ALL_SEGMENTS_TO_MODELS` - 需要澄清？
* `VIEW_ALL_SEGMENTS` - 用户可以查看在其公司帐户中设置的所有区段。

**信号**

* `VIEW_ALL_SIGNALS` - 用户可以查看 [在数据浏览器](/help/using/features/data-explorer/data-explorer-overview.md)中捕获的所有信号。