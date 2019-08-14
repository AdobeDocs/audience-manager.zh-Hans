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
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# 管理(CLUAC控件) {#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] 通过菜单中的选项，您可以创建Audience Manager用户并将其分配给组。您还可以查看限制(特征、区段、目标和模型)。

对于所有数据，企业客户都 [!DNL Audience Manager] 需要一个数据管理平台，但必须能够控制不同数据元素对特定业务单位的可见性。您可以使用组权限来完成此操作，也称为 [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC])。

[!DNL Audience Manager] 使用组分配权限。权限不是在用户级别分配的。组权限绑定到对象(特征、区段等)以及可对这些对象执行的操作(编辑、视图等)。这些控件也可通过Audience Manager REST API获得。请参阅 [用户管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、 [组管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)和 [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## Create Users {#create-users}

<!-- t_create_users.xml -->

在中创建用户 [!DNL Audience Manager] 并指定用户详细信息、登录状态并将用户分配给用户组。

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. 单击 ![](assets/icon_add.png) 以显示 [!UICONTROL Create New User] 页面。
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **用户名：** 为Audience Manager指定唯一用户名。
   * **名字：** 指定用户的名字。
   * **姓氏：** 指定用户的姓氏。
   * **电子邮件地址：** 指定用户的电子邮件地址。[!DNL Audience Manager] 不会向用户发送定期通知。[!DNL Audience Manager] 管理员可以访问用户的电子邮件地址，并可以根据需要手动通过电子邮件发送用户。例如，如果用户忘记密码，则在此字段中指定的电子邮件地址用于发送临时口令和说明重置口令。
   * **电话号码：** 指定用户的电话号码。
   * **管理员：** 指定此用户是否为 [!DNL Audience Manager] 管理员。管理员用户可以管理用户(创建、编辑等)和组(创建、分配权限等)。非管理员用户只能控制自己的用户配置文件，包括编辑其电子邮件地址和重置自己的口令。有关详细信息，请参阅 [编辑帐户设置](../../features/administration/edit-account-settings.md)。
1. 根据 **[!UICONTROL Login]**&#x200B;需要选择所需状态：
   * **活动：** 活动用户可以访问 [!DNL Audience Manager] 并具有按组成员关系授予的权限。
   * **取消激活：** 禁用的用户无法访问 [!DNL Audience Manager] ，并且没有任何权限。如果取消激活用户，则用户信息仍保留在其中 [!DNL Audience Manager] ，如有必要，您可以简单地重新激活这些用户。如果删除用户，则必须在以后重新创建用户时才能 [!DNL Audience Manager] 再次使用。
   * **已过期：** 用户的口令超过90天。
   * **待定：** 用户有一个临时密码，无论密码重置后还是作为新帐户，他们还没有设置永久口令。
   * **已锁定：** 个错误的登录尝试将锁定用户。
1. 在下 **[!UICONTROL Assigned Groups]**拉列表中，选择要为其分配此用户的所需用户组。
有关组和权限的详细信息，请参阅 [创建用户组](../../features/administration/administration-overview.md#create-group)。
1. 单击 **[!UICONTROL Save]**.

## 创建群组 {#create-group}

*组* 是共享访问目标、区段和特征对象权限的用户集合。您可以将组限制为仅限单个对象，也可以使其广泛访问不同对象组合。

<!-- t_create_groups.xml -->

要创建用户组，请执行以下操作：

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. 单击 ![](assets/icon_add.png) 以打开 [!UICONTROL Group Settings] 页面。
1. 在 [!UICONTROL Group Details]:
   * 命名用户组。
   * 提供简短的用户组描述。
1. 在中 [!UICONTROL Group Members]，单击用户 **[!UICONTROL Add Users]** 以将其添加到用户组。
1. 在中 [!UICONTROL Group Permissions]，选择 [特征](../../features/traits/trait-details-page.md)、 [区段](../../features/segments/segments-purpose.md)或 [目标](../../features/destinations/destinations.md) 。
**[!UICONTROL Add Object]**&#x200B;这将打开选定对象的权限窗口。
1. 选中您希望用户组成员具有的权限对应的复选框。
1. *(可选)* 将 [通配符权限分配](../../features/administration/administration-overview.md#wild-card-permissions) 给用户组。
1. 单击 **[!UICONTROL Save Group]**.

## 了解通配符权限 {#wild-card-permissions}

简化组权限管理 [!UICONTROL Wild Card Permissions]。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 使组成员能够自动访问与某个区段、目标或特征相关联的每个数据源。通过比较，常规权限仅允许您将特定数据源分配给其中一个对象。而且，添加新数据源时，组成员无法访问这些新源。

您必须打开用户组权限，然后将这些新数据源分配给用户组。[!UICONTROL Wild Card Permissions] 可避免手动数据源更新过程。无需 [!UICONTROL Wild Card Permissions] 显式授权即可访问新数据源。

![](assets/wild-card.png)

阅读下面的内容以了解每个通配符权限的含义：

**特性**

* `MAP_ALL_TRAITS_TO_MODELS` - 用户可以选择属性作为模型的基线。
* `EDIT_ALL_TRAITS` - 用户可以编辑公司帐户中设置的所有特征。
* `VIEW_ALL_TRAITS` - 用户可以查看在其公司帐户中设置的所有特征。
* `DELETE_ALL_TRAITS` - 用户可以删除公司帐户中设置的所有特征。
* `CREATE_ALL_ALGO_TRAITS` - 用户可以创建算法特征。
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
* `MAP_ALL_SEGMENTS_TO_MODELS` - 用户可以选择区段作为模型的基准。
* `VIEW_ALL_SEGMENTS` - 用户可以查看在其公司帐户中设置的所有区段。

**信号**

* `VIEW_ALL_SIGNALS` - 用户可以查看 [在数据浏览器](/help/using/features/data-explorer/data-explorer-overview.md)中捕获的所有信号。