---
description: 有关产品和功能的常见问题。
keywords: audience manager cookie
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: 产品特性和功能常见问题解答
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 84%

---

# 产品特性和功能常见问题解答{#product-features-and-functions-faq}

有关产品和功能的常见问题。

 

<!-- 

faq_features_functions.xml

 -->

**我的组织 ID 是什么？如何查找该 ID？**

*`Organization ID`* 是一个唯一 ID，用于在 [!DNL Audience Manager] 和 [!DNL Adobe Experience Cloud] 中标识您的组织。组织 ID 包含一个由 24 个字符构成的字母数字字符串（区分大小写），且其后面跟有 [!UICONTROL @AdobeOrg]。

例如，*`Organization ID`* 应如下所示：`1FD6776A524453CC0A490D44@AdobeOrg`。

*`Organization ID`* 可由 Audience Manager [DIL](../dil/dil-overview.md) API、[Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) 及其他 [!DNL Experience Cloud] 解决方案使用。具有管理员权限的用户可在 [!DNL Adobe Admin Console] 上找到 *`Organization ID`*。请参阅[管理 - 用户管理常见问题解答](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

 

**我能否批量创建特征或目标？**

能。请参阅[批量管理工具](../reference/bulk-management-tools/bulk-management-intro.md)。

>[!NOTE]
>
>[!DNL Audience Manager] *不*&#x200B;支持 [!UICONTROL Bulk Management Tools] 工具。提供这些工具只是为了方便用户。要进行批量更改，建议您改用 [Audience Manager API](../api/api.md)。

 

**执行批量ID导出到目标时，缺少某些客户ID。 为什么会发生这种情况？**

当设备ID([AAM UUID](../reference/ids-in-aam.md))关联到多个CRM ID([DPUUID](../reference/ids-in-aam.md))，则仅导出最新的映射。 因此，您可能会看到导出的设备ID数量低于预期数量。

 

**[!DNL Audience Manager] 是否可以消除对第三方标记或像素的需求并缩短页面加载时间？**

如果 [!DNL Audience Manager] 已与第三方数据合作伙伴集成，则可以使用对 [!DNL Audience Manager] 发起的服务器到服务器 ID 调用来替换其像素和标记。在这种情况下，[!DNL Audience Manager] 将在我们第一次看到用户时触发单个 ID 调用，并将该信息与您的第三方合作伙伴同步。如此一来，便无需从每页进行多个像素调用。减少像素调用可以缩短页面加载时间。

 

**我订阅了一个数据信息源。该数据存储在何处？**

您的数据信息源及其包含的所有特征在 [!DNL Audience Manager] 中会显示为子文件夹和特征。转到 **[!UICONTROL Audience Data > Traits]** 并展开 [!UICONTROL 3rd-Party Data] 文件夹，可查看您的特征，或使用此数据创建区段和模型。

 

**什么是 [!UICONTROL Tag Insertion Manager (TIM)]？**

Audience Manager 之前使用 [!UICONTROL Tag Insertion Manager] (TIM) 创建和管理 [!UICONTROL data collection code (DIL)]。此功能已过时，最先由 [!UICONTROL Dynamic Tag Manager (DTM)] 取代，后来由 [!DNL Adobe Experience Platform Tags] 取代。有关更多信息，请参阅 [Adobe Experience Platform标记](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

 

**算法模型和特征推荐之间有何区别？我何时应使用算法模型？何时应使用特征推荐？**

**算法模型**

算法模型不仅可以找到最具影响力的特征，还可以根据这些特征对用户进行评分，并为每个用户分配一个得分。然后，便可以通过创建算法特征来定位用户。借助特征生成器中的精度和范围控件，您可以指定要定位具有影响力特征的用户中的哪些特定用户。

通过算法模型，您能够选择不同精度级别的用户，并在 Audience Lab 中测试哪组用户的转化率更高。有关详细用例，请参阅[在 Audience Lab 中比较模型](../features/audience-lab/audience-lab-use-cases.md#compare-models)。

在算法模型中，模型每 8 天运行一次，并会刷新符合算法特征的用户。

**特征推荐**

特征推荐是一种快速了解与您在区段中使用的特征相似的其他特征的方法。

在以下情况下，您应使用特征推荐：

* 构建区段时需要快速获取信息；
* 要将区段用于短期促销活动，或者希望快速抑制转化的受众；
* 想要最大化范围。

 

**Adobe Analytics 区段与 Audience Manager 区段之间是否有任何区别？**

是，有关两者之间区别的深入说明，请参阅[了解 Analytics 和 Audience Manager 中的区段](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)。
