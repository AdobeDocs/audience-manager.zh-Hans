---
description: 本文介绍如何为新集成和现有集成配置Twitter自定义受众。
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: 将Twitter自定义受众配置为基于设备的自助服务目标
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# 配置 [!DNL Twitter Custom Audiences] 作为基于设备的自助服务目的地 {#configure-twitter}

本文介绍如何配置与的集成 [Twitter自定义受众](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## 先决条件 {#prerequisites}

在配置之前 [!DNL Twitter Custom Audiences] 目标，请确保满足以下先决条件。

* 您的 [!DNL Twitter Ads] 帐户必须符合广告资格。 新建 [!DNL Twitter Ads] 帐户在创建后头2周内没有资格获得广告。
* 您的 [!DNL Twitter] 您授权在Audience Manager中访问的用户帐户必须具有 [合作伙伴Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 权限启用。
* 创建 [!DNL Twitter Custom Audiences] 目标，请联系Adobe咨询或客户关怀以启用 [!DNL Twitter] 您帐户的ID同步（数据源ID = 1123）。 要在Audience Manager和之间正确同步，需要此参数 [!DNL Twitter].

## 添加新 [!DNL Twitter Custom Audiences] 目标 {#add-new-twitter-destination}

本节介绍在为 [!DNL Twitter Custom Audiences]. 此方案假定您没有现有 [!DNL Twitter Custom Audiences] 目标。

### 步骤 1. 验证 [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

在添加基于设备的目标之前，您需要先将Audience Manager和 [!DNL Twitter Custom Audiences] 帐户。 下面是如何执行此操作：

1. 登录到您的Audience Manager帐户，然后转到 **[!DNL Administration > Integrated Accounts]**. 如果您之前配置了与目标平台的集成，则应会在此页面中列出该集成。 否则，页面为空。
1. 单击 **[!DNL Add Account]**.
1. 选择 [!DNL Twitter Custom Audiences] 单击 **[!DNL Confirm]** 重定向到身份验证页面。

   ![集成平台](assets/dbd-integrated-platforms.png)

1. 经过身份验证后，您将被重定向到Audience Manager，您应该在该位置看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击 **[!DNL Confirm]**.

### 步骤 2. 创建新的基于设备的目标 {#step2-create-new-destination}

在链接了Audience Manager和 [!DNL Twitter Custom Audiences]，则可以创建新目标。 下面是如何执行此操作：

>[!NOTE]
>
>您无法更改现有基于设备的目标的名称。 确保提供有助于您正确识别目标的名称。

1. 登录您的Audience Manager帐户，转到 **[!DNL Audience Data > Destinations]**，然后单击 **[!DNL Create Destination]**.
1. 在 **[!DNL Basic Information]** ，输入 **[!DNL Name]** 和 **[!DNL Description]** ，然后使用以下设置： ![设置](assets/dbd-new-basic.png)
1. 单击 **[!DNL Next]**.
1. 选择 [数据导出标签](/help/using/features/data-export-controls.md#controls-labels) 要为此目标设置的URL。
1. 单击 **[!DNL Save]**.
1. 在 **[!DNL Segment Mappings]** 部分，选择要发送到此目标的受众区段。
1. 保存目标。

## 区段映射注意事项 {#segment-mapping-considerations}

将受众区段映射到 [!UICONTROL Twitter]，请确保满足以下区段命名要求：

* 提供人类可读的区段映射名称。 我们建议您使用与Audience Manager区段相同的名称。
* 请勿使用特殊字符(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)。 如果您的Audience Manager区段名称包含这些字符，请先删除这些字符，然后再将区段映射到 [!UICONTROL Twitter] 目标。

### 示例

* 正确的区段或映射名称：“美国和欧洲购物者”；
* 区段或映射名称不正确：“美国、欧洲5h0pP3rs”。

>[!IMPORTANT]
>
>您无法更改已映射区段的名称。 Audience Manager使用区段名称来正确识别集成中的区段。

## 匹配率注意事项 {#match-rates-considerations}

* Audience Manager与 [!UICONTROL Twitter Custom Audiences] 支持历史受众回填。 所有区段资格均发送至 [!UICONTROL Twitter] 创建目标时。

## 故障诊断 {#troubleshooting}

在配置数据或将数据发送到Twitter自定义受众目标时，您可能会遇到以下描述的错误。 本节将介绍哪些因素可能导致错误以及如何修复错误。

| 错误消息 | 发生次数/原因 | 分辨率 |
|---|---|---|
| `Internal server error` | 尝试添加新Audience Manager时，UI中会显示此错误消息 [!DNL Twitter] 帐户，该帐户使用的是过时的Twitter API版本。 | 联系 Adobe 客户关怀. |
| `Twitter Error: This request is not properly authenticated` | 尝试将具有不受支持区段名称的区段映射到目标时，Audience ManagerUI中会显示此错误消息。 | 查看映射的区段名称，并确保它们不包含不受支持的字符。 请参阅 [区段映射注意事项](#segment-mapping-considerations) ，以获取不支持的字符列表。 |
| `Twitter Error: Account XXXXXXXXX was not found` | 当为目标配置的凭据无权访问相应的Twitter Ads帐户时，Audience ManagerUI中会显示此错误消息。 | <ul><li>确保您使用的帐户凭据符合 [先决条件](#prerequisites).</li><li>使用相同的凭据导航到Twitter Ads UI，并检查相应的 `XXXXXXXXX` 帐户。 </li></ul> |