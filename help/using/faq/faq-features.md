---
description: 常见产品和功能相关问题和问题。
keywords: 受众经理cookies
seo-description: 常见产品和功能相关问题和问题。
seo-title: 产品功能和功能常见问题解答
solution: Audience Manager
title: 产品功能和功能常见问题解答
uuid: da5f5089-24a8-4455-88a6-eb62 d83939 d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

常见产品和功能相关问题和问题。

<br> 

<!-- 

faq_features_functions.xml

 -->

**我的组织ID是什么？我如何找到它？**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

For example, an *`Organization ID`* looks like this: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**我是否可以批量创建特征或目标？**

能。See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] 不 ** 支持这些工具 [!DNL Audience Manager]。它们为方便起见而提供，只是出于好意。For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**能否[!DNL Audience Manager]减少对第三方标签或像素的需求并提高页面加载时间？**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. 这消除了从每个页面调用多个像素的需求。减少像素调用可提高页面加载时间。

<br> 

**我订阅了数据源。Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**什么是[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**算法模型与特征推荐之间有何区别？When should I use each of them?**

**算法模型**

算法模型不仅找到最有影响力的特征，而且还根据这些特征给用户评分，为每个用户分配一个单独的分数。然后创建算法特征以定位用户。凭借Travical Builder中的准确性和触及力控制，您可以指定所有具有影响力特征的用户。

算法模型使您能够选择不同准确性级别的用户，并在Audience Lab中测试用户组的转换效果。See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

在Algorithmic Model中，该模型每隔天运行一次，并refre符合算法特征的用户。

**特征推荐**

Travical Recommendations是一种快速获取其他特征的方法，它类似于您在细分中使用的其他特征。

在以下情况下，您应使用特征推荐：

* 您需要在构建区段时快速洞察；
* 您正在将细分用于简短营销活动，或者在您希望快速抑制转化受众时使用细分；
* 您正在尝试最大化覆盖面。

<br> 

**Adobe Analytics和Audience Manager细分之间是否存在差异？**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
