---
description: 本文介绍如何为新集成和现有集成配置Amazon Advertising 。
solution: Audience Manager
title: 将Amazon Advertising配置为基于设备的自助服务目标
exl-id: 049af52a-b425-493d-9e77-9ced7ba6d168
source-git-commit: bac3167927af0957e7081e1ea653464101affcb8
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# 将[!DNL Amazon Advertising]配置为基于设备的自助服务目标 {#configure-amazon}

本文介绍如何配置与[Amazon Advertising](https://advertising.amazon.com/API/docs/en-us)的集成。

## 先决条件 {#prerequisites}

在配置[!DNL Amazon Advertising]目标之前，请确保满足以下先决条件。

* 您的[!DNL Amazon]帐户必须适用于广告。
* 在Audience Manager实例中创建第一个[!DNL Amazon Advertising]目标时，请联系Adobe Consulting或客户关怀团队为您的帐户启用[!DNL Amazon] ID同步(数据Source ID = 139200)。 这是Audience Manager与[!DNL Amazon]之间正确同步所必需的。
* 创建新数据提供程序受众后，您应[更新其元数据](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put)并添加&#x200B;**[!DNL audience fees]**。 对于此操作，您可以使用[Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access)或[Amazon Advertising UI](https://advertising.amazon.com/)。

## 添加新的[!DNL Amazon Advertising]目标 {#add-new-amazon-destination}

本节介绍为[!DNL Amazon Advertising]配置新的基于设备的目标时需要执行的步骤。 此方案假定您没有通过Adobe顾问或客户关怀部门配置的现有[!DNL Amazon Advertising]目标。

### 步骤1. 使用[!DNL Amazon Advertising]进行身份验证 {#step1-authenticate-with-amazon}

添加基于设备的目标之前，您需要关联Audience Manager和[!DNL Amazon Advertising]帐户。 以下是操作方法：

1. 登录到您的Audience Manager帐户并转到&#x200B;**[!UICONTROL Administration > Integrated Accounts]**。 如果您之前配置了与目标平台的集成，您应该会看到此页面中列出了该集成。 否则，页面为空。
1. 选择&#x200B;**[!UICONTROL Add Account]**。
1. 选择[!UICONTROL Amazon Data Provider]。

   ![集成平台](assets/dbd-amazon-without-options.png)

1. 根据创建[!DNL Amazon Ads]帐户的区域（北美洲、欧洲或远东）选择&#x200B;**[!UICONTROL Amazon Data Provider]**&#x200B;选项之一，然后单击&#x200B;**[!DNL Confirm]**&#x200B;以重定向到身份验证页面。

   ![集成平台](assets/dbd-amazon-with-options.png)

1. 完成身份验证后，您将被重定向到Audience Manager，您应会在其中看到关联的广告商帐户。 选择要使用的广告商帐户，然后单击&#x200B;**[!UICONTROL Confirm]**。 这样，您就为Audience Manager授予了访问权限，以便向您的受众发送更新。

### 步骤 2. 创建新的基于设备的目标 {#step2-create-new-destination}

关联Audience Manager和[!DNL Amazon Advertising]帐户后，即可创建新目标。 以下是操作方法：

>[!NOTE]
>
>无法更改现有基于设备的目标的名称。 请确保提供有助于您正确识别目标的名称。

1. 登录到您的Audience Manager帐户，转到&#x200B;**[!UICONTROL Audience Data > Destinations]**，然后选择&#x200B;**[!UICONTROL Create Destination]**。
1. 在&#x200B;**[!UICONTROL Basic Information]**&#x200B;部分中，输入新目标的&#x200B;**[!UICONTROL Name]**&#x200B;和&#x200B;**[!UICONTROL Description]**，并使用以下设置：

   ![设置](assets/dbd-new-account-amazon.png)

1. 选择&#x200B;**[!UICONTROL Next]**。
1. 选择要为此目标设置的[数据导出标签](/help/using/features/data-export-controls.md#controls-labels)。
1. 选择&#x200B;**[!UICONTROL Save]**。
1. 在&#x200B;**[!UICONTROL Segment Mappings]**&#x200B;部分中，选择要发送到此目标的受众区段。
1. 保存目标。

## 匹配率注意事项 {#match-rates-considerations}

Audience Manager与[!DNL Amazon Advertising]之间的集成支持历史受众回填。 在您创建目标时，所有区段资格都会发送到[!DNL Amazon]。

## 故障排除 {#troubleshooting}

配置数据或将数据发送到[!DNL Amazon Advertising]目标时，您可能会遇到如下所述的错误。 本节将说明导致错误的原因以及如何修复它们。

| 错误消息 | 发生次数/原因 | 解决方法 |
|---|---|---|
| `Internal server error` | 尝试使用过时版本的Amazon API添加新的[!DNL Amazon]Audience Manager时，帐户用户界面中会显示此错误消息。 | 联系Adobe客户关怀部门。 |
| `Amazon Error: Account XXXXXXXXX was not found` | 当为目标配置的凭据无权访问相应的Amazon AdsAudience Manager时，帐户UI中会显示此错误消息。 | <ul><li>确保您使用的帐户凭据符合[先决条件](#prerequisites)。</li><li>使用相同的凭据导航到Amazon广告UI，并检查相应的帐户下是否显示正确的受众。 </li></ul> |
