---
description: 常见产品和功能相关问题。
keywords: audience manager cookies
seo-description: 常见产品和功能相关问题。
seo-title: 产品特性和功能常见问题解答
solution: Audience Manager
title: 产品特性和功能常见问题解答
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# 产品特性和功能常见问题解答{#product-features-and-functions-faq}

常见产品和功能相关问题。

<br> 

<!-- 

faq_features_functions.xml

 -->

**我的组织ID是什么？如何找到它？**

该 *`Organization ID`* 是一个唯一ID，用于标识您的组织 [!DNL Audience Manager] 与 [!DNL Adobe Experience Cloud]。 它由区分大小写的24个字符的字母数字字符串后跟 [!UICONTROL @AdobeOrg]。

例如，一个 *`Organization ID`* 如下所示： `1FD6776A524453CC0A490D44@AdobeOrg`.

受众 *`Organization ID`* 经理的DIL API、 [Adobe](../dil/dil-overview.md) Experience Platform Identity Service和其 [他解决方案均使用](https://docs.adobe.com/content/help/en/id-service/using/home.html)该 [!DNL Experience Cloud] 服务。 具有管理员权限的用户可在 *`Organization ID`* 上找到 [!DNL Adobe Admin Console]。 请参阅管 [理——用户管理常见问题解答](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)。

<br> 

**我是否可以批量创建特征或目标？**

能。请参 [阅批量管理工具](../reference/bulk-management-tools/bulk-management-intro.md)。

>[!NOTE]
>
>工 [!UICONTROL Bulk Management Tools] 具 *不受支持* 。 [!DNL Audience Manager]提供这些服务是为了方便，仅出于礼貌。 对于批量更改，建议您改 [用受众管理器](../api/api.md) API。

<br> 

**是[!DNL Audience Manager]否可以减少对第三方标记或像素的需求并缩短页面加载时间？**

如 [!DNL Audience Manager] 果已与第三方数据合作伙伴集成，您可以使用服务器到服务器ID调用替换其像素和标记 [!DNL Audience Manager]。 在这种情况下， [!DNL Audience Manager] 当我们第一次看到用户时将触发单个ID调用，并将该信息与您的第三方合作伙伴同步。 这样，无需从每页进行多像素调用。 减少像素调用可缩短页面加载时间。

<br> 

**我订阅了一个数据源。 数据存储在哪里？**

您的数据源和信息源中包含的所有特征在中显示为子文件夹和特征 [!DNL Audience Manager]。 转到并 **[!UICONTROL Audience Data > Traits]** 展开文件 [!UICONTROL 3rd-Party Data] 夹以视图您的特征或使用此数据创建区段和模型。

<br> 

**什么是[!UICONTROL Tag Insertion Manager (TIM)]?**

受众管理 [!UICONTROL Tag Insertion Manager] 器使用(TIM)创建和管 [!UICONTROL data collection code (DIL)]理。 This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Experience Platform Launch]. For more information, see [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

<br> 

**算法模型和特质推荐之间有何差异？ 我何时应使用每个？**

**算法模型**

算法模型不仅可以找到最具影响力的特征，还可以根据这些特征对用户进行评分，并为每个用户分配一个个人得分。 然后创建算法特征来目标用户。 借助特征生成器中的准确性和范围控件，您可以指定所有具有要目标的有影响力特征的用户中的哪些用户。

Algorithmic Models使您能够选择不同精度级别的用户，并在受众实验室测试哪组用户转化效果更好。 请参阅受众实验室中的 [比较模型中的详细用例](../features/audience-lab/audience-lab-use-cases.md#compare-models)。

在“算法模型”中，该模型每8天运行一次，并刷新符合算法特征的用户。

**特征推荐**

特征推荐是一种快速方法，用于了解与您在区段中使用的特征相似的其他特征。

在以下情况下，您应使用特征推荐：

* 在构建细分时需要快速洞察；
* 您正在将区段用于短活动，或者当您希望快速抑制转换受众时；
* 你试图将触及力最大化。

<br> 

**Adobe Analytics和受众管理器细分之间是否有差异？**

是，请阅读了 [解分析和受众管理器中的](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) “区段”，以详细描述差异。
