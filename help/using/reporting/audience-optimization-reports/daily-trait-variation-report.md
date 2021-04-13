---
description: 此报表返回在选定日期之前30天内至少实现10,000次的特征列表，并在同一时间间隔内，在任一方向上的标准偏差大于或等于1.7。 该报表可帮助您评估特征中独特用户的展示次数随时间的变化。
seo-description: 此报表返回在选定日期之前30天内至少实现10,000次的特征列表，并在同一时间间隔内，在任一方向上的标准偏差大于或等于1.7。 该报表可帮助您评估特征中独特用户的展示次数随时间的变化。
seo-title: 每日特征变化报表
solution: Audience Manager
title: 每日特征变化报表
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization 报表
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---

# 每日特征变化报表 {#daily-trait-variation-report}

此报表返回在选定日期之前30天内至少实现10,000次的特征列表，并在同一时间间隔内，在任一方向上的标准偏差大于或等于1.7。 该报表可帮助您评估特征中独特用户的展示次数随时间的变化。

>[!NOTE]
>
>Audience Manager中的“每日特征变化”报表遵循RBAC原则。 您只能根据您所属的[RBAC用户组](/help/using/features/administration/administration-overview.md)查看您有权访问的数据源中的特征。

标准偏差测量与平均值（或平均/预期值）的偏差或偏差量。 标准差较低，表明数据点趋近于平均值。 高标准偏差表示数据点分布在大范围值中。

![](assets/daily_trait_variation.png)

使用[!UICONTROL Date]列表为报表选择一个或多个日期。 列表底部会显示一个颜色编码条形图，它以可视方式代表所有选定日期中所有特征的标准偏差范围。 黑色垂直线表示平均值。

中间列包含由[!UICONTROL Trait ID]和[!UICONTROL Trait Name]标识的特征列表。 单击任何特征可访问一个弹出对话框，您可以从以下选项中进行选择：

* **仅保留：** 从报表中删除所有其他特征并仅显示此特征的数据。
* **排除：** 从报表中删除此特征并显示所有其他特征的数据。您可以排除多个特征。
* **视图数** 据：用于显示该行的数据。您还可以将所有行作为文本文件下载。

[!UICONTROL Standard Deviation]列显示彩色编码的条形图，显示所选间隔内每个特征的标准差。 红条表示标准偏差为负的特征（数据点往往低于平均值）。 绿色条指示具有正标准差的特征（数据点往往高于平均值）。 将鼠标悬停在任意栏上可显示一个弹出对话框，其中包含更多信息和选项以保留或排除该特征并视图更多信息。

报表底部显示图标，可让您以各种格式导出数据、还原对报表所做的任何更改（如排除特征）、启用或禁用自动更新以及刷新报表数据。 请参阅[报表图标和说明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)。

## 用例 {#use-cases}

**示例1**:此报表在您具有具有高季节性级别的特征时非常有用。例如，假设您的在线商店正在测试各种类型和价格的季节性促销活动。 您在[!DNL Audience Manager]中定义了以下特征：

* `productPage == "December Promotion"`
* `price > "500"`

假设您在12月20日运行[!UICONTROL Daily Trait Variation]报表，并注意到过去30天内上述特征存在明显的正偏差。 这可能表明您的访客正在寻找您在季节性促销中提及的产品。 为了利用这一趋势，您可以投入更多精力将特定产品类别的创意定位到对其感兴趣的访客。

**示例2**:此报告可以帮助您确定与标记问题或特征错误配置相关的定位异常。想象一下，您根据在线商店的类别定义了以下特征：

* `productPage == "smartphones"`

由于您的商店的重新配置，您将根据品牌名称将智能手机页面拆分为多个页面。 但是，您忘记更新在[!DNL Audience Manager]中定义的特征。

一个月后，您会运行[!UICONTROL Daily Trait Variation]报表并注意到`productPage == "smartphones"`特征上存在大的负偏差，但根据您的网站分析，您的访客数已增加。 根据此信息，您意识到您尚未更新新产品页面的[!DNL Audience Manager]中的特征，因此您需要创建以下特征：

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;waewi&quot;

执行此操作后，您将看到受众符合新创建特征的资格。
