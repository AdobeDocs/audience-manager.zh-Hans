---
description: 载入状态报表检查入站数据源文件中记录处理的成功和失败率。 此报表以交互式条形图显示数据，并以表格形式提供概要量度。 此外，它包含一个选项，该选项在固定时间间隔内对文件进行采样，并显示每种错误类型最常见的错误。 您可以在Analytics >载入状态报表中找到此报表。 在创建集客数据源时，此报表也可用。
seo-description: The Onboarding Status Report checks success and failure rates for processing records in your inbound data source files. This report displays data in an interactive bar chart and provides summary metrics in tabular form. And, it includes an option that samples files for a fixed time interval and displays the most common errors for each error type. You can find this report in Analytics > Onboarding Status Report. This report is also available when you create an inbound data source.
seo-title: Onboarding Status Report
solution: Audience Manager
title: 载入状态报表
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Inbound and Outbound Reports
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1421'
ht-degree: 0%

---

# 载入状态报表{#onboarding-status-report-about}

载入状态报表检查入站数据源文件中记录处理的成功和失败率。 此报表以交互式条形图显示数据，并以表格形式提供概要量度。 此外，它包含一个选项，该选项在固定时间间隔内对文件进行采样，并显示每种错误类型最常见的错误。 您可以在Analytics >载入状态报表中找到此报表。 在创建集客数据源时，此报表也可用。

>[!NOTE]
>
>只有具有管理员权限的用户才能在Audience Manager用户界面中查看此报表。 通过将非管理员用户的电子邮件添加到报表，可以让这些用户收到有关已上传入站文件状态的通知。 请参阅[接收电子邮件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)。

## 载入状态报表：关于 {#onboarding-status-about}

[!UICONTROL Onboarding Status Report]检查入站数据源文件中记录处理的成功和失败率。 此报表以交互式条形图显示数据，并以表格形式提供概要量度。 此外，它包含一个选项，该选项在固定时间间隔内对文件进行采样，并显示每种错误类型最常见的错误。 您可以在&#x200B;**[!UICONTROL Analytics > Onboarding Status Report]**&#x200B;中找到此报告。 在创建集客数据源时，此报表也可用。

## 错误报告和错误采样 {#error-reporting-sampling}

错误报告和错误取样是[!UICONTROL Onboarding Status]报告的2个单独功能。

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 功能 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>错误报告</b> </p> </td>
   <td colname="col2"> <p>错误报表显示入站数据源中处理的记录数的成功和失败率。 它以交互式、栈叠条形图和图形下方表格中摘要量度的形式返回数据。 </p> <p>错误报告是自动的。 它会对所有入站数据源持续运行。 它会根据预设时间间隔范围或通过日历小组件设置的自定义时间间隔返回数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>采样错误</b> </p> </td>
   <td colname="col2"> <p>错误取样分析数据文件的内容并返回每种错误类型的10个最常见错误。 入站数据文件中的错误会阻止处理单个记录。 使用此报表作为疑难解答工具，以帮助减少文件错误数并提高处理率。 </p> <p>您必须手动激活错误采样。 它从激活之日起运行14天，然后自行关闭。 您可以在14天间隔过期后重新启用错误采样。 在<a href="../features/manage-datasources.md#create-data-source">创建入站数据源</a>时，或者通过选中现有入站数据源的<span class="wintitle">数据Source设置</span>部分中的<b><span class="uicontrol">错误采样</span></b>复选框来激活错误采样。 </p> <p>错误取样是一个计算要求很高的过程。 因此，对于每个错误类别，它只返回前10个错误。 它并非设计用于返回入站数据源中包含的每个错误。 这些错误是潜在大量类似错误的典型示例。 查看整个文件以查找此报表标记的错误类型，重新格式化文件，然后再次发送该文件。 </p> <p>有关如何为入站数据源正确设置数据文件格式的详细信息，请参阅<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">入站数据文件内容：语法、变量和示例</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 错误报告条形图 {#error-report-bar-chart}

错误报表以栈叠条形图形式显示记录处理的成功和失败率，如以下示例所示。 图形是交互式的。 单击条形图会在图形下方的表格中显示当天的摘要量度。

![](assets/stacked-graph.png)

## 错误报告表 {#error-report-tables}

错误报告在条形图下方显示表格数据。 该表显示成功率和失败率以及总数和百分比。

**成功和失败的记录**

此默认视图显示报表中记录总数的频率计数，并包括按错误类型划分的错误。

![](assets/success-failure.png)

**总计和百分比**

单击&#x200B;**[!UICONTROL Totals & Percentages]**&#x200B;查看已成功处理的文件所占的百分比。

![](assets/totals-percentages.png)

## 14天的错误取样报表 {#error-reporting-14-days}

激活错误取样后，报表将显示每种错误类型的前10个错误。 单击报告顶部的错误类型按钮可查看每组采样数据。

