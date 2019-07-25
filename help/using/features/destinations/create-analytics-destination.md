---
description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-description: Audience Analytics 允许您将 Audience Manager 区段发送至 Analytics。要使用此功能，请在 Audience Manager 中创建一个 Analytics 目标，然后再将区段映射到该目标。
seo-title: 配置Analytics目标
solution: Audience Manager
title: 配置Analytics目标
translation-type: tm+mt
source-git-commit: 3179b9007e102f7031cc4cc9e0da64f77cfa3eeb

---


# 配置Analytics目标

## 要求 {#requirements}

See [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## 您的默认分析目标和新的分析目标

| Analytics目标类型 | 描述 |
|---|---|
| 默认值 | 此默认目标的名称为“Adobe Analytics”，您可以编辑该名称。映射的报告套件ID显示在Audience Manager特征和区段的文件夹存储中。<br>Audience Manager会自动创建一个目标，如果您的帐户有： <br> <ul><li>Met the requirements described in the [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) documentation.</li><li>A [report suite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[将报告套件映射到组织](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)。</li></ul> |
| 新建 | 要创建新的Analytics目标，请转到“受众数据”&gt;“目标”&gt;“创建新目标”，然后按照以下每个部分的步骤操作。 |

## 步骤1：提供基本信息

本节包含启动Analytics目标创建过程的字段和选项。要完成本节，请执行以下操作：

1. Click **Basic Information** to expose the controls.
2. 命名目标。避免缩写和特殊字符。
3. *(可选)* 描述目标。简明描述是定义或提供目标的更多信息的有效方法。
4. *(可选)* 在 **平台** 列表中，将默认设置保留 **为“全部”**。目前，这些选项不做任何事情。它们设计为支持以后添加的功能。
5. In the **Category** list, select **Adobe Experience Cloud**.
6. In the **Type** list, select **Adobe Analytics**.
7. Click **Save** to go to the Configuration settings or click **Data Export Labels** to apply export controls to the destination.

>[!NOTE]
>
>For an Analytics destination, the **Auto-fill Destination Mappping** check box and **Segment ID** option are selected by default. 您无法更改这些设置。

![基础信息](assets/basicinformation.png)

## 步骤2：配置数据导出控件

This section contains options that apply [Data Export Controls](/help/using/features/data-export-controls.md) to an Analytics destination. 如果您不使用数据导出控件，请跳过此步骤。要完成本节，请执行以下操作：

1. Click **Data Export Controls** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Data Export Labels to a Destination](/help/using/features/destinations/manage-destinations.md#add-data-export-labels) ). 对于Analytics目标，默认情况下会选中PII复选框。
3. 单击&#x200B;**保存**。

![外部控件](assets/exportControls.png)

## 步骤3：映射报表包

配置部分列出了已启用服务器端转发的Analytics报告套件。如果您有多个Analytics目标，分配给这些目标的报表包将由Audience Manager共同排除和执行。要完成本节，请执行以下操作：

1. Click **Configuration** to expose the controls.
2. 选择要将区段发送到的一个(或多个)报表包。
3. 单击&#x200B;**保存**。

![Reportsuites](assets/reportSuites.png)

## 第步：细分映射

本节提供允许您自动或手动映射区段的选项。

| 映射选项 | 描述 |
|---|---|
| 自动映射当前和未来的区段 | 默认情况下，此功能会将访客符合条件的所有区段发送到Analytics。<br>如果一个访客在一次点击时属于超过150个Audience Manager细分，则只有150个最近合格的区段才会发送到Analytics，而其余列表将被截断。将向Analytics发送额外的标记，表明区段列表被截断。此操作在受众名称维度中显示为“受众限制”，在受众ID维度中显示为“1”。See the [FAQ](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) for details. <br>此外，此选项影响区段生成器中 [的目标可用性](/help/using/features/segments/segment-builder.md)。For example, if a segment is mapped automatically to an Analytics destination, that destination is not available for selection in the [destination mappings](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) section of Segment Builder. Analytics目标显示灰显，并在目标浏览器的类型列中显示“Analytics”。 |
| 手动映射区段 | 此选项会显示搜索和浏览控件，用于选择要发送到Analytics的区段。<br>要搜索区段，请执行以下操作： <br> <ol><li>在搜索字段中键入区段名称或ID。</li><li>Click <b>Add.</b></li><li>Continue to search and add segments or click <b>Done</b>.</li></ol><br>浏览区段： <ol><li>Click <b>Browse all segments</b>. 这会显示可用区段列表。</li><li>From the list, select the check box of the segment you want to use and click <b>Add selected segments</b>.</li><li>Click <b>Save</b> in the Add Mappings window. 在测试版期间，您无法更改映射、开始或结束日期。</li><li>Continue to browse and add segments or click <b>Done</b>.</li></ol> |

![映射段](assets/mapSegments.png)

## 后续步骤

创建并保存目标后，您可以在Analytics中处理该数据。但是，在选定的报表包中使用数据可能需要几个小时的时间。See [Use the Audience Data in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).



