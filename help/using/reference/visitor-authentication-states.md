---
description: Audience Manager中的访客身份验证状态决定了新特征信息是写入到访客的已身份验证配置文件中，还是写入到收集数据的设备配置文件中。 Audience Manager以相同的方式处理事件调用中的访客ID身份验证状态UNKNOWN和LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Audience Manager中的访客身份验证状态
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 2%

---

# Audience Manager中的访客身份验证状态{#visitor-authentication-states-in-audience-manager}

Audience Manager中的访客身份验证状态决定了新特征信息是写入到访客的已身份验证配置文件中，还是写入到收集数据的设备配置文件中。 Audience Manager以相同的方式处理事件调用中的访客ID身份验证状态UNKNOWN和LOGGED_OUT。

从[!DNL Experience Cloud] ID服务版本1.5开始，`setCustomerID`方法包含可选的`AuthState`对象。 `AuthState`根据访客的[身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=zh-Hans)来识别访客。 [!DNL Audience Manager]根据调用中传递的身份验证状态以及用于分段的[配置文件合并规则](../features/profile-merge-rules/merge-rules-dashboard.md)，以不同方式处理已实现的特征。

## 身份验证状态：未知 {#auth-status-unknown}

| 请求值 | 从已验证的配置文件中读取信息 | 将新特征写入已验证的配置文件 |
|---|---|---|
| 0 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL No Authenticated Profile]。</li></ul> | 不会，特征数据会添加到设备配置文件中。 |

示例调用（与身份验证状态对应的请求值会高亮显示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 身份验证状态：已验证 {#auth-status-authenticated}

| 请求值 | 从已验证的配置文件中读取信息 | 将新特征写入已验证的配置文件 |
|---|---|---|
| 1 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile]。</li></ul> | 是，特征数据会添加到已验证的配置文件中。 |

示例调用（与身份验证状态对应的请求值会高亮显示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 身份验证状态：LOGGED_OUT {#auth-status-logged-out}

| 请求值 | 从已验证的配置文件中读取信息 | 将新特征写入已验证的配置文件 |
|---|---|---|
| 2 | <ul><li>是，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles]。</li><li>否，如果[!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles]或[!UICONTROL No Authenticated Profile]。</li></ul> | 否，特征数据会写入设备配置文件中。 |

示例调用（与身份验证状态对应的请求值会高亮显示）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>在所有三种情况下，[!DNL Audience Manager]都在[CID和UUID](../reference/ids-in-aam.md)之间执行ID同步。

>[!MORELIKETHIS]
>
>* [客户 ID 和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=zh-Hans)
