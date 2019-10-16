---
description: 通过“配置文件链接”设备图表，为细分重定向和个性化细分资格提供推荐和使用案例。
seo-description: 通过“配置文件链接”设备图表，为细分重定向和个性化细分资格提供推荐和使用案例。
seo-title: 配置文件链接设备图形使用案例
solution: Audience Manager
title: 配置文件链接设备图形使用案例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 配置文件链接设备图形使用案例 {#profile-link-device-graph-use-cases}

推荐和使用案例，用于细分重定向和个性化细分资格 [!UICONTROL Profile Link Device Graph]。

## 推荐 {#recommendations}

考虑以下 [!UICONTROL Profile Link] 营销活动的设备图：

* 在其数字资产中进行高级身份验证。 如果您 [有少量经过身份验证的用户](merge-rule-definitions.md#device-options) ，请使用外部设备图形选项。
* 需要准确定位已知受众。 使用 [!UICONTROL Profile Link Device Graph] 第一方的实名数据构建。
* 实时在其已验证和未验证状态中定位已知受众。

![](assets/merge-rule-triangle2.png)

## 跨设备定位 {#cross-device-personalization}

假设约翰拥有三款他经常用来搜索节日套餐的设备：他的笔记本[!DNL Device 1]电脑、智能手机[!DNL Device 2]和平板电脑[!DNL Device 3]。 但是，John使用他的设备搜索包交易的不同项目：

* 他用笔记本电脑搜索航班；
* 他用智能手机搜索酒店；
* 他用平板电脑搜索导游。

即使John未在上述所有三台设备上验证身份，通过使用 **[!UICONTROL Last Authenticated Profiles]****[!UICONTROL Profile Link Device Graph]** +规则，假定他是在所有三台设备上验证的最后一个人，假期包提供者也可以将这些设备关联到John的已验证配置文件。

![last-device-graph](assets/last-device-graph.png)

由于Audience Manager可确定参与区段的配置文件合并的每个设备配置文件，因此三个设备配置文件都会被分段。 Audience manager可 [!UICONTROL Profile Link Device Graph] 以查看所有三台设备的行为，并为每个设备确定一个没有单台设备配置文件单独获得的区段的资格。

这使 [!UICONTROL Profile Merge Rule] 营销人员能够根据用户活动而非单个设备活动，向由一人拥有的所有设备提供一致的体验。

![跨设备个性化](assets/cross-device-personalization.png)

>[!MORE_LIKE_THIS]
>
>* [外部设备图形使用案例](external-graph-use-cases.md)
>* [配置文件合并规则的一般用例](merge-rule-targeting-options.md)
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

