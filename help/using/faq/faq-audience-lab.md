---
description: 有关Audience Lab功能的常见问题。
seo-description: 有关Audience Lab功能的常见问题。
seo-title: Audience Lab常见问题解答
solution: Audience Manager
title: Audience Lab常见问题解答
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6 d45 d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

有关Audience Lab功能的常见问题。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**在测试组中创建的测试区段是否有不同的细分ID？How do I map the IDs to different destinations?**

是，测试区段具有不同的区段ID。For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**相同的转化特征是否可以与多个测试组关联？**

是，这是允许的。请考虑使用与转换X相关的男性细分以及使用与转换X关联的女性细分进行一次测试的情况。这两种测试都推动了转换，这一点并不重要，因为测试两个不同的受众也是如此。

<br> 

**假设测试组正在使用针对测试细分拆分的身份验证配置文件。The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**如果上述案例中的访客来自于与其身份验证配置文件关联的四个UUID中的一个，那么该转换特征会来自链接到该身份验证配置文件的其他两个UUID中的转化特征，该转换特征是否会显示转换特征？Does this case count as one or three conversions?**

In this case, [!UICONTROL Audience Lab] counts three conversions, one for each device that has exhibited the authentication trait.

<br> 

**用户是否可以[!UICONTROL Segment: Read-Only]访问，还[!UICONTROL Audience Lab]可以测试区段创建访问？**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**我是否可以与和外部设备图表[!UICONTROL Audience Lab]一起使用？[!UICONTROL Profile Link Device Graph][Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html)、Tapad Device Graph、Liveramp Device Graph？**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
