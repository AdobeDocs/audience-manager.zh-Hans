---
description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: 配置Analytics目标
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 4%

---

# 配置Analytics目标

## 要求 {#requirements}

要配置Analytics目标，您的Audience Manager用户必须具有管理员权限。 请参阅管理指南中的[创建用户](/help/using/features/administration/administration-overview.md#create-users)。 请注意，具有`CREATE_DESTINATIONS` [通配符权限](/help/using/features/administration/administration-overview.md#wild-card-permissions)不足以创建Analytics目标。
有关更多要求，请参阅[Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=zh-Hans)中的先决条件。

## 您的默认Analytics目标和新Analytics目标

| Analytics目标类型 | 描述 |
|---|---|
| 默认值 | 此默认目标的名称为“Adobe Analytics”，您可以编辑该名称。 映射的报表包ID会显示在文件夹存储中，以用于Audience Manager特征和区段。 <br>  如果您的帐户具有： <br>，则Audience Manager会自动创建一个目标  <ul><li>符合[Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=zh-Hans)文档中描述的要求。</li><li>Analytics中的[报表包](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=zh-Hans)。</li></ul> |
| 新建 | 要创建新的Analytics目标，请转到受众数据>目标>创建新目标，然后执行下面所述每个部分的步骤。 |

## Adobe Analytics中的Audience Manager区段资格 {#segment-qualifications}

将区段信息发送到Analytics目标时，Audience Manager仅发送访客符合条件的区段。 如果访客不再符合区段的资格条件，此信息&#x200B;_不会_&#x200B;转发到Adobe Analytics。

例如，请考虑以下区段规则：

* 区段A：特征1和特征2
* 区段B：特征1，而非特征2

在Analytics报表中，配置文件可能会显示为同时符合两个区段的条件，即使它不再符合区段B的条件。

## 步骤1：提供基本信息

此部分包含启动Analytics目标创建过程的字段和选项。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**基本信息**&#x200B;以公开控件。
2. 命名目标。 避免使用缩写和特殊字符。
3. *（可选）*&#x200B;描述目标。 简洁的描述是定义或提供更多有关目标的信息的有效方式。
4. *（可选）*&#x200B;在&#x200B;**Platform**&#x200B;列表中，将默认设置保留为&#x200B;**All**。 目前，这些选项没有任何效果。 它们旨在支持以后可能添加的功能。
5. 在&#x200B;**类别**&#x200B;列表中，选择&#x200B;**Adobe Experience Cloud**。
6. 在&#x200B;**类型**&#x200B;列表中，选择&#x200B;**Adobe Analytics**。
7. 单击&#x200B;**保存**&#x200B;以转到配置设置，或单击&#x200B;**数据导出标签**&#x200B;以将导出控件应用到目标。

>[!NOTE]
>
>对于Analytics目标，默认情况下会选中&#x200B;**自动填充目标映射**&#x200B;复选框和&#x200B;**区段ID**&#x200B;选项。 您无法更改这些设置。

![基本信息](assets/basicinformation.png)

## 步骤2：配置数据导出控制

此部分包含将[数据导出控件](/help/using/features/data-export-controls.md)应用于Analytics目标的选项。 如果不使用数据导出控件，请跳过此步骤。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**数据导出控件**&#x200B;以公开这些控件。
1. 选择与应用于目标的数据导出控制对应的标签（请参阅[将数据导出标签添加到目标](/help/using/features/destinations/add-data-export-labels.md) ）。 对于Analytics目标，默认情况下会选中PII复选框。
1. 单击&#x200B;**保存**。

![exportcontrols](assets/exportControls.png)

## 步骤3：映射报表包

配置部分列出了已为服务器端转发启用的Analytics报表包。 如果您有多个Analytics目标，则分配给这些目标的报表包将互斥并由Audience Manager强制执行。 要完成此部分，请执行以下操作：

1. 单击&#x200B;**配置**&#x200B;以公开控件。
1. 选择一个（或多个）要将区段发送到的报表包。
1. 单击&#x200B;**保存**。

![报告包](assets/reportSuites.png)

## 步骤4：区段映射

此部分提供了允许您自动或手动映射区段的选项。

| 映射选项 | 描述 |
|---|---|
| 自动映射所有当前和未来区段 | 默认情况下，选中此功能后，会将访客符合条件的所有区段按点击发送到Analytics。 <br>  如果某位访客在一次点击中属于超过150个Audience Manager区段，则仅会将最近限定的150个区段发送到Analytics，而其余列表将被截断。 此外，还会向Analytics发送一个标记，指示区段列表被截断。 此操作在受众名称维度中显示为“已达到受众限制”，在受众ID维度中显示为“1”。 有关详细信息，请参阅[常见问题解答](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html?lang=zh-Hans)。 <br>  此外，此选项会影响[区段生成器](/help/using/features/segments/segment-builder.md)中的目标可用性。 例如，如果某个区段自动映射到Analytics目标，则该目标在区段生成器的[目标映射](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations)部分中不可选择。 Analytics目标将显示为灰色，并在目标浏览器的“类型”列中显示“Analytics”。 |
| 手动映射区段 | 此选项显示搜索和浏览控件，这些控件允许您选择要发送到Analytics的区段。 <br>  要搜索区段，请执行以下操作： <br>  <ol><li>在搜索字段中键入区段名称或ID。</li><li>单击<b>添加。</b></li><li>继续搜索和添加区段，或单击<b>完成</b>。</li></ol><br>  要浏览区段，请执行以下操作： <ol><li>单击<b>浏览所有区段</b>。 这会公开可用区段的列表。</li><li>从列表中，选中要使用的区段的复选框，然后单击<b>添加选定的区段</b>。</li><li>在“添加映射”窗口中单击<b>保存</b>。 在测试版发布期间，您无法更改映射、开始日期或结束日期。</li><li>继续浏览并添加区段，或单击<b>完成</b>。</li></ol> ![映射区段](assets/mapSegments.png) |

## 后续步骤

创建并保存目标后，您可以在Analytics中处理该数据。 但是，可能需要几个小时之后，数据才能显示在您选择的报表包中。 查看[在Analytics中使用受众数据](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html?lang=zh-Hans)。
