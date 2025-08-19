---
description: 通过管理菜单下的选项，您可以创建Audience Manager用户并将其分配给组。 您还可以查看限制（特征、区段、目标和模型）。
keywords: RBAC；RBAC；基于角色；基于角色；基于角色的访问控制
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 管理
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] （RBAC控件） {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 用户帐户管理正在移至[Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)。 要开始用户迁移，我们要求所有Audience Manager客户立即采取本文中所述的必要措施：[Audience Manager用户迁移到Admin Console](admin-console-migration.md)。
> 
> 在迁移完所有客户之后，本文档的用户管理部分将消失。

>[!IMPORTANT]
>
> 在使用[!DNL RBAC]之前，此功能必须由Adobe为您的组织启用。 请联系您的帐户团队以请求[!DNL RBAC]激活，或联系客户关怀团队。


通过[!UICONTROL Administration]菜单下的选项，可创建Audience Manager用户并将其分配给组。 您还可以查看限制（特征、区段、目标和模型）。

使用[!DNL Audience Manager]的企业客户需要有一个数据管理平台来管理其所有数据，但必须能够控制不同数据元素对特定业务部门的可见性。 您可以使用组权限(也称为[!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]))完成此操作。

[!DNL Audience Manager]使用组分配权限。 未在用户级别分配权限。 组权限与对象（[!UICONTROL traits]、区段等）以及您可以对这些对象执行的操作（编辑、查看等）相关联。 这些控件也可以通过Audience Manager REST API使用。 请参阅[用户管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md)、[群组管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)和[权限管理](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API方法。

## 创建用户 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 用户帐户管理正在移至[Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)。 要开始用户迁移，我们要求所有Audience Manager客户立即采取本文中所述的必要措施：[Audience Manager用户迁移到Admin Console](admin-console-migration.md)。
> 
> 在迁移完所有客户之后，本文档的用户管理部分将消失。
> 
>在[!DNL Audience Manager]中创建用户，并指定用户详细信息、登录状态以及将用户分配给组。

1. 单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Users]**。
1. 单击![](assets/icon_add.png)以显示[!UICONTROL Create New User]页。
1. 在&#x200B;**[!UICONTROL User Details]**&#x200B;下，填写以下字段：
   * **[!UICONTROL Username]：**&#x200B;为Audience Manager指定一个唯一的用户名。
   * **[!UICONTROL First Name]：**&#x200B;指定用户的名字。
   * **[!UICONTROL Last Name]：**&#x200B;指定用户的姓氏。
   * **[!UICONTROL Email Address]：**&#x200B;指定用户的电子邮件地址。 [!DNL Audience Manager]不向用户发送定期通知。 [!DNL Audience Manager]管理员有权访问用户的电子邮件地址，并且可以根据需要手动向用户发送电子邮件。 例如，如果用户忘记了密码，则使用此字段中指定的电子邮件地址发送临时密码以及重置密码的说明。
   * **[!UICONTROL Phone Number]：**&#x200B;指定用户的电话号码。
   * **[!UICONTROL Is Admin]：**&#x200B;指定此用户是否为[!DNL Audience Manager]管理员。 管理员用户可以管理用户（创建、编辑等）和组（创建、分配权限等）。 非管理员用户只能控制自己的用户配置文件，包括编辑其电子邮件地址和重置其密码。 有关详细信息，请参阅[编辑帐户设置](../../features/administration/edit-account-settings.md)。
1. 在&#x200B;**[!UICONTROL Login]**&#x200B;下，选择所需的状态：
   * **[!UICONTROL Active]：**&#x200B;活动用户可以访问[!DNL Audience Manager]并拥有组成员资格授予的权限。
   * **[!UICONTROL Deactivated]：**&#x200B;已停用用户无法访问[!DNL Audience Manager]，不具有任何权限。 如果您停用用户，则其用户信息将保留在[!DNL Audience Manager]中，如有必要，您可以简单地重新激活这些用户。 如果移除用户，则必须在将来再次使用[!DNL Audience Manager]时重新创建用户。
   * **[!UICONTROL Expired]：**&#x200B;用户的密码超过90天。
   * **[!UICONTROL Pending]：**&#x200B;用户具有临时密码（在密码重置后或作为全新帐户），并且用户尚未设置永久密码。
   * **[!UICONTROL Locked Out]：** 5次错误的登录尝试将会锁定用户。
1. 在&#x200B;**[!UICONTROL Assigned Groups]**&#x200B;下，从下拉列表中选择要为其分配此用户的所需组。
有关组和权限的详细信息，请参阅[创建组](../../features/administration/administration-overview.md#create-group)。
1. 单击 **[!UICONTROL Save]**。

## 创建[!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 用户帐户管理正在移至[Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)。 要开始用户迁移，我们建议所有Audience Manager客户立即采取本文中所述的必要措施：[Audience Manager用户迁移到Admin Console](admin-console-migration.md)。
> 
> 在迁移完所有客户后，此部分将消失。

*组*&#x200B;是共享对[!UICONTROL destination]、[!UICONTROL segment]和[!UICONTROL trait]对象的访问权限的用户集合。 您可以将组限制为仅单个对象，也可以授予他们对不同对象组合的广泛访问权限。

<!-- t_create_groups.xml -->

要创建组，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Administration]** > **[!UICONTROL Groups]**。
2. 单击![](assets/icon_add.png)以打开[!UICONTROL Group Settings]页面。
3. 在[!UICONTROL Group Details]内：
   * 命名组。
   * 提供简要的组描述。
