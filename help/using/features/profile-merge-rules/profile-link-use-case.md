---
description: Recommendations和使用案例，通过“用户档案链接”设备图表进行细分重定向和个性化细分资格认定。
seo-description: Recommendations和使用案例，通过“用户档案链接”设备图表进行细分重定向和个性化细分资格认定。
seo-title: 配置文件关联设备图用例
solution: Audience Manager
title: 配置文件关联设备图用例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 9%

---

# 配置文件关联设备图用例 {#profile-link-device-graph-use-cases}

Recommendations和使用案例，通过[!UICONTROL Profile Link Device Graph]进行细分重定向和个性化细分资格鉴定。

## 推荐 {#recommendations}

请考虑[!UICONTROL Profile Link]设备图表，了解以下活动:

* 在其数字资产中进行高级身份验证。 如果您有少量经过身份验证的用户，请使用[外部设备图表选项](merge-rule-definitions.md#device-options)。
* 需要准确定位已知受众。 [!UICONTROL Profile Link Device Graph]是使用第一方经身份验证的数据构建的。
* 实时目标其已验证和未验证状态中的已知受众。

![](assets/merge-rule-triangle2.png)

## 跨设备定位{#cross-device-personalization}

假设约翰拥有三款他经常用来搜索度假套餐的设备：他的笔记本电脑([!DNL Device 1])、智能手机([!DNL Device 2])和平板电脑([!DNL Device 3])。 但是，John使用他的设备来搜索包交易的不同项目：

* 他用笔记本电脑搜索航班；
* 他用智能手机搜索酒店；
* 他用平板电脑搜索导游。

即使John未在上述所有三台设备上进行身份验证，通过使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**&#x200B;规则，假定他是最后一个在所有三台设备上进行身份验证的人，假期包提供程序也可以将这些设备与John的已验证用户档案关联。

![最后设备图](assets/last-device-graph.png)

由于Audience Manager可以对参与用户档案合并的每个设备用户档案进行资格化，因此，所有三个设备用户档案都会被分段。 [!UICONTROL Profile Link Device Graph]允许Audience Manager查看所有三台设备的行为，并为每个设备确定一个没有单台设备用户档案自己有资格获得的区段。

此[!UICONTROL Profile Merge Rule]使营销人员能够根据用户活动而非单个设备活动，向由一人拥有的所有设备提供一致的体验。

![跨设备个性化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部设备图用例](external-graph-use-cases.md)
>* [配置文件合并规则的一般用例](merge-rule-targeting-options.md)
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

