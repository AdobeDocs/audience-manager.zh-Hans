---
description: 本文介绍如何为新集成和现有集成配置Twitter定制受众。
seo-description: 本文介绍如何为新集成和现有集成配置Twitter定制受众。
seo-title: 将特定于 Twitter 的受众配置为基于设备的自助服务目标
solution: Audience Manager
title: 将特定于 Twitter 的受众配置为基于设备的自助服务目标
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 8ff76decc1cbd7f7babd619dd1ce9fe047541337
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 4%

---


# 配置 [!DNL Twitter Tailored Audiences] 为基于自助设备的目标 {#configure-twitter}

本文介绍如何配置与Twitter定制 [受众的集成](https://business.twitter.com/en/targeting/tailored-audiences.html)。

## 先决条件 {#prerequisites}

在配置目 [!DNL Twitter Tailored Audiences] 标之前，请确保查看需要满足的以下Twitter先决条件。

1. 您的 [!DNL Twitter Ads] 帐户必须符合广告资格。 新帐 [!DNL Twitter Ads] 户在创建后的头2周内没有资格获得广告。
2. 在Audience Manager [!DNL Twitter] 中授权访问的用户帐户必须启用“ [合作伙伴受众管理者](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) ”权限。
3. 在您的Audience Manager实 [!DNL Twitter Tailored Audiences] 例中创建第一个目标时，请与Adobe咨询或客户服务部门联系，为您的 [!DNL Twitter] 帐户启用ID同步（数据源ID = 1123）。 这是在Audience Manager和之间正确同步所必需的 [!DNL Twitter]。

## 添加新目 [!DNL Twitter Tailored Audiences] 标 {#add-new-twitter-destination}

本节介绍为配置新的基于设备的目标时需要遵循的步骤 [!DNL Twitter Tailored Audiences]。 此方案假定您没有通过Adobe顾 [!DNL Twitter Tailored Audiences] 问或客户关怀配置现有目标。

### 步骤 1. 验证 [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

在添加基于设备的目标之前，您需要先将Audience Manager与帐户关 [!DNL Twitter Tailored Audiences] 联。 下面介绍如何实现此操作：

1. 登录您的Audience Manager帐户并转到 **[!DNL Administration > Integrated Accounts]**。 如果您之前配置了与目标平台的集成，您应会在本页中看到该集成。 否则，页面为空。
1. 单击 **[!DNL Add Account]**.
1. 选择 [!DNL Twitter Tailored Audiences] 并单击 **[!DNL Confirm]** 以重定向到身份验证页面。                     ![集成平台](assets/dbd-integrated-platforms.png)
1. 通过身份验证后，您将被重定向到Audience Manager，您应在该看到关联的广告商帐户的位置。 选择要使用的广告商帐户并单击 **[!DNL Confirm]**。

### 步骤 2. 创建新的基于设备的目标 {#step2-create-new-destination}

链接Audience Manager和 [!DNL Twitter Tailored Audiences]后，可以创建新目标。 下面介绍如何实现此操作：

>[!NOTE]
>
>无法更改现有基于设备的目标的名称。 请确保提供有助于正确识别目标的名称。

1. 登录到您的Audience Manager帐户，转 **[!DNL Audience Data > Destinations]**&#x200B;到并单击 **[!DNL Create Destination]**。
1. 在部 **[!DNL Basic Information]** 分中，输入 **[!DNL Name]** 和 **[!DNL Description]** 作为新目标，然后使用以下设置： ![设置](assets/dbd-new-basic.png)
1. 单击 **[!DNL Next]**.
1. 选择 [要为此目标](/help/using/features/data-export-controls.md#controls-labels) 设置的数据导出标签。
1. 单击 **[!DNL Save]**.
1. 在部 **[!DNL Segment Mappings]** 分中，选择要发送到此目标的受众段。
1. 保存目标。

## 区段映射注意事项 {#segment-mapping-considerations}

将受众段映射 [!UICONTROL Twitter]到时，请确保满足以下段命名要求：

* 提供可读的段映射名称。 我们建议使用您用于Audience Manager区段的相同名称。
* 请勿在段和段映射名`,` 称中 `%` 使 `:` 用 `;` 特殊字 `@``/``=``?``$`符()。 如果您的Audience Manager段名称包含这些字符，请先删除这些字符，然后再将段映射到目 [!UICONTROL Twitter] 标。

### 示例

* 正确的区段或映射名称： “美国和欧洲购物者”;
* 段或映射名称不正确： “美国、欧洲5h0pP3rs”。

>[!IMPORTANT]
>
>您无法更改已映射区段的名称。 Audience Manager使用区段名称来正确识别集成中的区段。

## 匹配率注意事项 {#match-rates-considerations}

* Audience Manager与历史受众回 [!UICONTROL Twitter Tailored Audiences] 填之间的集成支持。 创建目标时，会将所 [!UICONTROL Twitter] 有细分资格发送到。
