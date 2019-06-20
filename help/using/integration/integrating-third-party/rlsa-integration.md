---
description: 此过程需要AdWords再营销列表、像素代码和Audience Manager URL目标。它也称为搜索广告(RLA)集成的再营销列表。仅适用于付费搜索。
seo-description: 此过程需要AdWords再营销列表、像素代码和Audience Manager URL目标。它也称为搜索广告(RLA)集成的再营销列表。仅适用于付费搜索。
seo-title: 将区段发送到Google AdWords再营销列表
solution: Audience Manager
title: 将区段发送到Google AdWords再营销列表
uuid: ad821c6-48b4-42c0-42c0-b912-1563331e93 a2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. 仅适用于付费搜索。

>[!IMPORTANT]
>请注意，这并不是两个系统的按产品分类集成。

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. In your [!DNL Google Ads] account, [create a website re-marketing list](https://support.google.com/adwords/answer/2454064?hl=en) and write down your conversion ID.
1. 使用以下URL作为基础URL和安全URL的模板。将xxxxxxx部分替换为转换ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. 创建目标时使用以下设置：
   * 类型：URL
   * 序列化：已启用
   * 分隔符：Semolon(；)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >如果您使用多个区段，可为要映射到Google Ads目标的每个区段获取一个新的像素。这可以确保数据应用到适当的再营销列表。

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

完成的映射可能类似于：

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ This]
>
>* [目标](../../features/destinations/destinations.md)
>* [创建URL目标](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [关于AdWords再营销列表](https://support.google.com/adwords/answer/2472738)
>* [AdWords再营销工作的原理](https://support.google.com/adwords/answer/2454000)

