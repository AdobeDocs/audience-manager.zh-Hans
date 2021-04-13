---
description: 有关 Audience Lab 功能的常见问题解答。
seo-description: 有关 Audience Lab 功能的常见问题解答。
seo-title: Audience Lab 常见问题解答
solution: Audience Manager
title: Audience Lab 常见问题解答
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
exl-id: 25bdabb5-2ba8-45d2-81ca-05c0590d7d96
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 100%

---

# Audience Lab 常见问题解答 {#audience-lab-faq}

有关 Audience Lab 功能的常见问题解答。

<!-- 

audience-lab-faq.xml

 -->

<br> 

**在测试组中创建的测试区段是否具有不同的区段 ID？如何将这些 ID 映射到不同的目标？**

是，测试区段具有不同的区段 ID。对于包含 [!UICONTROL Auto-fill Destination Mapping] 的目标或已发送到 [!DNL Google] 的区段，[!UICONTROL Audience Lab] 将像目标平常处理映射一样处理这些映射值。

<br> 

**同一转化特征是否可以与多个测试组关联？**

是，这是可行的。假设一个测试组使用与转化特征 X 相关联的男性受众区段，而另一个测试组使用与转化特征 X 相关联的女性受众区段。由于这两个测试组测试的是两个不同的受众区段，因此即使这两个测试组同时促进转化也无妨。

<br> 

**假设一个测试组正在使用已验证的用户配置文件进行测试区段拆分。该已验证的用户配置文件与 4 个 [Audience Manager UUID](../reference/ids-in-aam.md) 相关联。当访客展现的转化特征来源于这四个 UUID 中的一个 UUID 时，[!UICONTROL Audience Lab] 会将这计为一次还是四次转化？**

在这种情况下，[!UICONTROL Audience Lab] 只计入一次转化。

<br> 

**以上例为基础，如果访客随后展现的转化特征来源于与已验证配置文件相关联的另外两个 UUID（而不是上例中提及的四个 UUID），那么又会怎么样呢？是将这计为一次还是三次转化？**

在这种情况下，[!UICONTROL Audience Lab] 会计入三次转化，每个展现已验证特征的设备计入一次。

<br> 

**用户是否可以同时具有 [!UICONTROL Segment: Read-Only] 权限和 [!UICONTROL Audience Lab] 测试区段创建权限？**

有关如何结合使用 [!UICONTROL Audience Lab] 和 [!UICONTROL RBAC] 权限的信息，请参阅[创建区段测试组](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups)。

**我是否可以将 [!UICONTROL Audience Lab] 与 [!UICONTROL Profile Link Device Graph] 和外部设备图（[Adobe Experience Cloud 设备协作](https://docs.adobe.com/content/help/zh-Hans/device-co-op/using/home.html)、Tapad 设备图、Liveramp 设备图）结合使用？**

目前，在使用 [!UICONTROL Profile Link Device Graph] 时，[!UICONTROL Audience Lab] 只能按连接到某个合格设备的设备拆分区段人口。我们正努力在 [!UICONTROL Audience Lab] 中添加对其他设备图的支持，准备就绪后，我们将通知您。
