---
description: 入门状态报告检查在入站数据源文件中处理记录的成功率和失败率。此报告显示交互式条形图中的数据，并提供表格表单中的摘要量度。它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics>入门状态报告中找到此报告。此报告在创建入站数据源时也可用。
seo-description: 入门状态报告检查在入站数据源文件中处理记录的成功率和失败率。此报告显示交互式条形图中的数据，并提供表格表单中的摘要量度。它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics>入门状态报告中找到此报告。此报告在创建入站数据源时也可用。
seo-title: 入门状态报告关于
solution: Audience Manager
title: 入门状态报告关于
uuid: ca8a90a-436b-4fce-adf1-48f3 b96 b3 ed2
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Onboarding Status Report{#onboarding-status-report-about}

入门状态报告检查在入站数据源文件中处理记录的成功率和失败率。此报告显示交互式条形图中的数据，并提供表格表单中的摘要量度。它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics&gt;入门状态报告中找到此报告。此报告在创建入站数据源时也可用。

>[!NOTE]
>
>只有具有管理员权限的用户才能在Audience Manager用户界面中看到此报告。您可以向非管理员用户通知上传的入站文件状态，方法是向报告中添加电子邮件。See [Receive E-mail Notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding Status Report: About {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. 此报告显示交互式条形图中的数据，并提供表格表单中的摘要量度。它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。You can find this report in **[!UICONTROL Analytics > Onboarding Status Report]**. 此报告在创建入站数据源时也可用。

## Error Reporting and Error Sampling {#error-reporting-sampling}

Error reporting and error sampling are 2 separate features of the [!UICONTROL Onboarding Status] report.

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
   <td colname="col2"> <p>错误报告显示在入站数据源中处理的记录数量的成功率和失败率。它返回交互式条形图中的数据，并作为图表下表中的摘要量度返回。 </p> <p>错误报告是自动的。它会持续为所有入站数据源运行。它会根据预设时间间隔的范围或使用日历构件设置的自定义时间间隔返回数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>错误采样</b> </p> </td>
   <td colname="col2"> <p>错误采样会解析数据文件的内容，并返回每个错误类型的10个最常见的错误。入站数据文件中的错误会阻止处理单个记录。使用此报告作为故障排除工具，帮助减少文件错误并提高处理速率。 </p> <p>必须手动激活错误采样。它从激活之日起连续14天，然后将其关闭。在14天间隔到期后，您可以重新打开错误采样。<a href="../features/manage-datasources.md#create-data-source"> 在创建入站数据源</a> 或通过从现有入站数据源的“ <b><span class="uicontrol"></span></b><span class="wintitle"> 数据源设置</span> ”部分选中“错误采样”复选框时，可以激活错误采样。 </p> <p>错误采样是一个计算要求苛刻的过程。因此，它仅返回每个错误类别的前10个错误。它并非用于返回入站数据源中包含的每个错误。这些错误是可能较大的相似错误组的代表性示例。查看整个文件，了解此报告标记的错误类型、重新格式化文件并再次发送。 </p> <p>See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for more information about how to properly format an data file for an inbound data source. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Error Report Bar Chart {#error-report-bar-chart}

该错误报告描绘堆积条形图中记录处理的成功和失败率，如下例所示。图形为交互式图形。单击条形图可在图表下的表格中显示当日的摘要量度。

![](assets/stacked-graph.png)

## Error Report Tables {#error-report-tables}

错误报告在条形图下方显示表格数据。表中显示了成功和失败率以及总计和百分比。

**成功和失败的记录**

此默认视图显示报告中记录总数的频率计数，并包含错误类型的错误分类。

![](assets/success-failure.png)

**总计和百分比**

Click **[!UICONTROL Totals & Percentages]** to see what % of your files were processed successfully.

![](assets/totals-percentages.png)

## Error Sampling Report for 14 Days {#error-reporting-14-days}

如果对错误采样进行了激活，报告将显示每个错误类型的前10个错误。单击报表顶部的错误类型按钮可查看每组采样数据。

>[!NOTE]
>
>报告不会突出显示此当前版本的记录错误。To find and fix file errors, you should review the results and compare those to the specifications in the [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentation.

![](assets/error-samples.png)

## Receive E-mail Notifications {#receive-email-notifications}

您可以添加接收已上传入站文件状态通知的收件人的电子邮件地址。请注意，您可以为不同数据源选择不同的收件人。

![](assets/mail-notifications.png)

## Create an Onboarding Status Report {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] returns the number records in a data source were processed successfully and how many failed. Follow these steps to generate a [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. **[!UICONTROL Analytics > Onboarding Status Report]**&#x200B;转至。搜索数据源或从列表中选择一个数据源。

2. 选择日期范围。选项包括：

   * 一组固定的报告间隔。
   * 可用于创建自定义日期范围的日历构件。

3. 单击 **[!UICONTROL OK]**.

## Onboarding Status Report Terms and Definitions {#report-terms-conditions}

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
   <td colname="col2"> <p>Lists files that <span class="keyword"> Audience Manager</span> received and processed from you selected inbound data source. </p> <p>如果文件名格式不正确，文件处理将失败。File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include <span class="keyword"> Amazon S3</span> and FTP. 有关如何命名文件的说明，请参阅： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 入站数据文件的 Amazon S3 名称要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式错误</b> </p> </td> 
   <td colname="col2"> <p>列出处理失败的记录数，因为它们与语法或格式要求不符。See <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a> for information on how to format your data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>AAM ID无效</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). 通常情况下，这表示ID： </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">与预期的38位格式不匹配。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字符。ID应仅为数字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>设备ID无效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正确的全局设备ID。See <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> and <a href="../features/global-data-sources.md">Global Data Sources</a>  for details on how device IDs should be formatted and what global data sources you should use, based on the device type.</p>
  <p>报告的错误取样部分包括有关无效设备ID的详细信息，如：</p>
   <ul>
    <li>与无效设备ID对应的数据源ID；</li>
    <li>无效的设备ID；</li>
    <li>基于数据源的预期设备ID的类型。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>不匹配AAM ID</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. <span class="keyword"> 在Audience Manager</span> 尚未执行ID同步或即使在同步之后，载入的ID也可能具有此状态，也可能与ID不匹配。 </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">继续存储并尝试同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a <span class="wintitle"> Stored Record</span> in the report if the ID cannot be synched. </li> 
    </ul> <p>如果您的载入文件包含移动ID，那么您可以比其他指标更轻松地对待这些数字。它们不会影响后续文件的成功率和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未实现特征</b> </p> </td> 
   <td colname="col2"> <p>Lists traits that <span class="keyword"> Audience Manager</span> cannot match to an onboarded trait. 这可能是以下结果的结果： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">在入站数据文件中有错误的格式化特征。For on how to format your data file, see <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>百分比成功</b> </p> </td> 
   <td colname="col2"> <p>成功存储的文件中记录的百分比。百分比成功=记录在文件中的记录/记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>接收的记录</b> </p> </td> 
   <td colname="col2"> <p>接收的记录总数。在大多数情况下，此数字应与入站数据文件中的记录总数(线)匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>存储的记录</b> </p> </td> 
   <td colname="col2"> <p>成功存储的记录数。Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. 存储的记录数可能小于接收的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>总认识的特征</b> </p> </td> 
   <td colname="col2"> <p>The number of traits for all users across all inbound files that get stored in the <span class="keyword"> Audience Manager</span> platform. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用的信号总数</b> </p> </td> 
   <td colname="col2"> <p>报告中收到的未使用信号总数。此总数基于成功存储的记录总数。 </p> <p>See <a href="../reporting/dynamic-reports/unused-signals.md"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>
