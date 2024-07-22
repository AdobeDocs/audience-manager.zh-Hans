---
description: 此报表返回的特征列表在选定日期之前的30天内已实现至少10,000次，并且在同一时间间隔内的任一方向上的标准偏差大于或等于1.7。 报表可帮助您评估某个特征中独特用户的展示次数在一段时间内的波动情况。
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: 每日特征变化报表
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# 每日特征变化报表 {#daily-trait-variation-report}

此报表返回的特征列表在选定日期之前的30天内已实现至少10,000次，并且在同一时间间隔内的任一方向上的标准偏差大于或等于1.7。 报表可帮助您评估某个特征中独特用户的展示次数在一段时间内的波动情况。

>[!NOTE]
>
>Audience Manager中的每日特征变化报告遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)，查看您有权访问的数据源中的特征。

标准偏差测量与平均值（或平均值/预期值）之间的偏差或分散程度。 较低的标准偏差表示数据点往往非常接近平均值。 高标准偏差表示数据点分布于大量值中。

![](assets/daily_trait_variation.png)

使用[!UICONTROL Date]列表为您的报告选择一个或多个日期。 以颜色编码的条形图显示在列表底部，该图表以可视化形式表示所有选定日期中所有特征的标准偏差范围。 黑色的垂直线表示平均值。

中间列包含由[!UICONTROL Trait ID]和[!UICONTROL Trait Name]标识的特征列表。 单击任意特征可访问弹出对话框，您可以从以下选项中进行选择：

* **仅保留：**&#x200B;从报表中删除所有其他特征，并仅显示此特征的数据。
* **排除：**&#x200B;从报表中删除此特征并显示所有其他特征的数据。 您可以排除多个特征。
* **查看数据：**&#x200B;允许您显示该行的数据。 您还可以将所有行下载为文本文件。

[!UICONTROL Standard Deviation]列显示颜色编码的条形图，这些条形图显示所选间隔内每个特征的标准偏差。 红色条表示具有负标准偏差（数据点往往低于平均值）的特征。 绿色条表示具有正标准偏差（数据点倾向于高于平均值）的特征。 将鼠标悬停在任何栏上会显示一个弹出对话框，其中包含更多信息和用于保留或排除该特征并查看更多信息的选项。

图标显示在报表底部，通过图标，可导出各种格式的数据，还原可能对报表所做的任何更改（例如排除特征），启用或禁用自动更新，以及刷新报表数据。 请参阅[说明的报告图标和工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)。

## 用例 {#use-cases}

**示例#1**：在您具有季节性级别较高的特征的情况下，此报表可能非常有用。 例如，假设您的在线商店正在测试各种类型和价格的季节性促销。 您在[!DNL Audience Manager]中定义了以下特征：

* `productPage == "December Promotion"`
* `price > "500"`

假设您在12月20日运行了[!UICONTROL Daily Trait Variation]报表，并且您注意到过去30天内上述特征出现了稳定的正偏差。 这可能表明您的访客正在寻找您的季节性促销活动中提到的产品。 要利用此趋势，您可以投入更多精力针对特定产品类别的创意内容，定位对创意内容感兴趣的访客。

**示例#2**：此报表可帮助您识别与标记问题或特征配置错误相关的定位异常。 假设您已根据在线商店的类别定义了以下特征：

* `productPage == "smartphones"`

由于商店的重新配置，您将根据品牌名称将智能手机页面拆分为多个页面。 但是，您忘记更新[!DNL Audience Manager]中定义的特征。

一个月后，您运行了[!UICONTROL Daily Trait Variation]报表，并根据网站分析发现，尽管您的访客数量有所增加，但`productPage == "smartphones"`特征仍存在较大的负偏差。 根据此信息，您意识到尚未为新的产品页面更新[!DNL Audience Manager]中的特征，因此您需要创建以下特征：

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

执行此操作后，您将看到受众符合新创建特征的条件。
