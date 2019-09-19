---
description: 此报告返回在所选日期之前30天内至少实现10,000次的特征列表，在同一时间间隔内，在任一方向上的标准偏差均大于或等于1.7。 该报告可帮助您评估来自某个特征中独特用户的展示次数随时间的变化情况。
seo-description: 此报告返回在所选日期之前30天内至少实现10,000次的特征列表，在同一时间间隔内，在任一方向上的标准偏差均大于或等于1.7。 该报告可帮助您评估来自某个特征中独特用户的展示次数随时间的变化情况。
seo-title: 每日特征变化报告
solution: Audience Manager
title: 每日特征变化报告
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# 每日特征变化报告 {#daily-trait-variation-report}

此报告返回在所选日期之前30天内至少实现10,000次的特征列表，在同一时间间隔内，在任一方向上的标准偏差均大于或等于1.7。 该报告可帮助您评估来自某个特征中独特用户的展示次数随时间的变化情况。

>[!NOTE]
>
>Audience Manager中的“每日特征变化”报告遵循RBAC原则。 您只能根据您所属的 [RBAC用户组来查看您有权访问的数据源中的特征](/help/using/features/administration/administration-overview.md) 。

标准偏差测量与平均值（或平均／预期值）的偏差或偏差量。 标准偏差较低，表明数据点趋于与平均值非常接近。 高标准差表示数据点分布在大范围的值上。

![](assets/daily_trait_variation.png)

使用列 [!UICONTROL Date] 表为报表选择一个或多个日期。 在列表底部显示一个颜色编码的条形图，它以可视方式代表所有选定日期的所有特征的标准偏差范围。 黑色垂直线表示平均值。

中间列包含由和标识的特征 [!UICONTROL Trait ID] 列表 [!UICONTROL Trait Name]。 单击任何特征以访问一个弹出对话框，通过该对话框可以从以下选项中进行选择：

* **** 仅保留：从报表中删除所有其他特征，并仅显示此特征的数据。
* **** 排除：从报表中删除此特征并显示所有其他特征的数据。 您可以排除多个特征。
* **** 查看数据：允许您显示该行的数据。 您还可以将所有行作为文本文件下载。

该列 [!UICONTROL Standard Deviation] 显示彩色编码的条形图，它们显示所选间隔内每个特征的标准偏差。 红色条表示标准偏差为负的特征（数据点往往低于平均值）。 绿色条指示标准偏差为正的特征（数据点往往高于平均值）。 将鼠标悬停在任何栏上可显示一个弹出对话框，其中包含更多信息和选项以保留或排除该特征并查看更多信息。

报告底部显示的图标允许您以各种格式导出数据，还原对报告所做的任何更改（如排除特征），启用或禁用自动更新，并刷新报告的数据。 请参 [阅报表图标和说明的工具](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)。

## 用例 {#use-cases}

**示例1**:此报告在您具有具有高季节性级别的特征时非常有用。 例如，假设您的在线商店正在测试各种类型和价格的季节性促销活动。 您在中定义了以下特征 [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

假设您在12 [!UICONTROL Daily Trait Variation] 月20日运行报告，并注意到过去30天内上述特征有明显的正偏差。 这可能表明您的访客正在寻找您在季节性促销中提及的产品。 为了利用这一趋势，您随后可以投入更多精力，将特定产品类别的创意人员定位到感兴趣的访客。

**示例2**:此报告可以帮助您确定与标记问题或特征配置错误相关的定位异常。 假设您根据在线商店的类别定义了以下特征：

* `productPage == "smartphones"`

由于您的商店进行了重新配置，您将根据品牌名称将智能手机页面拆分为多个页面。 但是，您忘记更新中定义的特征 [!DNL Audience Manager]。

一个月后，您会运行报告并 [!UICONTROL Daily Trait Variation]`productPage == "smartphones"` 注意到该特征有很大的负偏差，尽管根据您的网站分析，您的访客数量已经增加。 根据此信息，您会意识到您尚未更新新产品页面 [!DNL Audience Manager] 中的特征，因此您需要创建以下特征：

* productPage == "samsung"
* productPage == "apple"
* productPage == "waubeit"

完成此操作后，您将看到受众符合新创建特征的资格。
