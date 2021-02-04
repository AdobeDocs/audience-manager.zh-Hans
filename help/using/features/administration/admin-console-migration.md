---
description: Audience Manager用户管理正在向Adobe Admin Console转移。 本文说明了为用户迁移做准备时需要做什么，以及迁移完成后将发生什么变化。
keywords: rbac;RBAC；基于角色；基于角色；基于角色的访问控制
seo-description: Audience Manager用户管理正在向Adobe Admin Console转移。 本文说明了为用户迁移做准备时需要做什么，以及迁移完成后将发生什么变化。
seo-title: Audience Manager用户迁移到Admin Console
solution: Audience Manager
title: Audience Manager用户迁移到Admin Console
feature: Administration
translation-type: tm+mt
source-git-commit: e4a9ae06a1283870613d2751b171fc443b8701d8
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 3%

---


# [!DNL Audience Manager] 用户迁移到  [!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager] 用户帐户管理正在迁 [移到Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)，以便在Adobe解决方案中获得更流畅的体验。

使用[!DNL Admin Console]的好处包括：

| 好处 | 描述 |
|---|---|
| 单点登录 跨解决方案 | [!DNL Audience Manager] 用户可以使用 [!DNL Experience Cloud] 或登录到和所有其他解 [!DNL Adobe ID] 决方 [!DNL Enterprise ID]案。此登录支持跨[!DNL Experience Cloud]访问集成解决方案和核心服务。 迁移后，尝试通过旧登录(`bank.demdex.com`)登录的用户将被重定向到`experiencecloud.adobe.com`。 |
| 管理用户和用户组 | 迁移完成后，[!DNL Audience Manager]管理员将只管理[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)中的用户和组。 |
| 管理产品和服务 | 在[[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/)中，管理员可以： <ul><li>创建、更新和删除用户</li><li>授予对解决方案和服务的访问权限</li><li>授予用户权限</li></ul> |

为便于用户迁移，我们要求所有[!DNL Audience Manager]管理员按照本文所述的步骤，尽快开始将其用户帐户迁移到[Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)。

## 用户需要做什么{#what-to-do-users}

作为Audience Manager用户，您只需与[!DNL Audience Manager]管理员联系并要求他们在[!DNL Admin Console]中为您创建新的用户帐户。

## 管理员需要做什么{#what-to-do-admins}

Audience Manager管理员应按照以下步骤将用户迁移到[!DNL Admin Console]。

1. 转至[https://adminconsole.adobe.com](https://adminconsole.adobe.com)并使用您的Adobe ID或Enterprise ID登录。 如果您无权访问[!DNL Admin Console]，请与客户服务或Adobe顾问联系。
2. 有关如何创建和管理用户帐户的详细说明，请查看[!DNL Adobe Admin Console][帮助指南](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html)。
3. 为所有现有Audience Manager用户创建新用户帐户。
4. 通知用户新创建的用户帐户。 将用户迁移到[!DNL Admin Console]后，他们应停止使用旧版登录。

## 用户迁移注意事项{#considerations}

用户和管理员应牢记Audience Manager用户迁移的以下注意事项：

* 以Admin Console创建新用户帐户后，其旧版用户帐户的现有权限将自动结转。 管理员无需在[!DNL Admin Console]中分配新权限。
* 管理员无需禁用旧版用户帐户。 旧用户帐户将自动合并到迁移的用户帐户中。
* 对用户权限的更新仍将从[!DNL Audience Manager]进行管理。 [!DNL Admin Console]仅涵盖用户和组管理。