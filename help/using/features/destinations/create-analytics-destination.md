---
description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: 配置 Analytics 目标
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: 089a41b0176f2453e4f301c877dd6b020f726562
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 5%

---

# 配置 Analytics 目标

## 要求 {#requirements}

要配置Analytics目标，您的Audience Manager用户必须具有管理员权限。 请参阅《管理指南》中的[Create Users](/help/using/features/administration/administration-overview.md#create-users) 。 请注意，拥有`CREATE_DESTINATIONS` [通配符权限](/help/using/features/administration/administration-overview.md#wild-card-permissions)不足以创建Analytics目标。
有关更多要求，请参阅[Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html)中的先决条件。

## 您的默认Analytics目标和新的Analytics目标

| Analytics目标类型 | 描述 |
|---|---|
| 默认值 | 此默认目标的名称为“Adobe Analytics”，您可以对其进行编辑。 映射的报表包ID显示在您的Audience Manager特征和区段的文件夹存储中。 <br>  Audience Manager会在您的帐户具有以下项时自动创建一个目标：  <br>  <ul><li>满足[Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html)文档中描述的要求。</li><li>Analytics中的[报表包](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html)。</li></ul> |
| 新建 | 要创建新Analytics目标，请转到受众数据>目标>新建目标，然后针对下面描述的每个部分执行步骤。 |

## 步骤1:提供基本信息

此部分包含可启动Analytics目标创建过程的字段和选项。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**基本信息**&#x200B;以显示控件。
2. 命名目标。 避免缩写和特殊字符。
3. *（可选）* 描述目标。简洁的描述是定义或提供有关目标的更多信息的有效途径。
4. *（可选）* 在平台列 **** 表中，将默认设置保留 **为全部**。目前，这些选项没有任何用途。 它们旨在支持以后可能添加的功能。
5. 在&#x200B;**类别**&#x200B;列表中，选择&#x200B;**Adobe Experience Cloud**。
6. 在&#x200B;**类型**&#x200B;列表中，选择&#x200B;**Adobe Analytics**。
7. 单击&#x200B;**Save**&#x200B;以转到“配置”设置，或单击&#x200B;**数据导出标签**&#x200B;以将导出控件应用于目标。

>[!NOTE]
>
>对于Analytics目标，默认情况下会选中&#x200B;**自动填充目标映射**&#x200B;复选框和&#x200B;**区段ID**&#x200B;选项。 您无法更改这些设置。

![基本信息](assets/basicinformation.png)

## 步骤2:配置数据导出控制

此部分包含将[数据导出控件](/help/using/features/data-export-controls.md)应用到Analytics目标的选项。 如果您不使用数据导出控件，请跳过此步骤。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**数据导出控件**&#x200B;以公开控件。
1. 选择与应用于目标的数据导出控件对应的标签（请参阅[将数据导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md)）。 对于Analytics目标，默认情况下会选中PII复选框。
1. 单击&#x200B;**保存**。

![exportcontrols](assets/exportControls.png)

## 步骤3:映射报表包

“配置”部分列出了已启用服务器端转发的Analytics报表包。 如果您有多个Analytics目标，则分配给这些目标的报表包将互斥，并且由Audience Manager强制执行。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**配置**&#x200B;以公开控件。
1. 选择要将区段发送到的一个（或多个）报表包。
1. 单击&#x200B;**保存**。

![reportsuites](assets/reportSuites.png)

## 步骤4:区段映射

此部分提供了自动或手动映射区段的选项。

| 映射选项 | 描述 |
|---|---|
| 自动映射所有当前和未来区段 | 默认情况下，此功能会按每次点击将访客符合条件的所有区段发送到Analytics。 <br>  如果访客在一次点击中属于150个以上的Audience Manager区段，则仅向Analytics发送150个最近获得资格的区段，而其余的列表将被截断。此外，还会向Analytics发送一个标记，指示区段列表已被截断。 此操作在“受众名称”维度中显示为“已达到受众限制”，在“受众ID”维度中显示为“1”。 有关详细信息，请参阅[常见问题解答](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html)。 <br>  此外，此选项还会影响区段生成器中的目 [标可用性](/help/using/features/segments/segment-builder.md)。例如，如果区段自动映射到Analytics目标，则该目标在区段生成器的[目标映射](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations)部分中不可供选择。 Analytics目标显示为灰显状态，并在目标浏览器的“类型”列中显示“Analytics”。 |
| 手动映射区段 | 此选项会公开搜索和浏览控件，允许您选择要发送到Analytics的区段。 <br>  要搜索区段，请执行以下操作：  <br>  <ol><li>在搜索字段中键入区段名称或ID。</li><li>单击<b>Add.</b></li><li>继续搜索和添加区段，或单击<b>完成</b>。</li></ol><br>  要浏览区段，请执行以下操作： <ol><li>单击<b>浏览所有区段</b>。 这会公开可用区段的列表。</li><li>在列表中，选中要使用的区段的复选框，然后单击<b>添加选定区段</b>。</li><li>在“添加映射”窗口中，单击<b>Save</b>。 在测试版发布期间，您无法更改映射、开始或结束日期。</li><li>继续浏览并添加区段，或单击<b>完成</b>。</li></ol> ![映射段](assets/mapSegments.png) |

## 后续步骤

在创建并保存目标后，您可以在Analytics中处理该数据。 但是，可能需要几个小时才能在选定的报表包中显示数据。 请参阅[在Analytics中使用受众数据](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html)。
