---
description: Audience Manager用户管理即将转移到Adobe Admin Console。 本文说明准备用户迁移需要做哪些工作，以及迁移完成后将发生哪些变化。
keywords: RBAC；RBAC；基于角色；基于角色；基于角色的访问控制
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager用户迁移到Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Audience Manager]用户迁移到[!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager]用户帐户管理将转移到[Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)，以便在您的Adobe解决方案中实现更精简的体验。

使用[!DNL Admin Console]的好处包括：

| 好处 | 描述 |
|---|---|
| 跨解决方案的单点登录 | [!DNL Audience Manager]用户可以使用其[!DNL Experience Cloud]或[!DNL Adobe ID]登录到[!DNL Enterprise ID]和所有其他解决方案。 此登录允许跨[!DNL Experience Cloud]访问集成的解决方案和核心服务。 迁移后，尝试通过旧版登录(`bank.demdex.com`)进行登录的用户将被重定向到`experiencecloud.adobe.com`。 |
| 管理用户和组 | 迁移完成后，[!DNL Audience Manager]管理员将专门管理[[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)中的用户和组。 |
| 管理产品和服务 | 在[[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)中，管理员可以： <ul><li>创建、更新和移除用户</li><li>授予对解决方案和服务的访问权限</li></ul> |

为方便用户迁移，我们要求所有[!DNL Audience Manager]管理员按照本文中介绍的步骤，尽快开始将其用户帐户迁移到[Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)。

## 用户需要做什么 {#what-to-do-users}

作为Audience Manager用户，您只需联系[!DNL Audience Manager]管理员，要求他们在[!DNL Admin Console]中为您创建新的用户帐户。

## 管理员需要做什么 {#what-to-do-admins}

Audience Manager管理员应按照以下步骤将用户迁移到[!DNL Admin Console]。

1. 转到[https://adminconsole.adobe.com](https://adminconsole.adobe.com)并使用您的Adobe ID或Enterprise ID登录。 如果您无权访问[!DNL Admin Console]，请联系客户关怀团队或您的Adobe顾问。
2. 有关如何创建和管理用户帐户的详细说明，请查看[!DNL Adobe Admin Console] [帮助指南](https://helpx.adobe.com/cn/enterprise/admin-guide.html/enterprise/using/users.ug.html)。
3. 为所有现有Audience Manager用户创建新用户帐户。
4. 通知您的用户新创建的用户帐户。 用户迁移到[!DNL Admin Console]后，他们应停止使用旧版登录。

## 用户迁移注意事项 {#considerations}

对于Audience Manager用户迁移，用户和管理员都应牢记以下注意事项：

* 在Admin Console中创建新的用户帐户后，其旧用户帐户中的现有权限仍将适用。
* 用户权限的更新仍从[!DNL Audience Manager]进行管理。 [!DNL Admin Console]仅涵盖用户和组管理。
* 管理员不需要禁用旧版用户帐户。 旧用户帐户将自动合并到已迁移的用户帐户中。
