---
description: 本文档介绍可在数据隐私请求中使用的 Audience Manager ID 的类型。
seo-description: 本文档介绍可在数据隐私请求中使用的 Audience Manager ID 的类型。
seo-title: Audience Manager 标识符 (ID)
solution: Audience Manager
keywords: GDPR UI、GDPR API、CCPA、隐私、AAM ID
title: Audience Manager 标识符 (ID)
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 95%

---

# Audience Manager 标识符 (ID) {#aam-ids}

向 Adobe Audience Manager 提交[数据隐私请求](data-privacy-requests.md)时，您必须包括下面列出的标识符 (ID) 之一。您可以在我们的 [Audience Manager ID 索引](../../reference/ids-in-aam.md)中找到有关 ID 格式的更多信息。

## Adobe Audience Manager 独特用户 ID

* **用户 ID**：`aam_uuid`
* **定义**：Adobe Audience Manager 独特用户 ID
* **命名空间 ID**：0

**JSON 示例**：

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>您也可以使用 [!DNL CORE] 命名空间。

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **用户 ID**：`mid`
* **定义**：[!DNL Adobe Experience Cloud ID]，以前称为 [!DNL Visitor ID] 或 [!DNL Marketing Cloud ID]
* **命名空间 ID**：4

>[!NOTE]
>
>您也可以使用 [!DNL ECID] 命名空间。请参阅第二个 [!DNL JSON] 示例。

**JSON 示例**：

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## 客户 ID

**用户 ID**：`cid`

**定义**：客户 ID，例如您为匿名网站访客设置的 Cookie，或者来自离线系统的 [!DNL CRM] ID 或经过哈希处理的用户名。

**命名空间 ID**：特定于客户。请从您的 Audience Manager 实例中找到该 ID。

**JSON 示例**：

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## 移动设备广告 ID

**用户 ID**：`d_cid`

**定义**：移动设备广告 ID。

**命名空间 ID**：

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

有关更多详细信息，请参阅[全局数据源](../../features/global-data-sources.md)。

>[!IMPORTANT]
>
> 如果您使用的是 Mobile [!DNL SDK]，则还应该将 Experience Cloud ID (`MID`) 与移动设备广告 ID 一起发送，以获取完整的访问和删除响应。

**JSON 示例**：

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## 集成代码

**用户 ID**：`d_cid_ic`

**定义**：数据源的集成代码。可以在对 [!DNL Adobe Experience Cloud Privacy Core Service] 的 [!DNL API] 请求中使用它来代替数据源 ID/命名空间 ID。

**命名空间 ID**：不适用

**JSON 示例**：

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
