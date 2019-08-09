---
description: 此过程需要AdWords再营销列表、像素代码和Audience Manager URL目标。它也称为搜索广告(RLA)集成的再营销列表。仅适用于付费搜索。
seo-description: 此过程需要AdWords再营销列表、像素代码和Audience Manager URL目标。它也称为搜索广告(RLA)集成的再营销列表。仅适用于付费搜索。
seo-title: 将区段发送到Google AdWords再营销列表
solution: Audience Manager
title: 将区段发送到Google AdWords再营销列表
uuid: ad821c6-48b4-42c0-42c0-b912-1563331e93 a2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# 将区段发送到Google Ads再营销列表 {#send-segments-to-a-google-adwords-remarketing-list}

此过程需要再 [!DNL Google Ads] 营销列表、像素代码和Audience Manager [!DNL URL] 目标。它也称为搜索广告([!DNL RLSA])集成的再营销列表。仅适用于付费搜索。

>[!IMPORTANT]
>请注意，这并不是两个系统的按产品分类集成。

要将 [!DNL Google Ads] 再营销列表设置为 [!DNL Audience Manager] URL目标，请执行以下操作：

1. 在 [!DNL Google Ads] 您的帐户中 [，创建网站重新营销列表](https://support.google.com/adwords/answer/2454064?hl=en) 并记下转换ID。
1. 使用以下URL作为基础URL和安全URL的模板。将xxxxxxx部分替换为转换ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience Manager中 [，创建URL目标](../../features/destinations/create-url-destination.md) 或编辑现有目标。创建目标时使用以下设置：
   * 类型：URL
   * 序列化：已启用
   * 分隔符：Semolon(；)

1. 在目标的 [!UICONTROL Segment Mappings] 部分 [!DNL URL] 中，将代码从步骤添加到 [!DNL URL] 和 [!DNL Secure URL] 字段。分别在 `http:``https:`[!DNL URL] 和 [!DNL Secure URL] 字段中预览代码。

   >[!IMPORTANT]
   >
   >用未编码的全域替换编码的半号 `&``&`

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
   >如果您使用多个区段，可为要映射到Google Ads目标的每个区段获取一个新的像素。这可以确保数据应用到适当的再营销列表。

1. 在Audience Manager中将新区段映射到此目标时，请定义映射并 `aam=segmentID` 替换 `segmentID` 为区段的ID。
1. 在中 [!DNL Google Ads]定义桶时，创建与在步骤中定义的映射匹配的规则。

完成的映射可能类似于：

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ This]
>
>* [目标](../../features/destinations/destinations.md)
>* [创建URL目标](../../features/destinations/create-url-destination.md)
>* [关于AdWords再营销列表](https://support.google.com/adwords/answer/2472738)
>* [AdWords再营销工作的原理](https://support.google.com/adwords/answer/2454000)

