---
description: Recommendations，使用案例通过用户档案链接设备图表进行细分重新定位和个性化细分资格。
seo-description: Recommendations，使用案例通过用户档案链接设备图表进行细分重新定位和个性化细分资格。
seo-title: 配置文件关联设备图用例
solution: Audience Manager
title: 配置文件关联设备图用例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 9%

---


# 配置文件关联设备图用例 {#profile-link-device-graph-use-cases}

Recommendations，使用案例进行细分重定位，并通过[!UICONTROL Profile Link Device Graph]获得个性化细分资格。

## 推荐 {#recommendations}

请考虑[!UICONTROL Profile Link]设备图表，以了解以下活动:

* 在其数字资产中进行高级身份验证。 如果您有少量经过身份验证的用户，请使用[外部设备图形选项](merge-rule-definitions.md#device-options)。
* 需要准确定位已知受众。 [!UICONTROL Profile Link Device Graph]是使用第一方、经过身份验证的数据构建的。
* 实时目标其已验证和未验证状态中的已知受众。

![](assets/merge-rule-triangle2.png)

## 跨设备定位{#cross-device-personalization}

假设约翰拥有三款他经常用来搜索假日套餐的设备：他的笔记本电脑([!DNL Device 1])、智能手机([!DNL Device 2])和平板电脑([!DNL Device 3])。 但是，John使用他的设备来搜索包交易的不同项目：

* 他用笔记本电脑搜索航班；
* 他用智能手机搜索酒店；
* 他用平板电脑搜索导游。

即使John未在上述所有三台设备上进行身份验证，通过使用&#x200B;**[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]**&#x200B;规则，假设他是最后一个在所有三台设备上进行身份验证的人，假日包提供程序也可以将这些设备关联到John的已验证用户档案。

![最后设备图](assets/last-device-graph.png)

由于Audience Manager符合参与用户档案合并的每个设备用户档案的条件，所以所有三个设备用户档案都被分段。 [!UICONTROL Profile Link Device Graph]允许Audience Manager查看所有三台设备的行为，并为每个设备确定一个没有单台设备用户档案自己有资格获得的区段。

此[!UICONTROL Profile Merge Rule]使营销人员能够根据用户活动而非单个设备活动，向由一人拥有的所有设备提供一致的体验。

![跨设备个性化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部设备图用例](external-graph-use-cases.md)
>* [配置文件合并规则的一般用例](merge-rule-targeting-options.md)
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

