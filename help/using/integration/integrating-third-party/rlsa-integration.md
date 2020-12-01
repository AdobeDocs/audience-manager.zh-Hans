---
description: 此过程需要AdWords再营销列表、像素代码和Audience ManagerURL目标。 它也称为搜索广告(RLSA)集成的再营销列表。 仅适用于付费搜索。
seo-description: 此过程需要AdWords再营销列表、像素代码和Audience ManagerURL目标。 它也称为搜索广告(RLSA)集成的再营销列表。 仅适用于付费搜索。
seo-title: 将区段发送到 Google AdWords 再营销列表
solution: Audience Manager
title: 将区段发送到 Google AdWords 再营销列表
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 5%

---


# 将区段发送到Google广告再营销列表{#send-segments-to-a-google-adwords-remarketing-list}

此过程需要[!DNL Google Ads]再营销列表、像素代码和Audience Manager[!DNL URL] [!DNL destination]。 它也称为搜索广告集成的再营销列表([!DNL RLSA])。 仅适用于付费搜索。

>[!IMPORTANT]
>请注意，这不是两个系统按产品分类的集成。

将[!DNL Google Ads]再营销列表设置为[!DNL Audience Manager] [!DNL URL destination] :

1. 在您的[!DNL Google Ads]帐户中，[创建网站再营销列表](https://support.google.com/adwords/answer/2454064?hl=en)并记下您的转换ID。
1. 将以下URL用作基本URL和安全URL的模板。 将xxxxxxxxx部分替换为您的转换ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager中，[创建 [!DNL URL destination]](../../features/destinations/create-url-destination.md)或编辑现有[!DNL destination]。 创建[!DNL destination]时，请使用以下设置：
   * 类型：URL
   * 序列化：已启用
   * 分隔符：分号(;)

1. 在[!DNL URL] [!DNL destination]的[!UICONTROL Segment Mappings]部分，将步骤2中的代码添加到[!DNL URL]和[!DNL Secure URL]字段。 在[!DNL URL]和[!DNL Secure URL]字段中分别用`http:`和`https:`为代码添加前缀。

   >[!IMPORTANT]
   >
   >将编码和符`&`替换为未编码的和符`&`

   [!DNL URL]代码不安全：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   安全[!DNL URL]代码：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多个段，请为要映射到[!DNL Google Ads] [!DNL destination]的每个段获取新像素。 这可确保将数据应用于相应的再营销列表。

1. 在Audience Manager中将新段映射到此[!DNL destination]时，将映射定义为`aam=segmentID`，并将`segmentID`替换为段的ID。
1. 在[!DNL Google Ads]中定义存储段时，请创建与步骤6中定义的映射相匹配的规则。

完成的映射可能与以下内容类似：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [创建一个 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [关于AdWords再营销列表](https://support.google.com/adwords/answer/2472738)
>* [AdWords再营销的工作原理](https://support.google.com/adwords/answer/2454000)

