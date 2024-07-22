---
description: 通过“配置文件链接”设备图实现区段重定位和个性化区段资格的Recommendations和用例。
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: 配置文件链接设备图用例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 4%

---

# 配置文件链接设备图用例 {#profile-link-device-graph-use-cases}

通过[!UICONTROL Profile Link Device Graph]进行区段重定位和个性化区段资格的Recommendations和用例。

## 推荐 {#recommendations}

考虑适用于以下促销活动的[!UICONTROL Profile Link]设备图：

* 在其数字资产中进行高级别身份验证。 如果只有少量经过身份验证的用户，请使用[外部设备图选项](merge-rule-definitions.md#device-options)。
* 需要准确地定位已知受众。 [!UICONTROL Profile Link Device Graph]是使用第一方经过验证的数据生成的。
* 实时定位处于已验证和未验证状态的已知受众。

![](assets/merge-rule-triangle2.png)

## 跨设备定位 {#cross-device-personalization}

假设John拥有三种用于搜索假日套餐交易的设备：笔记本电脑([!DNL Device 1])、智能手机([!DNL Device 2])和平板电脑([!DNL Device 3])。 但是，John使用自己的设备搜索包交易的不同项目：

* 他用笔记本电脑搜索航班；
* 他用智能手机搜索酒店；
* 他用平板电脑寻找导游。

即使John未在上述所有三个设备上通过身份验证，通过使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**&#x200B;规则，假如John是最后一个在所有三个设备上进行身份验证的人，假日包提供商也可以将这些设备与John的已验证配置文件关联。

![last-device-graph](assets/last-device-graph.png)

由于Audience Manager限定参与区段配置文件合并的每个设备配置文件，因此所有三个设备配置文件都会被分段。 [!UICONTROL Profile Link Device Graph]允许Audience Manager查看所有三台设备的行为，并让每台设备都符合没有单个设备配置文件单独符合条件的区段。

此[!UICONTROL Profile Merge Rule]使营销人员能够根据用户活动而不是单个设备活动，为某个人拥有的所有设备提供一致的体验。

![跨设备个性化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部设备图用例](external-graph-use-cases.md)
>* [配置文件合并规则的一般用例](merge-rule-targeting-options.md)
>* [配置文件合并规则常见问题解答](../../faq/faq-profile-merge.md)
