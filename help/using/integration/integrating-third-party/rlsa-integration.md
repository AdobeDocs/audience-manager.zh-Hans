---
description: 此过程需要AdWords再营销列表、像素代码和Audience ManagerURL目标。 它也称为搜索广告(RLSA)集成的再营销列表。 仅适用于付费搜索。
seo-description: 此过程需要AdWords再营销列表、像素代码和Audience ManagerURL目标。 它也称为搜索广告(RLSA)集成的再营销列表。 仅适用于付费搜索。
seo-title: 将区段发送到Google AdWords再营销列表
solution: Audience Manager
title: 将区段发送到Google AdWords再营销列表
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: c70d02637615848a86fc980a70868a6b0f7bda00
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# 将区段发送到Google Ads再营销列表 {#send-segments-to-a-google-adwords-remarketing-list}

此过程需要 [!DNL Google Ads] 再营销列表、像素代码和Audience Manager [!DNL URL][!DNL destination]。 它也称为搜索广告()集成的再营销[!DNL RLSA]列表。 仅适用于付费搜索。

>[!IMPORTANT]
>请注意，这不是两个系统按产品分类的集成。

要将再营销 [!DNL Google Ads] 列表设置为 [!DNL Audience Manager][!DNL URL destination]:

1. 在您的 [!DNL Google Ads] 帐户 [中，创建网站再营销列表](https://support.google.com/adwords/answer/2454064?hl=en) ，并记下您的转换ID。
1. 将以下URL用作基本URL和安全URL的模板。 将xxxxxxxxx部分替换为您的转换ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager [中，创建[!DNL URL目标]](../../features/destinations/create-url-destination.md) 或编辑现有 [!DNL destination]。 创建时，请使用以下设置 [!DNL destination]:
   * 类型： URL
   * 序列化： 已启用
   * 分隔符： 分号(;)

1. 在您 [!UICONTROL Segment Mappings] 的部分 [!DNL URL] ，将步骤2中 [!DNL destination]的代码添加到和 [!DNL URL] 字 [!DNL Secure URL] 段。 分别在和字 `http:` 段 `https:` 中和 [!DNL URL] 前缀 [!DNL Secure URL] 代码。

   >[!IMPORTANT]
   >
   >用未编码的 `&` &amp;符号替换已编码的&amp;符 `&`

   不安全 [!DNL URL] 的代码：

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   安全 [!DNL URL] 代码：

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多个区段，请为要映射到的每个区段获取新像素 [!DNL Google Ads][!DNL destination]。 这可确保将数据应用于相应的再营销列表。

1. 在Audience Manager中将新区段映 [!DNL destination] 射到此区段时，将映射 `aam=segmentID` 定义 `segmentID` 为，并替换为区段的ID。
1. 在中定义存储段 [!DNL Google Ads]时，创建与第6步定义的映射相匹配的规则。

完成的映射可能与以下内容类似：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL目标]](../../features/destinations/destinations.md)
>* [创建[!DNL URL目标]](../../features/destinations/create-url-destination.md)
>* [关于AdWords再营销列表](https://support.google.com/adwords/answer/2472738)
>* [AdWords再营销的工作原理](https://support.google.com/adwords/answer/2454000)

