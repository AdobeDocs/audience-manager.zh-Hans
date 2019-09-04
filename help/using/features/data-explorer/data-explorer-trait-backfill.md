---
description: 回填特征可用于捕获历史受众，避免在特征创建日期之前丢失相关数据。
seo-description: 回填特征可用于捕获历史受众，避免在特征创建日期之前丢失相关数据。
seo-title: 回填特征真实性
title: 回填特征真实性
uuid: 8b0ef4e6-d16 a-4d1 d-94f1-b84 eeffffa9 a5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# 回填特征真实性 {#backfill-trait-realizations}

回填特征可用于捕获历史受众，避免在特征创建日期之前丢失相关数据。

[!UICONTROL Data Explorer Trait Backfill] 是一项高级功能，通过解锁其他用例增强Audience Manager体验。后台填写需要额外的处理能力，所有Audience Manager客户都可以以增量成本购买。有关更多详细信息，请与您的Adobe销售代表联系。

当您从未使用的信号创建特征时，您可以选择在特定时间段内回填特征真实性。[!DNL Audience Manager] 捕获符合新特性的受众的历史数据，并将其存储在相应的档案中。您可以看到 **[!UICONTROL Backfill Options]** 特征生成器 [!UICONTROL Trait Expression] 的部分 **[](../../features/traits/about-trait-builder.md)**&#x200B;中的内容。

>[!NOTE]
>
>您可以对基于规则的属性和载入的特征进行回填。

下面介绍如何回填特征真实性：

1. 转到 [!UICONTROL Audience Data > Signals > Search] amd运行信号搜索或使用 [信号控制板](../../features/data-explorer/data-explorer-signals-dashboard.md) 识别要在新特征中使用的信号。
1. 根据所需的信号创建新的特征。
1. 使用 **[!UICONTROL Backfill Options]****[!UICONTROL Trait Expression]** 部分中的部分选择您要为其回填特征真实性的时间间隔。预定义的预填时间间隔包括1、7、14和30天。您还可以选择最多30天的自定义日期范围。

   ![特征-背景填充](assets/signals-trait-backfill.png)

1. (可选)单击 **[!UICONTROL Estimate Realizations]****[!UICONTROL Estimated Trait Realizations]** 部分，查看过去天内回填特征的估计 [!UICONTROL Unique Trait Realizations] 值和 [!UICONTROL Total Trait Population] 值。

   ![估计特征-真实性](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >特征回填和估计不适用于使用以下运算符的表达式：
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 创建特征。

创建特征后，您将看到实现统计数据中包含的预填字段。

## 特征回填延迟 {#trait-backfilling-latency}

新创建的特征在创建后的两到三个小时开始捕获受众。然而，由于每天执行的大量数据都 [!DNL Audience Manager] 很大，因此填充的人群并不会立即反映在图形和 [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] 图形中。

Audience [!UICONTROL Trait Graph] Manager可在48小时内利用回填人群更新回填人群。

## 特征回填限制 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 允许您每月回填50个特征，并且在每个月的的的前一天重置回填计数器。

>[!NOTE]
>
>特征回填配额不会从过去几个月结转。例如，如果您本月回填30种特征，则特征的特征回填配额将重置为50，而非70。

## 对报告的影响 {#reporting-impact}

有回填特征的特性反映在和 [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population] 指标中，这 [!DNL Audience Manager] 将历史信号转变为特征现实。

但是，在 [!UICONTROL Trait Graph][!UICONTROL General Reports]特征 [!UICONTROL Trend Reports] 创建日期之前，我们会逆向更新历史指标并进行逆向更新。