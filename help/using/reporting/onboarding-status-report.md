---
description: 入门状态报告检查入站数据源文件中处理记录的成功和失败率。 此报告以交互式条形图的形式显示数据并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在“Analytics”>“入门状态报告”中找到此报告。 创建入站数据源时也提供此报告。
seo-description: 入门状态报告检查入站数据源文件中处理记录的成功和失败率。 此报告以交互式条形图的形式显示数据并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在“Analytics”>“入门状态报告”中找到此报告。 创建入站数据源时也提供此报告。
seo-title: 载入状态报表
solution: Audience Manager
title: 载入状态报表
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1498'
ht-degree: 7%

---


# 载入状态报表{#onboarding-status-report-about}

入门状态报告检查入站数据源文件中处理记录的成功和失败率。 此报告以交互式条形图的形式显示数据并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在“Analytics”>“入门状态报告”中找到此报告。 创建入站数据源时也提供此报告。

>[!NOTE]
>
>只有具有管理员权限的用户才能在Audience Manager用户界面中看到此报告。 您可以通过向报告中添加非管理员用户的电子邮件，通知他们已上传的入站文件的状态。 请参 [阅接收电子邮件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)。

## 入门状态报告： 关于 {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. 此报告以交互式条形图的形式显示数据并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在中找到此报表 **[!UICONTROL Analytics > Onboarding Status Report]**。 创建入站数据源时也提供此报告。

## 错误报告和错误采样 {#error-reporting-sampling}

