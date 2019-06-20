---
description: 回填特征可用于捕获历史受众，避免在特征创建日期之前丢失相关数据。
seo-description: 回填特征可用于捕获历史受众，避免在特征创建日期之前丢失相关数据。
seo-title: 回填特征真实性
title: 回填特征真实性
uuid: 8b0ef4e6-d16 a-4d1 d-94f1-b84 eeffffa9 a5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

回填特征可用于捕获历史受众，避免在特征创建日期之前丢失相关数据。

[!UICONTROL Data Explorer Trait Backfill] 是一项高级功能，通过解锁其他用例增强Audience Manager体验。后台填写需要额外的处理能力，所有Audience Manager客户都可以以增量成本购买。有关更多详细信息，请与您的Adobe销售代表联系。

当您从未使用的信号创建特征时，您可以选择在特定时间段内回填特征真实性。[!DNL Audience Manager] 捕获符合新特性的受众的历史数据，并将其存储在相应的档案中。You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>您可以对基于规则的属性和载入的特征进行回填。

下面介绍如何回填特征真实性：

1. Go to [!UICONTROL Audience Data > Signals > Search] amd run a Signals Search or use the [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) to identify the signals to use in the new trait.
1. 根据所需的信号创建新的特征。
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. 预定义的预填时间间隔包括1、7、14和30天。您还可以选择最多30天的自定义日期范围。
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >特征回填和估计不适用于使用以下运算符的表达式：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 创建特征。

创建特征后，您将看到实现统计数据中包含的预填字段。

## Trait Backfilling Latency {#trait-backfilling-latency}

新创建的特征在创建后的两到三个小时开始捕获受众。However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 允许您每月回填50个特征，并且在每个月的的的前一天重置回填计数器。

>[!NOTE]
>
>特征回填配额不会从过去几个月结转。例如，如果您本月回填30种特征，则特征的特征回填配额将重置为50，而非70。

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.