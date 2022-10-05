---
description: 此过程需要AdWords再营销列表、像素代码和Audience ManagerURL目标。 它也称为搜索广告(RLSA)集成的再营销列表。 仅适用于付费搜索。
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: 将区段发送到 Google AdWords 再营销列表
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# 将区段发送到Google广告再营销列表 {#send-segments-to-a-google-adwords-remarketing-list}

此过程需要 [!DNL Google Ads] 再营销列表、像素代码和Audience Manager [!DNL URL] [!DNL destination]. 它也称为搜索广告的再营销列表([!DNL RLSA])集成。 仅适用于付费搜索。

>[!IMPORTANT]
>请注意，这不是两个系统的按产品化集成。

设置 [!DNL Google Ads] 再营销列表 [!DNL Audience Manager] [!DNL URL destination]:

1. 在 [!DNL Google Ads] 帐户， [创建网站再营销列表](https://support.google.com/tagmanager/answer/6106960?hl=en) 并记下转换ID。
1. 将以下URL用作基本URL和安全URL的模板。 将xxxxxxxx部分替换为您的转化ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager中， [创建 [!DNL URL destination]](../../features/destinations/create-url-destination.md) 或编辑现有 [!DNL destination]. 在创建 [!DNL destination]:
   * 类型：URL
   * 序列化：已启用
   * 分隔符：分号(&amp;semi;))

1. 在 [!UICONTROL Segment Mappings] 部分 [!DNL URL] [!DNL destination]，将步骤2中的代码添加到 [!DNL URL] 和 [!DNL Secure URL] 字段。 为代码添加前缀 `http:` 和 `https:` 在 [!DNL URL] 和 [!DNL Secure URL] 字段。

   >[!IMPORTANT]
   >
   >替换编码的与号 `&` 与号未编码 `&`

   不安全 [!DNL URL] 代码：

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
   >如果您使用多个区段，请为要映射到的每个区段获取一个新像素 [!DNL Google Ads] [!DNL destination]. 这可确保数据被应用到相应的再营销列表。

1. 将新区段映射到此 [!DNL destination] 在Audience Manager中，将映射定义为 `aam=segmentID` 替换 `segmentID` 和区段的ID。
1. 在中定义存储段时 [!DNL Google Ads]，则创建与步骤6中定义的映射匹配的规则。

已完成的映射可能类似于以下内容：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [创建一个 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [关于AdWords再营销列表](https://support.google.com/adwords/answer/2472738)
>* [AdWords再营销的工作原理](https://support.google.com/adwords/answer/2454000)