错误报告和错误采样是报告的两个独立 [!UICONTROL Onboarding Status] 特征。

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
   <td colname="col2"> <p>错误报告显示入站数据源中处理的记录数的成功率和失败率。 它返回交互式堆叠条形图中的数据以及图形下表中的摘要度量。 </p> <p>错误报告是自动的。 它可持续运行于所有入站数据源。 它根据您使用日历构件设置的预设时间间隔或自定义时间间隔返回数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>错误采样</b> </p> </td>
   <td colname="col2"> <p>采样错误会分析数据文件的内容，并返回每个错误类型的10个最常见错误。 入站数据文件中的错误会阻止处理单个记录。 将此报告用作故障排除工具，帮助减少文件错误数并提高处理速率。 </p> <p>必须手动激活错误采样。 它从激活之日起运行14天，然后关闭它。 在14天的间隔过期后，您可以重新打开错误采样。 在创建入站数据源 <a href="../features/manage-datasources.md#create-data-source"> 时或通过选中现有入站数据源</a> “数据源设置”部分的“错误采样”复选框 <b><span class="uicontrol"> ，激活</span></b><span class="wintitle"></span> 错误采样。 </p> <p>误差采样是一个计算量大的过程。 因此，它只为每个错误类别返回前10个错误。 它并非设计为返回入站数据源中包含的每个错误。 这些错误是一组可能较大的类似错误的代表性示例。 查看整个文件是否有错误类型，此报告会标记、重新设置文件格式并再次发送。 </p> <p>请参 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 阅入站数据文件内容： 语法、变量和示例</a> ，以了解有关如何为入站数据源正确设置数据文件格式的更多信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 错误报告条形图 {#error-report-bar-chart}

错误报告以堆叠条形图的形式显示记录处理的成功率和失败率，如下例所示。 图是交互的。 单击条形图下方的表格中显示当天的摘要度量。

![](assets/stacked-graph.png)

## 错误报告表 {#error-report-tables}

错误报告在条形图下显示表格数据。 下表显示了成功率和失败率以及总数和百分比。

**成功和失败的记录**

此默认视图显示报表中记录总数的频率计数，并按错误类型细分错误。

![](assets/success-failure.png)

**合计和百分比**

单 **[!UICONTROL Totals & Percentages]** 击查看成功处理的文件百分比。

![](assets/totals-percentages.png)

## 14天错误采样报告 {#error-reporting-14-days}

当错误采样处于活动状态时，报告将显示每个错误类型的前10个错误。 单击报告顶部的错误类型按钮以查看每组采样数据。

>[!NOTE]
>
>报告不会突出显示此当前版本的记录错误。 要查找并修复文件错误，您应查看结果并将其与入站数据文件内容文档中的 [规范进行比较](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 。

![](assets/error-samples.png)

## 接收电子邮件通知 {#receive-email-notifications}

您可以添加要通知已上传入站文件状态的收件人的电子邮件地址。 请注意，您可以为不同的数据源选择不同的收件人。

![](assets/mail-notifications.png)

## 创建入门状态报告 {#create-onboard-status-report}

返回 [!UICONTROL Sample Error Report] 数据源中成功处理的记录数以及失败记录数。 请按照以下步骤生成 [!UICONTROL Sample Error Report]。

<!-- 

create-onboarding-status-report.xml

 -->


1. 转到 **[!UICONTROL Analytics > Onboarding Status Report]**。 搜索数据源或从列表中选择一个数据源。

2. 选择日期范围。 选项包括：

   * 一组固定的报告间隔。
   * 可创建自定义日期范围的日历构件。

3. 单击 **[!UICONTROL OK]**.

## 入门状态报告术语和定义 {#report-terms-conditions}

此报告中使用的标签和术语的参考指南。

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
   <td colname="col2"> <p>列表从您选 <span class="keyword"> 定的入站</span> 数据源接收并处理的Audience Manager文件。 </p> <p>如果文件名的格式不正确，文件处理将失败。 文件名要求因将此数据发送到Audience Manager的方式而 <span class="keyword"> 异</span>。 投放方 <span class="keyword"> 法包括Amazon</span> S3和FTP。 有关如何命名文件的说明，请参阅： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 入站数据文件的 Amazon S3 名称要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式错误</b> </p> </td> 
   <td colname="col2"> <p>列表因不符合语法或格式要求而无法处理的记录数。 请参 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 阅入站数据文件内容： 语法、变量和示例</a> ，以了解如何格式化数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>无效AAM ID</b> </p> </td> 
   <td colname="col2"> <p>列表格式不正确的 <span class="keyword"> Audience Manager</span> ID(UUID)数。 通常，这表示ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">与预期的38位格式不匹配。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字符。 ID应仅为数字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>设备ID无效</b> </p> </td> 
   <td colname="col2"> <p>列表格式不正确的全局设备ID的数量。 请参 <a href="../reference/ids-in-aam.md">阅Audience Manager和</a><a href="../features/global-data-sources.md">全局数据源中的ID索引</a> ，了解如何格式化设备ID以及您应根据设备类型使用哪些全局数据源的详细信息。</p>
  <p>报告的错误采样部分包含有关无效设备ID的详细信息，如：</p>
   <ul>
    <li>与无效设备ID对应的数据源ID;</li>
    <li>设备ID无效；</li>
    <li>期望的设备ID的类型（基于数据源）。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>无匹配的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>这些已载入的 <span class="keyword"> ID</span> Audience Manager与现有ID不匹配。 载入的ID在Audience Manager尚未执 <span class="keyword"> 行ID</span> 同步时可能具有此状态，或者即使在同步后仍无法与ID匹配。 </p> <p>如果出现不匹配的移动ID, <span class="keyword"> Audience Manager</span> : </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">继续存储并尝试同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">如果ID无法同 <span class="wintitle"> 步</span> ，则将其记录为报告中的“存储记录”。 </li> 
    </ul> <p>如果已载入的文件包含移动ID，则可以比其他指标更轻松地处理这些数字。 它们不会影响后续文件的成功和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未实现任何特征</b> </p> </td> 
   <td colname="col2"> <p>列表特征， <span class="keyword"> Audience Manager</span> 无法与载入的特征匹配。 这可能是以下原因造成的： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">入站数据文件中的特征格式不正确。 有关如何格式化数据文件的信息，请参阅入站 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 数据文件内容： 语法、变量和示例</a>。 </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">尚未在Audience Manager中定义的 <span class="keyword"> 特征</span>。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>文件中成功存储的记录百分比。 成功百分比=已处理记录／文件中记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已接收记录</b> </p> </td> 
   <td colname="col2"> <p>收到的记录总数。 在大多数情况下，此数字应与入站数据文件中的记录总数（行）匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>存储记录</b> </p> </td> 
   <td colname="col2"> <p>成功存储的记录数。 由于文件格式错误，所收到的某些记录可能不由Audience Manager <span class="keyword"> 存储</span>。 所存储的记录数可以小于所接收的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已实现特征总数</b> </p> </td> 
   <td colname="col2"> <p>存储在Audience Manager平台中的所有入站文件中的所有用户的特征 <span class="keyword"> 数</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用信号总数</b> </p> </td> 
   <td colname="col2"> <p>报告中接收的未使用信号总数。 此总数基于成功存储的记录总数。 </p> <p>有关详 <a href="../reporting/dynamic-reports/unused-signals.md"> 细信息，请参阅</a> “未使用的信号报告”。 </p> </td> 
  </tr> 
 </tbody> 
</table>
