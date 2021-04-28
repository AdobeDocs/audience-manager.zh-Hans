---
description: Audience Manager中的访客身份验证状态确定新特征信息是写入访客的已验证用户档案还是写入设备用户档案（从中收集数据）。 Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: Audience Manager中的访客身份验证状态确定新特征信息是写入访客的已验证用户档案还是写入设备用户档案（从中收集数据）。 Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT。
seo-title: Audience Manager 中的访客身份验证状态
solution: Audience Manager
title: Audience Manager 中的访客身份验证状态
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 参考
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: c3c829ef1335d1e073b719f8252103fa578bb4e6
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 7%

---

# Audience Manager 中的访客身份验证状态{#visitor-authentication-states-in-audience-manager}

Audience Manager中的访客身份验证状态确定新特征信息是写入访客的已验证用户档案还是写入设备用户档案（从中收集数据）。 Audience Manager以相同方式处理访客ID身份验证状态UNKNOWN和LOGGED_OUT。

从[!DNL Experience Cloud] ID服务v1.5+开始，`setCustomerID`方法包括可选的`AuthState`对象。 `AuthState` 根据访客的身份验 [证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。[!DNL Audience Manager] 根据呼叫中传递的身份验证状态和用于分段的 [用户档案合](../features/profile-merge-rules/merge-rules-dashboard.md) 并规则，以不同方式处理已实现的特征。

## 身份验证状态：未知{#auth-status-unknown}

| 请求值 | 从已验证的用户档案读取信息 | 向已验证的用户档案写入新特征 |
|---|---|---|
| 0 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL No Authenticated Profile]。</li></ul> | 否，特征数据将添加到设备用户档案。 |

示例调用（与身份验证状态对应的请求值会突出显示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 身份验证状态：已验证{#auth-status-authenticated}

| 请求值 | 从已验证的用户档案读取信息 | 向已验证的用户档案写入新特征 |
|---|---|---|
| 1 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile]。</li></ul> | 是，特征数据将添加到已验证用户档案。 |

示例调用（与身份验证状态对应的请求值会突出显示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 身份验证状态：LOGGED_OUT {#auth-status-logged-out}

| 请求值 | 从已验证的用户档案读取信息 | 向已验证的用户档案写入新特征 |
|---|---|---|
| 2 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL No Authenticated Profile]。</li></ul> | 否，特征数据将写入设备用户档案。 |

示例调用（与身份验证状态对应的请求值会突出显示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 在所有三种情况下 [执行](../reference/ids-in-aam.md) CID和UUID之间的ID同步。

>[!MORELIKETHIS]
>
>* [客户 ID 和身份验证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