>[!NOTE]
>
>报告未突出显示此当前版本的记录错误。 要查找并修复文件错误，应查看结果，并将结果与[入站数据文件内容](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)文档中的规范进行比较。

![](assets/error-samples.png)

## 接收电子邮件通知 {#receive-email-notifications}

您可以添加希望收到已上载入站文件状态通知的收件人的电子邮件地址。 请注意，您可以为不同的数据源选择不同的收件人。

![](assets/mail-notifications.png)

## 创建载入状态报表 {#create-onboard-status-report}

[!UICONTROL Sample Error Report]返回数据源中已成功处理的记录数以及失败的记录数。 按照以下步骤生成[!UICONTROL Sample Error Report]。

<!-- 

create-onboarding-status-report.xml

 -->


1. 转到&#x200B;**[!UICONTROL Analytics > Onboarding Status Report]**。 搜索数据源或从列表中选择数据源。

2. 选择日期范围。 选项包括：

   * 一组固定的报表间隔。
   * 日历小组件允许您创建自定义日期范围。

3. 单击 **[!UICONTROL OK]**。

## 载入状态报告术语和定义 {#report-terms-conditions}

有关本报告中所用标签和术语的参考指南。

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 术语 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>数据同步文件名</b> </p> </td> 
   <td colname="col2"> <p>列出<span class="keyword">Audience Manager</span>从您选择的入站数据源接收和处理的文件。 </p> <p>如果文件名格式不正确，文件处理将失败。 文件名要求因您将此数据发送到<span class="keyword">Audience Manager</span>的方式而异。 传递方法包括<span class="keyword"> Amazon S3</span>和FTP。 有关如何命名文件的说明，请参阅： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> 入站数据文件的<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md">Amazon S3名称要求</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式错误</b> </p> </td> 
   <td colname="col2"> <p>列出由于不符合语法或格式要求而处理失败的记录数。 有关如何设置数据格式的信息，请参阅<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">入站数据文件内容：语法、变量和示例</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>无效的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正确的<span class="keyword">Audience Manager</span>用户ID (UUID)的数量。 通常，这表示ID： </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">不符合预期的38位数格式。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字符。 ID应当仅为数字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>设备ID无效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正确的全局设备ID的数量。 有关应该如何设置设备ID的格式以及您应该使用哪些全局数据源（基于设备类型）的详细信息，请参阅<a href="../reference/ids-in-aam.md">Audience Manager</a>中的ID索引<a href="../features/global-data-sources.md">和</a>。</p>
  <p>报表的错误取样部分包含有关无效设备ID的详细信息，例如：</p>
   <ul>
    <li>与无效设备ID对应的数据源ID；</li>
    <li>无效的设备ID；</li>
    <li>所需的设备ID的类型，基于数据源。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>没有匹配的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>这些是已载入的ID <span class="keyword">Audience Manager</span>不能与现有ID匹配。 当<span class="keyword">Audience Manager</span>尚未执行ID同步或即使在同步后仍无法与ID匹配时，已载入的ID可以具有此状态。 </p> <p>如果移动设备ID不匹配，<span class="keyword">Audience Manager</span>将： </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">继续存储并尝试同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">如果ID无法同步，则在报告中将其记录为<span class="wintitle">存储记录</span>。 </li> 
    </ul> <p>如果您的载入文件包含移动设备ID，那么您可以比其他量度更轻松地处理这些数字。 它们不会影响后续文件的成功率和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未实现任何特征</b> </p> </td> 
   <td colname="col2"> <p>列出<span class="keyword">Audience Manager</span>不能与已载入的特征匹配的特征。 这可能是以下原因造成的： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">入站数据文件中特征格式不正确。 有关如何格式化数据文件的信息，请参阅<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">入站数据文件内容：语法、变量和示例</a>。 </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3"><span class="keyword">Audience Manager</span>中尚未定义的特征。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>文件中已成功存储的记录的百分比。 成功百分比=已处理的记录/文件中的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>条记录已接收</b> </p> </td> 
   <td colname="col2"> <p>接收的记录总数。 在大多数情况下，此数字应与入站数据文件中的记录总数（行）匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>存储的记录</b> </p> </td> 
   <td colname="col2"> <p>成功存储的记录数。 由于文件格式错误，<span class="keyword">Audience Manager</span>可能无法存储某些收到的记录。 存储的记录数可以少于接收的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已实现特征总数</b> </p> </td> 
   <td colname="col2"> <p>所有入站文件中存储在<span class="keyword">Audience Manager</span>平台中的所有用户特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用的信号总数</b> </p> </td> 
   <td colname="col2"> <p>报告中接收的未使用信号总数。 此总数基于成功存储的记录总数。 </p> <p>有关详细信息，请参阅<a href="../reporting/dynamic-reports/unused-signals.md">未使用的信号报表</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
