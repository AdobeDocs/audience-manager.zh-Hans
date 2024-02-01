---
description: 本文介绍如何为新集成和现有集成配置Amazon Advertising。
solution: Audience Manager
title: 将Amazon Advertising配置为基于设备的自助服务目标
source-git-commit: 01f3c2d813a91b8541bd8ba8a8b030f67a4f979e
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---


# 配置 [!DNL Amazon Advertising] 作为基于设备的自助服务目标 {#configure-amazon}

本文介绍如何配置与的集成 [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## 先决条件 {#prerequisites}

配置之前 [!DNL Amazon Advertising] 目标，请确保您满足以下先决条件。

* 您的 [!DNL Amazon] 帐户必须符合广告条件。
* 创建第一个 [!DNL Amazon Advertising] Audience Manager目标客户，请联系Adobe咨询或客户关怀团队以启用 [!DNL Amazon] 您的帐户的ID同步(数据源ID = 139200)。 这是Audience Manager和之间的正确同步所必需的 [!DNL Amazon].
* 创建新的数据提供程序受众后，您应 [更新其元数据](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) 并添加 **[!DNL audience fees]**. 对于此操作，您可以使用 [Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) 或 [Amazon广告UI](https://advertising.amazon.com/).

## 添加新 [!DNL Amazon Advertising] 目标 {#add-new-amazon-destination}

本节介绍配置新的基于设备的目标时需要执行的步骤 [!DNL Amazon Advertising]. 此方案假定您没有 [!DNL Amazon Advertising] 通过Adobe顾问或客户关怀配置的目标。

### 步骤1. 使用进行身份验证 [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

添加基于设备的目标之前，您需要关联Audience Manager和 [!DNL Amazon Advertising] 帐户。 以下是操作方法：

1. 登录到您的Audience Manager帐户并转到 **[!UICONTROL Administration > Integrated Accounts]**. 如果您之前配置了与目标平台的集成，您应该会看到此页面中列出了该集成。 否则，页面为空。
1. 选择 **[!UICONTROL Add Account]**.
1. 选择 [!UICONTROL Amazon Data Provider].

   ![集成平台](assets/dbd-amazon-without-options.png)

1. 选择其中一项 **[!UICONTROL Amazon Data Provider]** 选项取决于 [!DNL Amazon Ads] 创建帐户（北美洲、欧洲或远东），然后单击 **[!DNL Confirm]** 重定向到“身份验证”页面。

   ![集成平台](assets/dbd-amazon-with-options.png)

1. 完成身份验证后，您将被重定向到Audience Manager，您应会在其中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击 **[!UICONTROL Confirm]**. 这样，您就为Audience Manager授予了访问权限，以便向您的受众发送更新。

### 步骤 2. 创建新的基于设备的目标 {#step2-create-new-destination}

关联Audience Manager和 [!DNL Amazon Advertising] 帐户，您可以创建新目标。 以下是操作方法：

>[!NOTE]
>
>无法更改现有基于设备的目标的名称。 请确保提供有助于您正确识别目标的名称。

1. 登录到您的Audience Manager帐户，转到 **[!UICONTROL Audience Data > Destinations]**，并选择 **[!UICONTROL Create Destination]**.
1. 在 **[!UICONTROL Basic Information]** 部分，输入 **[!UICONTROL Name]** 和 **[!UICONTROL Description]** ，并使用以下设置：

   ![设置](assets/dbd-new-account-amazon.png)

1. 选择 **[!UICONTROL Next]**.
1. 选择 [数据导出标签](/help/using/features/data-export-controls.md#controls-labels) 要为此目标设置的属性。
1. 选择 **[!UICONTROL Save]**.
1. 在 **[!UICONTROL Segment Mappings]** 部分，选择要发送到此目标的受众区段。
1. 保存目标。

## 匹配率注意事项 {#match-rates-considerations}

Audience Manager与之间的集成 [!DNL Amazon Advertising] 支持历史受众回填。 所有区段资格都会发送到 [!DNL Amazon] 创建目标时。

## 故障排除 {#troubleshooting}

配置数据或将数据发送到 [!DNL Amazon Advertising] 目标，您可能会遇到如下所述的错误。 本节将说明导致错误的原因以及如何修复它们。

| 错误消息 | 发生次数/原因 | 解决方法 |
|---|---|---|
| `Internal server error` | 尝试添加新时，Audience ManagerUI中会显示此错误消息 [!DNL Amazon] 使用过时版本的Amazon API的帐户。 | 联系Adobe客户关怀部门。 |
| `Amazon Error: Account XXXXXXXXX was not found` | 当为目标配置的凭据无权访问相应的Amazon AdsAudience Manager时，帐户UI中会显示此错误消息。 | <ul><li>确保您使用的帐户凭据符合 [先决条件](#prerequisites).</li><li>使用相同的凭据导航到Amazon广告UI，并检查相应的帐户下是否显示正确的受众。 </li></ul> |
