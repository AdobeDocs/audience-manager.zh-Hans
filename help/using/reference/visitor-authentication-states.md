---
description: Audience Manager 中访客身份验证状态可确定是否将新的特征信息写入访客的经过身份验证的用户档案或设备用户档案（从中收集数据）。 Audience Manager 处理未知的访客 ID 身份验证状态，并以相同的方式在事件调用中 LOGGED_OUT。
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Audience Manager 中的访客身份验证状态
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Audience Manager 中的访客身份验证状态{#visitor-authentication-states-in-audience-manager}

Audience Manager 中访客身份验证状态可确定是否将新的特征信息写入访客的经过身份验证的用户档案或设备用户档案（从中收集数据）。 Audience Manager 处理未知的访客 ID 身份验证状态，并以相同的方式在事件调用中 LOGGED_OUT。

[!DNL Experience Cloud]从 ID 服务 v 1.5 + 开始，该 `setCustomerID` 方法包含可选 `AuthState` 对象。`AuthState` 根据访客的 [ 身份验证状态 ](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) 进行识别。 [!DNL Audience Manager] 根据调用中传递的身份验证状态和 [ 用于分段的配置文件合并规则 ](../features/profile-merge-rules/merge-rules-dashboard.md) ，以不同方式处理已实现的特征。

## Authentication 状态：未知 {#auth-status-unknown}

| 请求值 | 从已验证的用户档案中读取信息 | 将新特征写入经过身份验证的用户档案 |
|---|---|---|
| 0 | <ul><li>是，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>否，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL No Authenticated Profile] 。</li></ul> | 不会，这些特征数据会添加到设备用户档案中。 |

示例调用（显示与身份验证状态对应的请求值）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication 状态：已验证 {#auth-status-authenticated}

| 请求值 | 从已验证的用户档案中读取信息 | 将新特征写入经过身份验证的用户档案 |
|---|---|---|
| 1 | <ul><li>是，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL Last Authenticated Profiles].</li><li>否，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | 是，特徵資料會新增至已驗證的設定檔。 |

示例调用（显示与身份验证状态对应的请求值）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication 状态： LOGGED_OUT {#auth-status-logged-out}

| 请求值 | 从已验证的用户档案中读取信息 | 将新特征写入经过身份验证的用户档案 |
|---|---|---|
| 2 | <ul><li>是，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles] 。</li><li>否，如果 [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 或 [!UICONTROL No Authenticated Profile] 。</li></ul> | 否，特徵資料會寫入裝置設定檔中。 |

呼叫範例（反白顯示與驗證狀態對應的請求值）：

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 執行ID同步，介於 [CID和UUID](../reference/ids-in-aam.md) 在所有三種情況下。

>[!MORELIKETHIS]
>
>* [客户 ID 和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

