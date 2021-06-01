---
description: Recommendations和使用配置文件链接设备图进行区段重定向和个性化区段鉴别的用例。
seo-description: Recommendations和使用配置文件链接设备图进行区段重定向和个性化区段鉴别的用例。
seo-title: 配置文件关联设备图用例
solution: Audience Manager
title: 配置文件关联设备图用例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: 配置文件合并
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# 配置文件关联设备图用例 {#profile-link-device-graph-use-cases}

Recommendations和使用[!UICONTROL Profile Link Device Graph]进行区段重定位和个性化区段鉴别的用例。

## 推荐 {#recommendations}

请考虑[!UICONTROL Profile Link]设备图，该设备图用于以下促销活动：

* 对其数字属性进行高级身份验证。 如果您有少量经过身份验证的用户，请使用[外部设备图选项](merge-rule-definitions.md#device-options)。
* 需要准确定位已知受众。 [!UICONTROL Profile Link Device Graph]是使用经过身份验证的第一方数据构建的。
* 实时定位处于已验证和未验证状态的已知受众。

![](assets/merge-rule-triangle2.png)

## 跨设备定位{#cross-device-personalization}

比如说，John拥有三种设备，他经常使用这些设备来搜索假日套餐促销：他的笔记本电脑([!DNL Device 1])、智能手机([!DNL Device 2])和平板电脑([!DNL Device 3])。 但是，John会使用其设备搜索包交易的不同项目：

* 他用笔记本电脑搜索航班；
* 他用智能手机搜索酒店；
* 他用平板电脑搜索导游。

即使John未在上述所有三台设备上进行身份验证，也可以使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**&#x200B;规则，假设他是最后一个在所有三台设备上进行身份验证的人员，假日包提供程序也可以将这些设备与John的已验证配置文件相关联。

![最后设备图](assets/last-device-graph.png)

由于Audience Manager符合参与区段配置文件合并的每个设备配置文件的条件，因此所有三个设备配置文件都会被分段。 [!UICONTROL Profile Link Device Graph]允许Audience Manager查看所有三台设备的行为，并确定每台设备符合某个区段的资格条件，该区段没有单个设备配置文件单独符合该区段的资格条件。

此[!UICONTROL Profile Merge Rule]使营销人员能够根据用户活动而不是单个设备活动，向一人拥有的所有设备提供一致的体验。

![跨设备个性化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部设备图用例](external-graph-use-cases.md)
* [配置文件合并规则的一般用例](merge-rule-targeting-options.md)
* [配置文件合并规则常见问题解答](../../faq/faq-profile-merge.md)

