---
description: 常见产品和功能相关问题和问题。
keywords: 受众管理器cookie
seo-description: 常见产品和功能相关问题和问题。
seo-title: 产品特性和功能常见问题解答
solution: Audience Manager
title: 产品特性和功能常见问题解答
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 产品特性和功能常见问题解答{#product-features-and-functions-faq}

常见产品和功能相关问题和问题。

<br> 

<!-- 

faq_features_functions.xml

 -->

**我的组织ID是什么？如何找到它？**

该ID *`Organization ID`* 是一个唯一的ID，用于标识您的组织与 [!DNL Audience Manager] 您的组织 [!DNL Adobe Experience Cloud]。 它由区分大小写的24个字符的字母数字字符串后跟 [!UICONTROL @AdobeOrg]。

例如，一个 *`Organization ID`* 类似于： `1FD6776A524453CC0A490D44@AdobeOrg`.

Audience Manager *`Organization ID`* 的 [DIL](../dil/dil-overview.md) API、 [Experience Cloud ID服务和其他解决方案都使用它](https://marketing.adobe.com/resources/help/en_US/mcvid/)[!DNL Experience Cloud] 。 具有管理员权限的用户可以在上 *`Organization ID`* 找到该 [!DNL Adobe Admin Console]项。 请参阅管 [理——用户管理常见问题解答](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)。

<br> 

**我是否可以批量创建特征或目标？**

能。请参 [阅批量管理工具](../reference/bulk-management-tools/bulk-management-intro.md)。

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支 *持工具* 。 [!DNL Audience Manager]提供这些服务是为了方便和礼貌。 对于批量更改，我们建议您改用 [Audience Manager API](../api/api.md) 。

<br> 

**是[!DNL Audience Manager]否可以减少对第三方标记或像素的需求并缩短页面加载时间？**

如果 [!DNL Audience Manager] 已与第三方数据合作伙伴集成，您可以用服务器到服务器ID调用替换其像素和标记 [!DNL Audience Manager]。 在这种情况下， [!DNL Audience Manager] 当我们第一次看到用户时将触发单个ID调用，并将该信息与您的第三方合作伙伴同步。 这样，无需从每页进行多像素调用。 减少像素调用可缩短页面加载时间。

<br> 

**我订阅了一个数据源。 数据存储在哪里？**

您的数据源和源中包含的所有特征显示为中的子文件夹和特征 [!DNL Audience Manager]。 转到并展 **[!UICONTROL Audience Data > Traits]** 开文件夹，查 [!UICONTROL 3rd-Party Data] 看您的特征，或使用这些数据创建区段和模型。

<br> 

**什么是[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager使用 [!UICONTROL Tag Insertion Manager] (TIM)来创建和管理 [!UICONTROL data collection code (DIL)]。 This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. 有关详细信息，请参 [阅Adobe Launch](https://docs.adobelaunch.com/) 和 [动态标签管理](https://marketing.adobe.com/resources/help/en_US/dtm/)。

<br> 

**算法模型和特征推荐之间有何区别？ 我何时应该使用每个？**

**算法模型**

算法模型不仅可以找到最具影响力的特征，而且可以根据这些特征对用户进行评分，并为每个用户分配一个单独的得分。 然后，您创建算法特征来定位用户。 借助Trait Builder中的准确性和范围控制，您可以指定所有具有要定位的有影响力的特征的用户中的哪些用户。

Algorithmic Models使您能够选择不同准确度级别的用户，并在Audience lab中测试哪组用户转化效果更好。 请参阅Audience lab中的比较模 [型中的详细用例](../features/audience-lab/audience-lab-use-cases.md#compare-models)。

在“算法模型”中，该模型每8天运行一次，并刷新符合算法特征的用户。

**特征推荐**

特征推荐是一种快速获取其他特征洞察的方法，这些特征与您在区段中使用的特征相似。

在以下情况下，您应使用特征推荐：

* 在构建细分时，您需要快速洞察；
* 您使用细分进行简短的营销活动，或者您希望快速抑制转化受众；
* 您正在尝试将触及力最大化。

<br> 

**Adobe Analytics和Audience manager细分之间有何区别？**

是，请阅读了 [解Analytics和Audience manager中的细分](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) ，详细了解差异。
