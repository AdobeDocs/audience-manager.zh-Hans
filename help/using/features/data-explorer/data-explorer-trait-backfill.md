---
description: 回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-description: 回填特征实现以捕获历史受众并避免在特征创建日期之前丢失相关数据。
seo-title: 回填特征实现
title: 回填特征实现
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Backfill Trait Realizations {#backfill-trait-realizations}

Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.

[!UICONTROL Data Explorer Trait Backfill] is a premium capability that enhances the Audience Manager experience by unlocking additional use cases. Backfill requires additional processing power and is available to all Audience Manager customers at an incremental cost. Please contact your Adobe sales representative for additional details.

When you create traits from unused signals, you can choose to backfill the trait realizations over a specific period of time. [!DNL Audience Manager] captures the historical data about audiences that qualify for the new trait and stores them on the corresponding profile. 您可以在特 **[!UICONTROL Backfill Options]** 征构建 [!UICONTROL Trait Expression] 器的部分 **[中看到](../../features/traits/about-trait-builder.md)**。

>[!NOTE]
>
>您可以回填基于规则和已载入特征的特征实现。

下面介绍如何回填特征实现：

1. 转至并 [!UICONTROL Audience Data > Signals > Search] 运行“信号搜索”或使用“信号 [控制板](../../features/data-explorer/data-explorer-signals-dashboard.md) ”来识别要用于新特征的信号。
1. 根据所需信号创建新特征。
1. 使用部 **[!UICONTROL Backfill Options]** 分中 **[!UICONTROL Trait Expression]** 的选项选择要回填特征实现的时间间隔。 预定义的回填间隔包括1、7、14和30天。 您还可以选择最多30天的自定义日期范围。

   ![特征回填](assets/signals-trait-backfill.png)

1. （可选）单 **[!UICONTROL Estimate Realizations]** 击该部 **[!UICONTROL Estimated Trait Realizations]** 分可查看最近7天内回填特 [!UICONTROL Unique Trait Realizations] 征 [!UICONTROL Total Trait Population] 的估计值和值。

   ![估计特征实现](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特征回填和估计对于使用以下运算符的表达式的特征不可用：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 创建特征。

创建完特征后，您将看到其回填的实现包含在实现统计信息中。

Watch the video below for a video walkthrough of how to backfill traits.

[!VIDEO](https://video.tv.adobe.com/v/25169/?captions=chi_hans)

## Trait Backfilling Latency {#trait-backfilling-latency}

Newly created traits start capturing audiences two to three hours after creation. However, due to the large volume of data that  performs on a daily basis, the backfilled population is not immediately reflected in the  and  graphs.[!DNL Audience Manager][!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population]

Audience Manager updates the  with the backfilled population within 48 hours from trait creation.[!UICONTROL Trait Graph]

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] allows you to backfill up to 50 traits per month, with the backfill counter being reset on the 1 day of each month.

>[!NOTE]
>
>Trait backfilling quota does not carry over from previous months. E.g., if you backfill 30 traits this month, the trait backfill quota for the next month is reset to 50, not 70.

## 对报告的影响 {#reporting-impact}

回填的特征实现反映在和 [!UICONTROL Unique Trait Realizations] 度量 [!UICONTROL Total Trait Population] 中，将历史信 [!DNL Audience Manager] 号转换为特征实现。

However, the , , and  are not updated retroactively with historical metrics backfilled before the trait creation date.[!UICONTROL Trait Graph][!UICONTROL General Reports][!UICONTROL Trend Reports]