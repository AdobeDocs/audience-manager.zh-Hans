---
description: 入门状态报告检查入站数据源文件中处理记录的成功和失败率。 此报告以交互式条形图的形式显示数据，并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在“分析”>“入门状态报告”中找到此报告。 在创建入站数据源时，此报告也可用。
seo-description: 入门状态报告检查入站数据源文件中处理记录的成功和失败率。 此报告以交互式条形图的形式显示数据，并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在“分析”>“入门状态报告”中找到此报告。 在创建入站数据源时，此报告也可用。
seo-title: 入门状态报告关于
solution: Audience Manager
title: 入门状态报告关于
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# 入门状态报告{#onboarding-status-report-about}

入门状态报告检查入站数据源文件中处理记录的成功和失败率。 此报告以交互式条形图的形式显示数据，并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在“分析”&gt;“入门状态报告”中找到此报告。 在创建入站数据源时，此报告也可用。

>[!NOTE]
>
>只有具有管理员权限的用户才能在Audience Manager用户界面中查看此报告。 可以向报告添加已上载入站文件的电子邮件，以通知非管理员用户其状态。 请参 [阅接收电子邮件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)。

##  入门状态报告：关于 {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. 此报告以交互式条形图的形式显示数据，并以表格形式提供摘要指标。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在中找到此报告 **[!UICONTROL Analytics > Onboarding Status Report]**。 在创建入站数据源时，此报告也可用。

## 错误报告和错误采样 {#error-reporting-sampling}

