---
description: 此过程需要AdWords再营销列表、像素代码和Audience Manager URL目标。 它也称为搜索广告(RLSA)集成的再营销列表。 仅适用于付费搜索。
seo-description: 此过程需要AdWords再营销列表、像素代码和Audience Manager URL目标。 它也称为搜索广告(RLSA)集成的再营销列表。 仅适用于付费搜索。
seo-title: 将区段发送到Google adWords再营销列表
solution: Audience Manager
title: 将区段发送到Google adWords再营销列表
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 将区段发送到Google广告再营销列表 {#send-segments-to-a-google-adwords-remarketing-list}

此过程需要再 [!DNL Google Ads] 营销列表、像素代码和Audience manager目标 [!DNL URL] 位置。 它也称为搜索广告([!DNL RLSA])集成的再营销列表。 仅适用于付费搜索。

>[!IMPORTANT]
>请注意，这不是两个系统按产品分类的集成。

要将再营销列 [!DNL Google Ads] 表设置为 [!DNL Audience Manager] URL目标，请执行以下操作：

1. 在您的 [!DNL Google Ads] 帐户中， [创建网站再营销列表](https://support.google.com/adwords/answer/2454064?hl=en) ，并记下您的转化ID。
1. 将以下URL用作基本URL和安全URL的模板。 将xxxxxxxx部分替换为您的转换ID。

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 在Audience manager中，创 [建URL目标](../../features/destinations/create-url-destination.md) ，或编辑现有目标。 创建目标时，请使用以下设置：
   * 类型：URL
   * 序列化：已启用
   * 分隔符：分号(;)

1. 在目标 [!UICONTROL Segment Mappings] 位置的部 [!DNL URL] 分，将步骤2中的代码添加到和 [!DNL URL] 字 [!DNL Secure URL] 段。 分别在和字 `http:` 段中 `https:` 和前 [!DNL URL] 缀代 [!DNL Secure URL] 码前加和。

   >[!IMPORTANT]
   >
   >用未编码的 `&` &amp;符号替换编码的&amp;符 `&`

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
   >如果您使用多个区段，请为要映射到Google Ads目标的每个区段获取新像素。 这可确保将数据应用到相应的再营销列表。

1. 在Audience Manager中将新区段映射到此目标时，将映射定义为， `aam=segmentID` 并 `segmentID` 替换为区段的ID。
1. 在中定义存储段时， [!DNL Google Ads]请创建一个与第6步定义的映射相匹配的规则。

完成的映射可能类似于：

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [目标](../../features/destinations/destinations.md)
>* [创建URL目标](../../features/destinations/create-url-destination.md)
>* [关于AdWords再营销列表](https://support.google.com/adwords/answer/2472738)
>* [AdWords再营销的工作原理](https://support.google.com/adwords/answer/2454000)

