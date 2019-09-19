---
description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-title: 配置分析目标
solution: Audience Manager
title: 配置分析目标
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


#  配置分析目标

## 要求 {#requirements}

请参 [阅Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/)。

## 您的默认分析目标和新的分析目标

| 分析目标类型 | 描述 |
|---|---|
| 默认值 | 此默认目标的名称为“Adobe Analytics”，您可以编辑该名称。 映射的报表包ID显示在Audience Manager特征和区段的文件夹存储中。 <br>  如果您的帐户具有： <br>  <ul><li>满足Audience Analytics文档中描 [述的要求](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) 。</li><li>Analytics中 [的报表包](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) 。</li><li>[将报表包映射到组织](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)。</li></ul> |
| 新建 | 要创建新的Analytics目标，请转到受众数据&gt;目标&gt;创建新目标，然后按照下面介绍的每个部分的步骤操作。 |

## 第1步：提供基本信息

此部分包含用于启动Analytics目标创建过程的字段和选项。 要完成此部分，请执行以下操作：

1. 单击“ **基本信息** ”以显示控件。
1. 命名目标。 避免缩写和特殊字符。
1. *（可选）* ，描述目标。 简洁的描述是定义或提供有关目标的更多信息的有效方法。
1. *（可选）* 在“平 **台”列表中** ，将默认设置保留为“全 **部”**。 目前，这些选项不会执行任何操作。 它们旨在支持以后可能添加的功能。
1. 在“类 **别** ”列表中，选 **择Adobe Experience Cloud**。
1. 在“类 **型** ”列表中，选 **择Adobe Analytics**。
1. 单击 **保存** ，转到配置设置，或单击数据导 **出标签** ，将导出控件应用到目标。

>[!NOTE]
>
>对于分析目标，默认情 **况下会选中“自动填充目标映射** ”复选框 **和“区段ID** ”选项。 您无法更改这些设置。

![基本信息](assets/basicinformation.png)

## 第2步：配置数据导出控件

此部分包含将“数据导出控 [件”应用到](/help/using/features/data-export-controls.md) “分析”目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分，请执行以下操作：

1. 单击“ **数据导出控件** ”以显示控件。
1. 选择与应用于目标的数据导出控件对应的标签(请参阅将数 [据导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) )。 对于Analytics目标，默认情况下会选中PII复选框。
1. 单击&#x200B;**保存**。

![导出控件](assets/exportControls.png)

## 第3步：映射报表包

“配置”部分列出了已启用服务器端转发的分析报表包。 如果您有多个Analytics目标，则分配给这些目标的报表包将互斥，并由Audience manager强制执行。 要完成此部分，请执行以下操作：

1. 单击 **配置** ，以显示控件。
1. 选择要将区段发送到的一个（或多个）报表包。
1. 单击&#x200B;**保存**。

![reportsuites](assets/reportSuites.png)

## 第4步：区段映射

此部分提供的选项允许您自动或手动映射区段。

| 映射选项 | 描述 |
|---|---|
| 自动映射所有当前和未来细分 | 默认情况下，此功能会将访客有资格访问的所有区段按点击发送到Analytics。 <br>  如果访客在一次点击中属于超过150个Audience manager区段，则只有150个最近符合条件的区段会发送到Analytics，而其余的列表会被截断。 将向Analytics发送另一个标志，表示区段列表被截断。 此操作在“受众名称”维中显示为“已达到受众限制”，在“受众ID”维中显示为“1”。 有关详细信息， [请参阅常](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) 见问题解答。 <br>  此外，此选项还会影响区段生成器中的目 [标可用性](/help/using/features/segments/segment-builder.md)。 例如，如果区段自动映射到分析目标，则该目标在区段生成器的目标映射部分 [不可供选择](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) 。 分析目标将显示为灰色，并在目标浏览器的“类型”列中显示“分析”。 |
| 手动映射区段 | 此选项显示搜索和浏览控件，允许您选择要发送到Analytics的区段。 <br>  要搜索区段，请执行以下操作： <br>  <ol><li>在搜索字段中键入区段名称或ID。</li><li>Click <b>Add.</b></li><li>继续搜索和添加区段，或单击 <b>完成</b>。</li></ol><br>  浏览区段： <ol><li>单击 <b>浏览所有区段</b>。 这会显示可用区段的列表。</li><li>从列表中，选中要使用的区段的复选框，然后单击添 <b>加选定区段</b>。</li><li>在“添 <b>加映射</b> ”窗口中单击“保存”。 在测试版期间，您无法更改映射、开始或结束日期。</li><li>继续浏览和添加区段，或单击 <b>完成</b>。</li></ol> ![mapsegments](assets/mapSegments.png) |

## 后续步骤

在创建并保存目标后，您可以在Analytics中处理该数据。 但是，在选定的报表包中提供数据可能需要几个小时。 See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
