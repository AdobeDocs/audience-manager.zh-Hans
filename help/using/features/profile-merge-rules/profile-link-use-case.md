---
description: 通过用户档案链接设备图表，为细分重定向和个性化细分资格提供推荐和使用案例。
seo-description: 通过用户档案链接设备图表，为细分重定向和个性化细分资格提供推荐和使用案例。
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

推荐和使用案例，用于进行细分重新定位和个性化的细分资格 [!UICONTROL Profile Link Device Graph]。

## 推荐 {#recommendations}

考虑以下 [!UICONTROL Profile Link] 活动的设备图：

* 在其数字资产中进行高级身份验证。 如果 [用户数量较少](merge-rule-definitions.md#device-options) ，请使用外部设备图形选项。
* 需要准确定位已知受众。 使用 [!UICONTROL Profile Link Device Graph] 第一方、经过身份验证的数据构建。
* 实时目标其已验证和未验证状态中的已知受众。

![](assets/merge-rule-triangle2.png)

## 跨设备定位 {#cross-device-personalization}

假设约翰拥有三款他经常用来搜索假日套餐的设备： 他的笔记本[!DNL Device 1]电脑()、智[!DNL Device 2]能手机()和平板电脑([!DNL Device 3])。 但是，John使用他的设备来搜索包交易的不同项目：

* 他用笔记本电脑搜索航班；
* 他用智能手机搜索酒店；
* 他用平板电脑搜索导游。

即使John未在上述所有三台设备上验证身份，通过使用 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** 规则，假设John是所有三台设备上最后一个验证人，假日包提供商也可以将这些设备关联到John的验证用户档案。

![最后设备图](assets/last-device-graph.png)

由于Audience Manager符合参与用户档案合并的每个设备用户档案的条件，所以所有三个设备用户档案都被分段。 Audience Manager [!UICONTROL Profile Link Device Graph] 可以查看所有三台设备的行为，并为每个设备确定一个没有单台设备用户档案自己有资格获得的细分。

这使 [!UICONTROL Profile Merge Rule] 营销人员能够根据用户活动而非单个设备活动，向由一人拥有的所有设备提供一致的体验。

![跨设备个性化](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [外部设备图用例](external-graph-use-cases.md)
>* [配置文件合并规则的一般用例](merge-rule-targeting-options.md)
>* [用户档案合并规则常见问题解答](../../faq/faq-profile-merge.md)

