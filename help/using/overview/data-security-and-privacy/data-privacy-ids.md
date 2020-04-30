---
description: 此文档涵盖可在数据隐私请求中使用的受众管理器ID类型。
seo-description: 此文档涵盖可在数据隐私请求中使用的受众管理器ID类型。
seo-title: 受众管理器标识符(ID)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: 受众管理器标识符(ID)
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 受众管理器标识符(ID) {#aam-ids}

在向Adobe [受众管理](data-privacy-requests.md) 器提交数据隐私请求时，您必须包括下面列出的一个标识符(ID)。 您可以在我们的受众管理器ID索引中找 [到有关ID格式的更多信息](../../reference/ids-in-aam.md)。

## Adobe受众管理器唯一用户ID

* **用户 ID**: `aam_uuid`
* **定义**: Adobe受众管理器唯一用户ID
* **命名空间ID**: 0

**JSON 示例**:

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
>You can also use the [!DNL CORE] namespace.

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

* **用户 ID**: `mid`
* **定义**: [!DNL Adobe Experience Cloud ID]，以前称为 [!DNL Visitor ID] 或 [!DNL Marketing Cloud ID]
* **命名空间ID**: 4

>[!NOTE]
>
>You can also use the [!DNL ECID] namespace. 请参阅第二个 [!DNL JSON] 示例。

**JSON 示例**:

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

## Customer ID

**用户 ID**: `cid`

**定义**: 客户ID，如您为匿名网站访客设置的Cookie，或 [!DNL CRM] 来自脱机系统的ID或散列用户名。

**命名空间ID**: 客户特定。 请从您的受众管理器实例中找到它。

**JSON 示例**:

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

## 移动广告ID

**用户 ID**: `d_cid`

**定义**: 移动广告ID。

**命名空间 ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

有关更 [多详细信息](../../features/global-data-sources.md) ，请参阅全局数据源。

>[!IMPORTANT]
>
> 如果您使用的是移 [!DNL SDK]动设备，则还应发送Experience Cloud ID()`MID`和移动广告ID，以获得完整的访问和删除响应。

**JSON 示例**:

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

**用户 ID**: `d_cid_ic`

**定义**: 数据源的集成代码。 在请求时，可以使用它代替数据源ID /命名空间 [!DNL API] ID [!DNL Adobe Experience Cloud Privacy Core Service]。

**命名空间ID**: 不适用

**JSON 示例**:

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
