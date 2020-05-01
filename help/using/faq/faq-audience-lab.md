---
description: 有关受众实验室功能的常见问题。
seo-description: 有关受众实验室功能的常见问题。
seo-title: 受众实验室常见问题解答
solution: Audience Manager
title: 受众实验室常见问题解答
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 受众实验室常见问题解答{#audience-lab-faq}

有关受众实验室功能的常见问题。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**在测试组中创建的测试段是否具有不同的段ID? 如何将ID映射到不同的目标？**

是，测试段具有不同的段ID。 对于发送到 [!UICONTROL Auto-fill Destination Mapping] 的目标或区 [!DNL Google]段， [!UICONTROL Audience Lab] 将像处理通常的目标一样处理映射值。

<br> 

**同一转换特征是否可以与多个测试组关联？**

是的，这是允许的。 假设一个测试使用与转换X关联的男性区段，而一个测试使用与转换X关联的女性区段。由于两个测试都在测试两个不同的受众，因此不管这两个测试都在推动转换。

<br> 

**假设测试组正在使用经过身份验证的用户档案进行测试段拆分。 已验证的用户档案链接到4个[受众管理器UUID](../reference/ids-in-aam.md)。 当访客显示四个UUID中的一个的转换特征时，是否将[!UICONTROL Audience Lab]其计为一个或四个转换？**

在这种情况下， [!UICONTROL Audience Lab] 只计一次转换。

<br> 

**如果上述情况的访客首先显示与其已验证用户档案链接的四个UUID中的一个的转换特征，然后还显示与已验证用户档案链接的另外两个UUID的转换特征，该怎么办？ 此情况是否计为一次或三次转换？**

在这种情况下 [!UICONTROL Audience Lab] ，对三个转换进行计数，每个设备显示身份验证特征时一个转换。

<br> 

**用户是否可以访[!UICONTROL Segment: Read-Only]问，同时也可以[!UICONTROL Audience Lab]测试段创建访问权限？**

有关 [如何使用权限](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) ，请参阅创建区段 [!UICONTROL Audience Lab] 测试 [!UICONTROL RBAC] 组。

**我是否可以[!UICONTROL Audience Lab]与外部设[!UICONTROL Profile Link Device Graph]备图形([Adobe Experience Cloud Device Co-op、Tapad Device Graph](https://docs.adobe.com/content/help/en/device-co-op/using/home.html)、Liveramp Device Graph)结合使用？**

目前， [!UICONTROL Audience Lab] 只能在使用时，按连接到符合条件的设备的设备划分细分群体 [!UICONTROL Profile Link Device Graph]。 我们正在为其他设备 [!UICONTROL Audience Lab] 图形添加支持，并会在我们添加支持时通知您。
