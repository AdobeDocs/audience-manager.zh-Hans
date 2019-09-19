---
description: 有关Audience lab功能的常见问题解答。
seo-description: 有关Audience lab功能的常见问题解答。
seo-title: Audience Lab常见问题解答
solution: Audience Manager
title: Audience Lab常见问题解答
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab常见问题解答{#audience-lab-faq}

有关Audience lab功能的常见问题解答。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**在测试组中创建的测试段是否具有不同的段ID? 如何将ID映射到不同的目标？**

是的，测试段具有不同的段ID。 对于发送到 [!UICONTROL Auto-fill Destination Mapping] 的目标或区段， [!DNL Google][!UICONTROL Audience Lab] 将像处理通常的目标一样处理映射值。

<br> 

**同一转换特征是否可以与多个测试组关联？**

是的，这是允许的。 假设一个测试使用与转换X关联的阳段，而一个测试使用与转换X关联的阴段。由于测试了两个不同的受众，所以这两个测试都会推动转化率，这并不重要。

<br> 

**假设测试组正在为测试段拆分使用经过身份验证的配置文件。 已验证的配置文件链接到4[个Audience Manager UUID](../reference/ids-in-aam.md)。 当访客显示四个UUID中的一个的转换特征时，是否[!UICONTROL Audience Lab]将此计为一个或四个转换？**

在这种情况下， [!UICONTROL Audience Lab] 只计一次转化。

<br> 

**如果上述情况的访客首先显示与其已验证配置文件链接的四个UUID中的一个的转换特征，然后显示与已验证配置文件链接的两个其他UUID的转换特征，该怎么办？ 此情况是否计为一次或三次转换？**

在这种情况下， [!UICONTROL Audience Lab] 对三个转换进行计数，每个设备显示身份验证特征。

<br> 

**用户是否可以访[!UICONTROL Segment: Read-Only]问，但也可以测试[!UICONTROL Audience Lab]区段创建访问权限？**

有关如 [何使用权限的信息](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ，请参阅创建区段测 [!UICONTROL Audience Lab] 试组 [!UICONTROL RBAC] 。

**我是否可以[!UICONTROL Audience Lab]与外部设备图[!UICONTROL Profile Link Device Graph]形([Adobe Experience Cloud Device Co-op、Tapad Device Graph、Liveramp Device Graph](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html))结合使用？**

目前，在 [!UICONTROL Audience Lab] 使用时，只能由连接到符合条件的设备的设备拆分细分群体 [!UICONTROL Profile Link Device Graph]。 我们正在为其他设备图形 [!UICONTROL Audience Lab] 添加支持，并会在我们添加支持时通知您。
