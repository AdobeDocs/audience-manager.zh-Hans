---
description: Audience Manager使用者管理即將移至Adobe Admin Console。 本文說明準備使用者移轉所需的工作，以及移轉完成後將發生的變化。
keywords: rbac；RBAC；角色型；角色型；角色型存取控制
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager使用者移轉至Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 3%

---

# [!DNL Audience Manager] 使用者移轉至 [!DNL Admin Console] {#user-migration}

## 概述 {#overview}

[!DNL Audience Manager] 使用者帳戶管理即將移至 [Adobe Admin Console](https://helpx.adobe.com/cn/enterprise/using/admin-console.html)，以便在您的Adobe解決方案中提供更精簡的體驗。

使用 [!DNL Admin Console] 包括以下好处：

| 好处 | 描述 |
|---|---|
| 单点登录 跨解決方案 | [!DNL Audience Manager] 使用者可以登入 [!DNL Experience Cloud] 以及所有其他使用其 [!DNL Adobe ID] 或 [!DNL Enterprise ID]. 此登入可讓您存取整合式解決方案和核心服務，涵蓋以下所有領域： [!DNL Experience Cloud]. 移轉後，使用者嘗試透過舊版登入頁面(`bank.demdex.com`)將重新導向至 `experiencecloud.adobe.com`. |
| 管理使用者和群組 | 移轉一旦完成， [!DNL Audience Manager] 管理員將專門管理下列位置中的使用者和群組： [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| 管理產品和服務 | 從 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)，管理員可以： <ul><li>创建、更新和删除用户</li><li>授予对解决方案和服务的访问权限</li></ul> |

为便于用户迁移，我们要求所有 [!DNL Audience Manager] 管理员开始按照本文所述的步骤，尽快将其用户帐户迁移到 [ Adobe Admin Console ](https://helpx.adobe.com/cn/enterprise/using/admin-console.html) 。

## 用户需要执行的操作 {#what-to-do-users}

身為Audience Manager使用者，您只需要聯絡 [!DNL Audience Manager] 管理員，並要求他們為您建立新的使用者帳戶 [!DNL Admin Console].

## 管理員需要做什麼 {#what-to-do-admins}

Audience Manager管理員應遵循以下步驟將使用者移轉至 [!DNL Admin Console].

1. 前往 [https://adminconsole.adobe.com](https://adminconsole.adobe.com) 並使用您的Adobe ID或Enterprise ID登入。 如果您無權存取 [!DNL Admin Console]，請聯絡客戶服務或您的Adobe顧問。
2. 檢查 [!DNL Adobe Admin Console] [說明指南](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) 以取得有關如何建立和管理使用者帳戶的詳細說明。
3. 為所有現有的Audience Manager使用者建立新的使用者帳戶。
4. 通知用户新创建的用户帐户。 一旦用户迁移到 [!DNL Admin Console] ，他们就应该停止使用旧版登录。

## 用户迁移注意事项 {#considerations}

用户和管理员应牢记以下有关 Audience Manager 用户迁移的注意事项：

* 在 Admin Console 中创建新的用户帐户后，他们的旧用户帐户的现有权限仍将适用。
* 使用者許可權的更新仍會從管理 [!DNL Audience Manager]. 此 [!DNL Admin Console] 僅涵蓋使用者和群組管理。
* 管理員不需要停用舊版使用者帳戶。 舊的使用者帳戶會自動合併到已移轉的使用者帳戶中。
