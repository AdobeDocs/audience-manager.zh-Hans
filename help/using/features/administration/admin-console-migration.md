---
description: Audience Manager用户管理正在迁移至Adobe Admin Console。 本文介绍了为用户迁移做准备所需执行的操作，以及迁移完成后将更改的操作。
keywords: RBAC；基于角色；基于角色；基于角色的访问控制
seo-description: Audience Manager用户管理正在迁移至Adobe Admin Console。 本文介绍了为用户迁移做准备所需执行的操作，以及迁移完成后将更改的操作。
seo-title: Audience Manager用户迁移到Admin Console
solution: Audience Manager
title: Audience Manager用户迁移到Admin Console
feature: 管理
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# [!DNL Audience Manager] 用户迁移到  [!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager] 用户帐户管理正在迁移到 [Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)，以便在您的Adobe解决方案中更轻松地体验。

使用[!DNL Admin Console]的好处包括：

| 好处 | 描述 |
|---|---|
| 单点登录 跨解决方案 | [!DNL Audience Manager] 用户可以使用 [!DNL Experience Cloud] 其或登录到和所有其他解 [!DNL Adobe ID] 决方 [!DNL Enterprise ID]案。此登录允许跨[!DNL Experience Cloud]访问集成的解决方案和核心服务。 迁移后，尝试通过旧版登录(`bank.demdex.com`)进行登录的用户将被重定向到`experiencecloud.adobe.com`。 |
| 管理用户和群组 | 迁移完成后，[!DNL Audience Manager]管理员将专门在[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)中管理用户和组。 |
| 管理产品和服务 | 从[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)中，管理员可以： <ul><li>创建、更新和删除用户</li><li>授予对解决方案和服务的访问权限</li></ul> |

为了方便用户迁移，我们要求所有[!DNL Audience Manager]管理员按照本文中描述的步骤，尽快将其用户帐户迁移到[Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。

## {#what-to-do-users}用户需要执行的操作

作为Audience Manager用户，您只需联系[!DNL Audience Manager]管理员，要求他们在[!DNL Admin Console]中为您创建新的用户帐户。

## {#what-to-do-admins}管理员需要执行的操作

Audience Manager管理员应按照以下步骤将用户迁移到[!DNL Admin Console]。

1. 转到[https://adminconsole.adobe.com](https://adminconsole.adobe.com)，然后使用您的Adobe ID或Enterprise ID登录。 如果您无权访问[!DNL Admin Console]，请联系客户关怀团队或您的Adobe顾问。
2. 请查看[!DNL Adobe Admin Console] [帮助指南](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html)，以了解有关如何创建和管理用户帐户的详细说明。
3. 为所有现有Audience Manager用户创建新用户帐户。
4. 将新创建的用户帐户通知您的用户。 将用户迁移到[!DNL Admin Console]后，他们应停止使用旧版登录方式。

## 用户迁移注意事项 {#considerations}

对于Audience Manager用户迁移，用户和管理员应牢记以下注意事项：

* 在Admin Console中创建新用户帐户后，其旧版用户帐户的现有权限仍将适用。
* 用户权限的更新仍将通过[!DNL Audience Manager]进行管理。 [!DNL Admin Console]仅涵盖用户和组管理。
* 管理员无需禁用旧版用户帐户。 旧用户帐户将自动合并到迁移的用户帐户中。