4. 在[!UICONTROL Group Members]中，单击&#x200B;**[!UICONTROL Add Users]**&#x200B;选项中的用户以将其添加到组。
5. 在[!UICONTROL Group Permissions]中，从[中选择](../../features/traits/trait-details-page.md)特征[、](../../features/segments/segments-purpose.md)区段[或](../../features/destinations/destinations.md)目标&#x200B;**[!UICONTROL Add Object]**。
这将打开选定对象的权限窗口。
6. 选中您希望群组成员拥有的权限对应的复选框。
7. *（可选）*&#x200B;将[通配符权限](../../features/administration/administration-overview.md#wild-card-permissions)分配给组。
8. 单击 **[!UICONTROL Save Group]**。

## 了解[!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 用户帐户管理正在移至[Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)。 要开始用户迁移，我们建议所有Audience Manager客户立即采取本文中所述的必要措施：[Audience Manager用户迁移到Admin Console](admin-console-migration.md)。
> 
> 在迁移完所有客户后，此部分将消失。

使用[!UICONTROL Wild Card Permissions]简化组权限管理。

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions]为群组成员提供对与[!UICONTROL segment]、[!UICONTROL destination]或[!UICONTROL trait]关联的每个数据源的自动访问权限。 相比之下，常规权限只允许您将特定[!UICONTROL data sources]分配给这些对象之一。 此外，当您添加新[!UICONTROL data sources]时，组成员无权访问这些新源。

您必须打开组权限并将这些新[!UICONTROL data sources]分配给组。 [!UICONTROL Wild Card Permissions]允许您避免此手动[!UICONTROL data source]更新过程。 具有[!UICONTROL Wild Card Permissions]的组无需明确授权即可访问新[!UICONTROL data sources]。

![](assets/wild-card.png)

请阅读下文，了解每个[!UICONTROL wildcard permission]的含义：

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` — 用户可以选择[!UICONTROL traits]作为[!UICONTROL models]的基线。
* `EDIT_ALL_TRAITS` — 用户可以编辑在其公司帐户内设置的所有[!UICONTROL traits]。
* `VIEW_ALL_TRAITS` — 用户可以查看在其公司帐户中设置的所有[!UICONTROL traits]。
* `DELETE_ALL_TRAITS` — 用户可以删除在其公司帐户内设置的所有[!UICONTROL traits]。
* `CREATE_ALL_ALGO_TRAITS` — 用户可以创建[!UICONTROL algorithmic traits]。
* `MAP_ALL_TO_SEGMENTS` — 用户可以将属于其公司的任何[!UICONTROL traits]添加到[!UICONTROL segments]。
* `CREATE_ALL_TRAITS` — 用户可以创建[!UICONTROL traits]。

**[!UICONTROL Models]**

* `VIEW_MODELS` — 用户有权查看属于其公司的[!UICONTROL models]。

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` — 用户可以查看属于其公司的所有[!UICONTROL derived signals]。
* `CREATE_DERIVED_SIGNALS` — 用户可以创建[!UICONTROL derived signals]。
* `EDIT_DERIVED_SIGNALS` — 用户可以编辑属于其公司的所有[!UICONTROL derived signals]。
* `DELETE_DERIVED_SIGNALS` — 用户可以删除属于其公司的任何[!UICONTROL derived signals]。

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` — 用户可以编辑在其公司帐户中设置的所有[!UICONTROL destinations]。
* `CREATE_DESTINATIONS` — 用户可以创建[!UICONTROL destinations]。
* `VIEW_ALL_DESTINATIONS` — 用户可以查看在其公司帐户中设置的所有[!UICONTROL destinations]。
* `DELETE_ALL_DESTINATIONS` — 用户可以删除在其公司帐户内设置的所有[!UICONTROL destinations]。

**[!UICONTROL Tags]**

* `VIEW_TAGS` — 用户可以在其[!UICONTROL Tag Containers]上执行所有操作（查看、创建、编辑、删除）。

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` — 用户可以对其[!UICONTROL Audience Lab]测试组执行所有操作（查看、创建、编辑、删除）。

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` — 用户可以创建区段。
* `DELETE_ALL_SEGMENTS` — 用户可以删除在其公司帐户内设置的所有区段。
* `MAP_ALL_TO_DESTINATIONS` — 用户可以将属于其公司的任何区段映射到目标。
* `EDIT_ALL_SEGMENTS` — 用户可以编辑在其公司帐户中设置的所有区段。
* `MAP_ALL_SEGMENTS_TO_MODELS` — 用户可以选择区段作为模型的基线。
* `VIEW_ALL_SEGMENTS` — 用户可以查看在其公司帐户中设置的所有区段。

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` — 用户可以查看[Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md)中捕获的所有信号。

## 用例 {#use-cases}

### 监控用户访问 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control]可以帮助您监视用户登录状态，让您清楚地了解谁可以访问您的Audience Manager实例。

根据您的业务要求，您可以根据需要启用和禁用用户帐户。

![monitor-user-access](assets/monitor-user-access.png)

### 确保对敏感的[!UICONTROL Data Sources]的访问保护 {#protect-sensitive-data-sources}

您可以为每个用户组在[!UICONTROL Role-Based Access Control]、区段和[!UICONTROL trait]级别配置[!UICONTROL destination]。

此功能可帮助您管理用户查看、创建、读取、写入和编辑特定数据集的方式，甚至限制用户访问不应向他们提供的数据集。

![访问保护](assets/access-protection.png)