错误报告和错误采样是报告的2个独立功 [!UICONTROL Onboarding Status] 能。

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
   <td colname="col2"> <p>错误报告显示入站数据源中处理的记录数的成功率和失败率。 它以交互式的堆叠条形图返回数据，并以摘要度量形式返回图表下的表。 </p> <p>错误报告是自动的。 它可持续运行于所有入站数据源。 它根据您使用日历构件设置的预设时间间隔或自定义时间间隔返回数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>错误采样</b> </p> </td>
   <td colname="col2"> <p>采样错误会分析数据文件的内容，并返回每个错误类型的10个最常见错误。 入站数据文件中的错误会阻止处理单个记录。 将此报告用作故障排除工具，帮助减少文件错误数并提高处理率。 </p> <p>必须手动激活错误采样。 它从激活之日起运行14天，然后关闭自己。 在14天的间隔过期后，您可以重新打开错误采样。 在创建入站数据源时 <a href="../features/manage-datasources.md#create-data-source"></a><b><span class="uicontrol"></span></b><span class="wintitle"></span> ，或通过选中现有入站数据源的“数据源设置”部分的“错误采样”复选框来激活错误采样。 </p> <p>误差采样是一个计算量很大的过程。 因此，它只为每个错误类别返回前10个错误。 它并非设计为返回入站数据源中包含的每个错误。 这些错误是一组可能较大的类似错误的代表性示例。 查看整个文件是否有错误类型，此报告会标记、重新设置文件格式并再次发送。 </p> <p>请参阅 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 入站数据文件内容：语法、变量和示例</a> ，以了解有关如何为入站数据源正确设置数据文件格式的更多信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 错误报告条形图 {#error-report-bar-chart}

错误报告以条形图的形式绘制记录处理的成功率和失败率，如下例所示。 该图是交互式的。 单击某条可在图形下方的表格中显示当天的摘要指标。

![](assets/stacked-graph.png)

## 错误报告表 {#error-report-tables}

错误报告在条形图下方显示表格数据。 下表显示了成功率和失败率以及总数和百分比。

**成功记录和失败记录**

此默认视图显示报表中总记录的频率计数，并按错误类型细分错误。

![](assets/success-failure.png)

**合计和百分比**

单 **[!UICONTROL Totals & Percentages]** 击查看成功处理的文件百分比。

![](assets/totals-percentages.png)

## 14天的错误采样报告 {#error-reporting-14-days}

当错误采样处于活动状态时，报告将显示每个错误类型的前10个错误。 单击报告顶部的错误类型按钮可查看每组采样数据。

>[!NOTE]
>
>报告不会突出显示当前版本中的记录错误。 要查找和修复文件错误，您应查看结果并将其与入站数据文件内容文档中的规 [范进行比较](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 。

![](assets/error-samples.png)

## 接收电子邮件通知 {#receive-email-notifications}

您可以添加收件人的电子邮件地址，以便收到上传的入站文件状态通知。 请注意，您可以为不同的数据源选择不同的收件人。

![](assets/mail-notifications.png)

## 创建入门状态报告 {#create-onboard-status-report}

返回 [!UICONTROL Sample Error Report] 数据源中成功处理的记录数以及失败的记录数。 请按照以下步骤生成 [!UICONTROL Sample Error Report]。

<!-- 

create-onboarding-status-report.xml

 -->


1. 转到 **[!UICONTROL Analytics > Onboarding Status Report]**。 搜索数据源或从列表中选择一个数据源。

2. 选择日期范围。 选项包括：

   * 一组固定的报告间隔。
   * 可创建自定义日期范围的日历构件。

3. 单击 **[!UICONTROL OK]**.

## 入门状态报告条款和定义 {#report-terms-conditions}

有关此报告中使用的标签和术语的参考指南。

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
   <td colname="col2"> <p>列出Audience Manager从您选 <span class="keyword"> 定的入站数据源接收和处理的文件</span> 。 </p> <p>如果文件名的格式不正确，文件处理将失败。 文件名要求因将此数据发送到 <span class="keyword"> Audience manager的方式而异</span>。 交付方法 <span class="keyword"> 包括Amazon S3</span> 和FTP。 有关如何命名文件的说明，请参阅： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 入站数据文件的 Amazon S3 名称要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式错误</b> </p> </td> 
   <td colname="col2"> <p>列出由于不符合语法或格式要求而处理失败的记录数。 请参阅 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 入站数据文件内容：语法、变量和示例</a> ，以了解如何设置数据格式的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>AAM ID无效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正确的 <span class="keyword"> Audience Manager用户</span> ID(UUID)的数量。 通常，这表示ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">与预期的38位格式不匹配。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字符。 ID应仅为数字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>设备ID无效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正确的全局设备ID的数量。 有关 <a href="../reference/ids-in-aam.md">设备ID的格式化方式以及您应根据设备类型使用哪些全局数据源的详细信息，请参阅Audience Manager和</a><a href="../features/global-data-sources.md"></a> Global Data Sources中的ID索引。</p>
  <p>报告的错误采样部分包含有关无效设备ID的详细信息，例如：</p>
   <ul>
    <li>与无效设备ID对应的数据源ID;</li>
    <li>设备ID无效；</li>
    <li>基于数据源的预期设备ID的类型。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>无匹配的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>这些已载入的ID <span class="keyword"> 是Audience Manager</span> ，与现有ID不匹配。 载入的ID在 <span class="keyword"> Audience Manager</span> 尚未执行ID同步或即使在同步后仍无法与ID匹配时可能具有此状态。 </p> <p>如果移动ID不匹配， <span class="keyword"> Audience Manager</span> 将： </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">继续存储并尝试同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">如果ID无法同 <span class="wintitle"> 步</span> ，请将其记录为报告中的存储记录。 </li> 
    </ul> <p>如果已载入的文件包含移动ID，则您可以比其他指标更轻松地处理这些数字。 它们不会影响后续文件的成功和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未实现任何特征</b> </p> </td> 
   <td colname="col2"> <p>列出Audience Manager不能与已载入 <span class="keyword"> 的特征匹配</span> 的特征。 这可能是以下原因造成的： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">入站数据文件中的特征格式不正确。 有关如何设置数据文件格式的信息，请参阅入站数 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 据文件内容：语法、变量和示例</a>。 </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">尚未在 <span class="keyword"> Audience Manager中定义的特征</span>。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>文件中成功存储的记录百分比。 成功百分比=已处理记录／文件中的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>收到的记录</b> </p> </td> 
   <td colname="col2"> <p>收到的记录总数。 在大多数情况下，此数字应与入站数据文件中的记录总数（行）匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>存储记录</b> </p> </td> 
   <td colname="col2"> <p>成功存储的记录数。 由于文件格式错误，Audience manager可能无法存储收到的某些记 <span class="keyword"> 录</span>。 所存储的记录数可以小于所接收记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>实现的总特征</b> </p> </td> 
   <td colname="col2"> <p>存储在 <span class="keyword"> Audience Manager平台中的所有入站文件中的所有用户的特征数</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用信号总数</b> </p> </td> 
   <td colname="col2"> <p>报告中接收的未使用信号的总数。 此总数基于成功存储的记录总数。 </p> <p>有关更 <a href="../reporting/dynamic-reports/unused-signals.md"> 多信息，请参阅未使用的信号报告</a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>
