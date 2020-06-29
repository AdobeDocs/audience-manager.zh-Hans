---
description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-title: 配置 Analytics 目标
solution: Audience Manager
title: 配置 Analytics 目标
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 8%

---


# 配置 Analytics 目标

## 要求 {#requirements}

要配置Analytics目标，您的Audience Manager用户必须具有“管理员”权限。 请参 [阅《管理指南](/help/using/features/administration/administration-overview.md#create-users) 》中的“创建用户”。 请注意，拥有通配符 `CREATE_DESTINATIONS` 权 [限不足](/help/using/features/administration/administration-overview.md#wild-card-permissions) ，无法创建Analytics目标。
有关进一步要求，请参阅受众 [Analytics的先决条件](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html)。

## 您的默认Analytics目的地和新Analytics目的地

| Analytics目标类型 | 描述 |
|---|---|
| 默认值 | 此默认目标的名称为“AdobeAnalytics”，您可以编辑该名称。 映射的报表包ID显示在您的存储特征和区段的文件夹Audience Manager中。 <br>  Audience Manager在帐户具有以下各项时自动创建一个目标： <br>  <ul><li>满足受众Analytics文 [档中所述](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/mc-audiences-aam.html) 的要求。</li><li>Analytics [的一个报](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) 告套间。</li><li>[将报表包映射到组织](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)。</li></ul> |
| 新建 | 要创建新的Analytics目标，请转至受众数据>目标>创建新目标，然后按照下面介绍的每个部分的步骤操作。 |

## 第1步： 提供基本信息

此部分包含开始Analytics目标创建过程的字段和选项。 要完成此部分：

1. 单击 **“基本信息** ”以显示控件。
2. 命名目标。 避免缩写和特殊字符。
3. *（可选）* 描述目标。 简洁的描述是定义或提供有关目标的更多信息的有效方式。
4. *(可选* )在“ **平台** ”列表中，将默认设置保 **留为All**。 目前，这些选项没有任何用处。 它们旨在支持以后可能添加的功能。
5. 在 **类别** 列表 **中**，选择Adobe Experience Cloud。
6. 在“类 **型** ”列表 **中**，选择AdobeAnalytics。
7. 单击 **保存** ，转到配置设置，或单击数据 **导出标签** ，将导出控件应用到目标。

>[!NOTE]
>
>对于Analytics目标， **默认情况下会选中“自动填充目标** 映 **射”复选框和“段** ID”选项。 您无法更改这些设置。

![基本信息](assets/basicinformation.png)

## 第2步： 配置数据导出控件

本节包含将数据导出控 [制应用于Analytics](/help/using/features/data-export-controls.md) 目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分：

1. 单击“ **数据导出控件** ”以显示控件。
1. 选择与应用于目标的数据导出控件对应的标签(请参 [阅将数据导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) )。 对于Analytics目标，默认情况下会选中PII复选框。
1. 单击&#x200B;**保存**。

![导出控件](assets/exportControls.png)

## 第3步： 映射报表包

“配置”部分列表已启用服务器端转发的Analytics报表包。 如果您有多个Analytics目标，则分配给这些目标的报表包将互斥，并由Audience Manager执行。 要完成此部分：

1. 单击 **配置** ，以显示控件。
1. 选择要将区段发送到的一个或多个报表包。
1. 单击&#x200B;**保存**。

![reportsuites](assets/reportSuites.png)

## 第4步： 区段映射

此部分提供了可自动或手动映射区段的选项。

| 映射选项 | 描述 |
|---|---|
| 自动映射所有当前和未来细分 | 默认情况下，此功能将按点击将访客有资格访问的所有区段发送到Analytics。 <br>  如果访客在一次点击中属于超过150个Audience Manager段，则仅向Analytics发送150个最新符合条件的段，而其余的列表则被截断。 向Analytics发送额外的标志，表明该段列表被截断。 此操作在受众名称维中显示为“已达到受众限制”，在受众ID维中显示为“1”。 有关详细信 [息](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) ，请参阅常见问题解答。 <br>  此外，此选项还影响区段生成器中的目 [标可用性](/help/using/features/segments/segment-builder.md)。 例如，如果区段自动映射到Analytics目标，则该目标在区段生成器的目标映射部分 [不可](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) 供选择。 Analytics目标将灰显，并在目标浏览器的“类型”列中显示“Analytics”。 |
| 手动映射区段 | 此选项显示搜索和浏览控件，允许您选择要发送到Analytics的区段。 <br>  要搜索区段，请执行以下操作： <br>  <ol><li>在搜索字段中键入段名称或ID。</li><li>Click <b>Add.</b></li><li>继续搜索和添加区段，或单击 <b>完成</b>。</li></ol><br>  浏览区段： <ol><li>单击 <b>浏览所有区段</b>。 这会显示一列表可用区段。</li><li>在列表中，选中要使用的区段的复选框，然后单击添 <b>加选定区段</b>。</li><li>单击 <b>添加</b> “映射”窗口中的保存。 在测试版期间，您无法更改映射、开始或结束日期。</li><li>继续浏览和添加区段，或单击 <b>完成</b>。</li></ol> ![mapsegmts](assets/mapSegments.png) |

## 后续步骤

创建并保存目标后，您可以在Analytics处理该数据。 但是，可能需要几个小时才能在所选报表包中提供数据。 See [Use the Audience Data in Analytics](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html).
