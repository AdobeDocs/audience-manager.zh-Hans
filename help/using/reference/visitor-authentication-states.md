---
description: Audience Manager中的访客身份验证状态确定新特征信息是写入访客的已验证用户档案还是写入设备用户档案（从中收集数据）。 Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: Audience Manager中的访客身份验证状态确定新特征信息是写入访客的已验证用户档案还是写入设备用户档案（从中收集数据）。 Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT。
seo-title: Audience Manager 中的访客身份验证状态
solution: Audience Manager
title: Audience Manager 中的访客身份验证状态
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Audience Manager 中的访客身份验证状态{#visitor-authentication-states-in-audience-manager}

Audience Manager中的访客身份验证状态确定新特征信息是写入访客的已验证用户档案还是写入设备用户档案（从中收集数据）。 Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT。

从ID [!DNL Experience Cloud] 服务v1.5+开始，该方 `setCustomerID` 法包括可选 `AuthState` 对象。 `AuthState` 根据访客的身份验 [证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。 [!DNL Audience Manager] 根据调用中传递的身份验证状态和用于分段的用户档案合并规 [则，以不同方式](../features/profile-merge-rules/merge-rules-dashboard.md) 处理已实现的特征。

## 身份验证状态：未知 {#auth-status-unknown}

| 请求值 | **从已验证** 的用户档案读取信息 | **将新特征** 写入已验证的用户档案 |
---------|----------|---------
| 0 | <ul><li>是，如果已验证选项合并规则=“上次已验证用户档案”。</li><li>否，如果已验证选项合并规则=“当前已验证用户档案”或“无已验证用户档案”。</li></ul> | 否，特征数据将添加到设备用户档案。 |


示例调用（与身份验证状态对应的请求值会突出显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 身份验证状态：已验证 {#auth-status-authenticated}

| 请求值 | **从已验证** 的用户档案读取信息 | **将新特征** 写入已验证的用户档案 |
---------|----------|---------
| 1 | <ul><li>是，如果已验证选项合并规则=“当前已验证用户档案”或“上次已验证用户档案”。</li><li>否，如果已验证选项合并规则=“无已验证用户档案”。</li></ul> | 是，特征数据将添加到已验证的用户档案。 |

示例调用（与身份验证状态对应的请求值会突出显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 身份验证状态：LOGGED_OUT {#auth-status-logged-out}

| 请求值 | **从已验证** 的用户档案读取信息 | **将新特征** 写入已验证的用户档案 |
---------|----------|---------
| 2 | <ul><li>是，如果已验证选项合并规则=“上次已验证用户档案”</li><li>否，如果已验证选项合并规则=“当前已验证用户档案”或“无已验证用户档案”</li></ul> | 否，特征数据将写入设备用户档案。 |

示例调用（与身份验证状态对应的请求值会突出显示）:

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 在所有三种情况下 [在CID和UUID](../reference/ids-in-aam.md) 之间执行ID同步。

>[!MORELIKETHIS]
>
>* [客户 ID 和身份验证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

