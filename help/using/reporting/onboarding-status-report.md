---
description: 载入状态报表检查入站数据源文件中记录处理的成功和失败率。 此报表以交互式条形图形式显示数据，并以表格形式提供概要量度。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics >载入状态报表中找到此报表。 在创建入站数据源时，此报表也可用。
seo-description: 载入状态报表检查入站数据源文件中记录处理的成功和失败率。 此报表以交互式条形图形式显示数据，并以表格形式提供概要量度。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics >载入状态报表中找到此报表。 在创建入站数据源时，此报表也可用。
seo-title: 载入状态报表
solution: Audience Manager
title: 载入状态报表
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: 入站和出站报表
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1502'
ht-degree: 7%

---

# 载入状态报表{#onboarding-status-report-about}

载入状态报表检查入站数据源文件中记录处理的成功和失败率。 此报表以交互式条形图形式显示数据，并以表格形式提供概要量度。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics >载入状态报表中找到此报表。 在创建入站数据源时，此报表也可用。

>[!NOTE]
>
>只有具有管理员权限的用户才能在Audience Manager用户界面中看到此报表。 您可以通过向报表添加非管理员用户的电子邮件，向其发送有关已上传入站文件状态的通知。 请参阅[接收电子邮件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications)。

## 载入状态报表：关于{#onboarding-status-about}

[!UICONTROL Onboarding Status Report]检查入站数据源文件中记录处理的成功和失败率。 此报表以交互式条形图形式显示数据，并以表格形式提供概要量度。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在&#x200B;**[!UICONTROL Analytics > Onboarding Status Report]**&#x200B;中找到此报表。 在创建入站数据源时，此报表也可用。

## 错误报告和错误采样{#error-reporting-sampling}

错误报告和错误采样是[!UICONTROL Onboarding Status]报告的2个不同功能。

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
   <td colname="col2"> <p>错误报表显示入站数据源中处理的记录数的成功率和失败率。 它可在交互式堆叠条形图中返回数据，并在图形下方的表格中作为概要量度。 </p> <p>错误报告是自动的。 它针对所有入站数据源持续运行。 它会根据预设时间间隔范围或您使用日历小组件设置的自定义时间间隔返回数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>错误取样</b> </p> </td>
   <td colname="col2"> <p>错误采样会解析数据文件的内容，并为每个错误类型返回10个最常见的错误。 集客数据文件中的错误会阻止处理单个记录。 将此报告用作故障诊断工具，以帮助减少文件错误数并提高处理率。 </p> <p>必须手动激活错误取样。 它从激活之日起持续14天，然后关闭自己。 在14天的间隔过期后，您可以重新打开错误取样功能。 在<a href="../features/manage-datasources.md#create-data-source">创建集客数据源</a>时，或通过选中现有集客数据源<span class="wintitle">数据源设置</span>部分中的<b><span class="uicontrol">错误采样</span></b>复选框来激活错误采样。 </p> <p>误差采样是一个计算上要求很高的过程。 因此，它仅为每个错误类别返回前10个错误。 它并非设计为返回集客数据源中包含的每个错误。 这些错误是一组可能较大的类似错误的代表性示例。 查看整个文件，了解此报告标记的错误类型，重新设置文件格式，然后再次发送。 </p> <p>请参阅<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">入站数据文件内容：语法、变量和示例</a> ，以了解有关如何为入站数据源正确设置数据文件格式的更多信息。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 错误报表条形图{#error-report-bar-chart}

错误报表以图形表示堆叠式条形图中记录处理的成功和失败率，如以下示例所示。 图表是交互式的。 单击某条栏会在图表下方的表格中显示当天的概要量度。

![](assets/stacked-graph.png)

## 错误报表表{#error-report-tables}

错误报告在条形图下方显示表格数据。 该表显示了成功和失败率以及总数和百分比。

**成功和失败的记录**

此默认视图显示报表中总记录的频率计数，并包含按错误类型划分错误的信息。

![](assets/success-failure.png)

**总计和百分比**

单击&#x200B;**[!UICONTROL Totals & Percentages]**&#x200B;可查看已成功处理文件的百分比。

![](assets/totals-percentages.png)

## 14天的取样报告出错{#error-reporting-14-days}

在错误取样处于活动状态时，报告将显示每种错误类型的前10个错误。 单击报表顶部的错误类型按钮可查看每组采样数据。

>[!NOTE]
>
>此报表未突出显示此当前版本中的记录错误。 要查找和修复文件错误，您应查看结果并将其与[入站数据文件内容](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)文档中的规范进行比较。

