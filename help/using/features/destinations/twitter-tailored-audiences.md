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
source-wordcount: '689'
ht-degree: 1%

---

# 将[!DNL Twitter Custom Audiences]配置为基于设备的自助服务目标 {#configure-twitter}

本文介绍如何配置与[Twitter自定义受众](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html)的集成。

## 先决条件 {#prerequisites}

在配置[!DNL Twitter Custom Audiences]目标之前，请确保满足以下先决条件。

* 您的[!DNL Twitter Ads]帐户必须适用于广告。 新[!DNL Twitter Ads]帐户在创建后的前2周内没有资格进行广告。
* 您在Audience Manager中授权访问的[!DNL Twitter]用户帐户必须启用[合作伙伴Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels)权限。
* 在Audience Manager实例中创建第一个[!DNL Twitter Custom Audiences]目标时，请联系Adobe Consulting或客户关怀团队为您的帐户启用[!DNL Twitter] ID同步(数据Source ID = 1123)。 这是Audience Manager与[!DNL Twitter]之间正确同步所必需的。

## 添加新的[!DNL Twitter Custom Audiences]目标 {#add-new-twitter-destination}

本节介绍为[!DNL Twitter Custom Audiences]配置新的基于设备的目标时需要执行的步骤。 此方案假定您没有通过Adobe顾问或客户关怀部门配置的现有[!DNL Twitter Custom Audiences]目标。

### 步骤1. 使用[!DNL Twitter Custom Audiences]进行身份验证 {#step1-authenticate-with-twitter}

在添加基于设备的目标之前，您需要关联Audience Manager和您的[!DNL Twitter Custom Audiences]帐户。 以下是操作方法：

1. 登录到您的Audience Manager帐户并转到&#x200B;**[!DNL Administration > Integrated Accounts]**。 如果您之前配置了与目标平台的集成，您应该会看到此页面中列出了该集成。 否则，页面为空。
1. 单击 **[!DNL Add Account]**。
1. 选择[!DNL Twitter Custom Audiences]并单击&#x200B;**[!DNL Confirm]**&#x200B;以重定向到身份验证页面。

   ![集成平台](assets/dbd-integrated-platforms.png)

1. 完成身份验证后，您将被重定向到Audience Manager，您应该会在其中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!DNL Confirm]**。

### 步骤 2. 创建新的基于设备的目标 {#step2-create-new-destination}

关联Audience Manager和[!DNL Twitter Custom Audiences]后，即可创建新目标。 以下是操作方法：

>[!NOTE]
>
>无法更改现有基于设备的目标的名称。 请确保提供有助于您正确识别目标的名称。

1. 登录到您的Audience Manager帐户，转到&#x200B;**[!DNL Audience Data > Destinations]**，然后单击&#x200B;**[!DNL Create Destination]**。
1. 在&#x200B;**[!DNL Basic Information]**&#x200B;部分中，输入新目标的&#x200B;**[!DNL Name]**&#x200B;和&#x200B;**[!DNL Description]**，并使用以下设置：![设置](assets/dbd-new-basic.png)
1. 单击 **[!DNL Next]**。
1. 选择要为此目标设置的[数据导出标签](/help/using/features/data-export-controls.md#controls-labels)。
1. 单击 **[!DNL Save]**。
1. 在&#x200B;**[!DNL Segment Mappings]**&#x200B;部分中，选择要发送到此目标的受众区段。
1. 保存目标。

## 区段映射注意事项 {#segment-mapping-considerations}

将受众区段映射到[!UICONTROL Twitter]时，请确保满足以下区段命名要求：

* 提供人类可读的区段映射名称。 我们建议您使用与Audience Manager区段相同的名称。
* 不要在区段和区段映射名称中使用特殊字符(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)。 如果您的Audience Manager区段名称包含这些字符，请在将区段映射到[!UICONTROL Twitter]目标之前删除它们。

### 示例

* 正确的区段或映射名称：“美国和欧洲购物者”；
* 区段或映射名称不正确：“US， European 5h0pP3rs”。

>[!IMPORTANT]
>
>无法更改已映射区段的名称。 Audience Manager使用区段名称来正确识别集成中的区段。

## 匹配率注意事项 {#match-rates-considerations}

* Audience Manager与[!UICONTROL Twitter Custom Audiences]之间的集成支持历史受众回填。 在您创建目标时，所有区段资格都会发送到[!UICONTROL Twitter]。

## 故障排除 {#troubleshooting}

配置数据或将数据发送到Twitter自定义受众目标时，您可能会遇到如下所述的错误。 本节将说明导致错误的原因以及如何修复它们。

| 错误消息 | 发生次数/原因 | 解决方法 |
|---|---|---|
| `Internal server error` | 尝试使用过时版本的Twitter API添加新的[!DNL Twitter]帐户时，Audience Manager UI中会显示此错误消息。 | 联系Adobe客户关怀部门。 |
| `Twitter Error: This request is not properly authenticated` | 尝试将具有不支持的区段名称的区段映射到目标时，Audience Manager UI中会显示此错误消息。 | 查看映射的区段名称，确保它们不包含不支持的字符。 有关不支持的字符列表，请参阅[区段映射注意事项](#segment-mapping-considerations)。 |
| `Twitter Error: Account XXXXXXXXX was not found` | 当为目标配置的凭据无权访问相应的Twitter广告帐户时，Audience Manager UI中会显示此错误消息。 | <ul><li>确保您使用的帐户凭据符合[先决条件](#prerequisites)。</li><li>使用相同的凭据导航到Twitter广告UI，并检查相应的`XXXXXXXXX`帐户下是否显示正确的受众。 </li></ul> |