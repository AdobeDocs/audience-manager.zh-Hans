---
description: 个人特征的详细信息页面提供了以下信息概述：特征名称、ID、性能指标、定义特征的表达式、它属于的区段以及特征审计日志。要查看这些详细信息，请转到“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-description: 个人特征的详细信息页面提供了以下信息概述：特征名称、ID、性能指标、定义特征的表达式、它属于的区段以及特征审计日志。要查看这些详细信息，请转到“受众数据”>“特征”，然后单击要处理的特征的名称。
seo-title: 特征详细信息页面
solution: Audience Manager
title: 特征详细信息页面
uuid: 23301376-c1 cc-4778-b8 c4-9831f6739 db9
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Trait Details Page {#trait-details-page}

个人特征的详细信息页面提供了以下信息概述：特征名称、ID、性能指标、定义特征的表达式、它属于的区段以及特征审计日志。To vew these details, go to [!UICONTROL Audience Data > Traits] and click the name of the trait you want to work with.

## 基本信息 {#basics}

[!UICONTROL Basic Information] 该部分显示了构建特征时完成的必填字段和可选字段的详细信息。其中包括特征类型、特征ID、描述、数据源和其他元数据等内容。这些详细信息因特征类型(文件夹、载入或基于规则)而异。

![](assets/basicInfo.png)

## Trait Graph {#trait-graph}

The [!UICONTROL Trait Graph] provides at-a-glance performance metrics for your selected trait. 将光标停留在趋势线上，可查看所选特征的其他数据。

[!UICONTROL Unique Trait Realizations] 表示在给定时间段内将此特征添加到其配置文件的唯一用户计数。The [!UICONTROL Total Trait Population] indicates the number of unique users currently qualified for this trait.

* 对于基于规则的特征，特征资格符合实时条件，因为用户可以在浏览器中获得特征。
* For onboarded traits, trait qualification happens after an inbound file is processed, i.e. the inbound file is [fed into Audience Manager](../../faq/faq-inbound-data-ingestion.md) and that is when the trait qualification happens.
* **独特特征真实性**：在给定时间段内将此特征添加到其配置文件的唯一用户计数。
* **特征总数**：当前符合此特征的唯一用户的数量。

![](assets/traitGraph.png)

## Trait Expression {#trait-expression}

[!UICONTROL Trait Expression] 此部分显示用户必须达到的条件才能达到特征的条件。These rules are set when you [create or edit a trait](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

[!UICONTROL Segments with this Trait] 该部分列出所选特征所属的所有区段。您可以单击区段名称以查看该区段的详细信息。

![](assets/traitSegments.png)

## Trait Audit/History Log {#trait-audit-history}

For rule-based and onboarded traits, the [!UICONTROL Trait Expression Change History] shows you the last 10 changes made to trait expression rules and who made them. If your trait has more than 10 changes, click **[!UICONTROL Export to CSV]** to download the entire audit log. 审核日志不适用于文件夹或算法特征。

>[!NOTE]
>
>[!UICONTROL Not Available] 列 [!UICONTROL By User] 中表示该用户的帐户已被删除。

![](assets/traitHistory.png)