![](assets/error-samples.png)

## 接收电子邮件通知{#receive-email-notifications}

您可以添加接收者的电子邮件地址，以便接收有关已上传入站文件状态的通知。 请注意，您可以为不同的数据源选择不同的收件人。

![](assets/mail-notifications.png)

## 创建载入状态报表{#create-onboard-status-report}

[!UICONTROL Sample Error Report]返回数据源中已成功处理的数量记录以及失败的数量。 按照以下步骤生成[!UICONTROL Sample Error Report]。

<!-- 

create-onboarding-status-report.xml

 -->


1. 转到&#x200B;**[!UICONTROL Analytics > Onboarding Status Report]**。 搜索数据源或从列表中选择一个数据源。

2. 选择日期范围。 选项包括：

   * 一组固定的报告间隔。
   * 用于创建自定义日期范围的日历小组件。

3. 单击 **[!UICONTROL OK]**.

## 载入状态报表术语和定义{#report-terms-conditions}

有关此报表中使用的标签和术语的参考指南。

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
   <td colname="col2"> <p>列出从您选择的入站数据源接收并处理<span class="keyword">Audience Manager</span>的文件。 </p> <p>如果文件名格式不正确，文件处理将失败。 文件名要求因您将此数据发送到<span class="keyword">Audience Manager</span>的方式而异。 交付方法包括<span class="keyword"> Amazon S3</span>和FTP。 有关如何命名文件的说明，请参阅： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 入站数据文件的 Amazon S3 名称要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>设置错误格式</b> </p> </td> 
   <td colname="col2"> <p>列出由于语法或格式要求不匹配而处理失败的记录数。 请参阅<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">入站数据文件内容：语法、变量和示例</a>以了解有关如何设置数据格式的信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>无效的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正确的<span class="keyword">Audience Manager</span>用户ID(UUID)的数量。 通常，这表示ID: </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">与预期的38位格式不匹配。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字符。 ID应该只是数字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>设备ID无效</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正确的全局设备ID的数量。 请参阅<a href="../reference/ids-in-aam.md">Audience Manager</a>和<a href="../features/global-data-sources.md">全局数据源</a>中的ID索引，以详细了解设备ID的格式设置以及您应根据设备类型使用的全局数据源。</p>
  <p>报告的错误取样部分包含有关无效设备ID的详细信息，例如：</p>
   <ul>
    <li>与无效设备ID对应的数据源ID;</li>
    <li>设备ID无效；</li>
    <li>基于数据源的预期设备ID类型。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>无匹配的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>这些是已载入的ID <span class="keyword">Audience Manager</span>与现有ID不匹配。 当<span class="keyword">Audience Manager</span>尚未执行ID同步时，载入的ID可能具有此状态，或者即使在同步后仍无法匹配ID。 </p> <p>对于不匹配的移动ID，<span class="keyword">Audience Manager</span>将： </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">继续存储并尝试同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">如果ID无法同步，请在报表中将其记录为<span class="wintitle">存储记录</span>。 </li> 
    </ul> <p>如果已载入的文件包含移动ID，则与其他量度相比，您可以更轻松地处理这些数字。 它们不会影响后续文件的成功率和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未实现特征</b> </p> </td> 
   <td colname="col2"> <p>列出<span class="keyword">Audience Manager</span>与已载入特征不匹配的特征。 这可能是以下原因的结果： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">入站数据文件中的特征格式不正确。 有关如何设置数据文件格式的信息，请参阅<a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md">入站数据文件内容：语法、变量和示例</a>。 </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">尚未在<span class="keyword">Audience Manager</span>中定义的特征。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>文件中已成功存储的记录的百分比。 成功百分比=已处理的记录数/文件中的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>收到的记录</b> </p> </td> 
   <td colname="col2"> <p>收到的记录总数。 在大多数情况下，此数字应与集客数据文件中的记录总数（行）匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>存储的记录</b> </p> </td> 
   <td colname="col2"> <p>已成功存储的记录数。 由于文件格式错误，收到的某些记录可能不会由<span class="keyword">Audience Manager</span>存储。 存储的记录数可以小于接收的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已实现特征总数</b> </p> </td> 
   <td colname="col2"> <p>存储在<span class="keyword">Audience Manager</span>平台中的所有集客文件中所有用户的特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用的信号总数</b> </p> </td> 
   <td colname="col2"> <p>报告中接收的未使用信号的总数。 此总数基于成功存储的记录总数。 </p> <p>有关更多信息，请参阅<a href="../reporting/dynamic-reports/unused-signals.md">未使用的信号报表</a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>
