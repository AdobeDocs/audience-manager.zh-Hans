---
description: 测试组报告部分返回有关测试组转化的信息，从而轻松比较测试区段的功效。 有许多过滤器和维度可用于数据可视化。
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: 测试组报表
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# 测试组报表 {#test-group-reporting}

测试组报告部分返回有关测试组转化的信息，从而轻松比较测试区段的功效。 有许多过滤器和维度可用于数据可视化。

[!UICONTROL Audience Lab]返回您创建的测试区段的详细报表信息，并允许您将报表数据另存为[!DNL CSV]文件。 您可以选择介于&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;和&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;之间。

**[!UICONTROL Aggregate Reporting]**&#x200B;返回测试区段的绝对值。 **[!UICONTROL Trend Reporting]**&#x200B;返回特定时段&#x200B;*内趋势*&#x200B;的图形。 您可以通过四个选项卡自定义报表：

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">群体转化率</span></b> </p> </td> 
   <td colname="col2"> <p>返回属于已转换的特定测试区段的设备的百分比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">个转换器</span></b> </p> </td> 
   <td colname="col2"> <p>返回展现在测试组中选择的转化特征的设备数量。 <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external">观看此视频</a>，了解如何创建转化特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 总转化次数<b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>返回测试区段生成的转化次数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">测试区段人口</span></b> </p> </td> 
   <td colname="col2"> <p>返回属于测试区段的设备数。 在<b><span class="uicontrol">总人口</span></b>或<b><span class="uicontrol">实时人口</span></b>之间切换。 此差异在<a href="../../faq/faq-reporting.md">报告常见问题解答</a>中进行了说明。 </p> </td>
  </tr>
 </tbody>
</table>

您可以选择要为其生成报表的特定转化特征，也可以选择组合的所有特征。 您可以定义应返回信息的日期范围，并将报告导出为[!DNL CSV]文件。

>[!NOTE]
>
>* 测试组的报表将填充其开始日期后的第二天。
>* 只有在测试开始日期之后以及将设备添加到测试区段之后，才会计算设备的转化率。 如果在为设备分配测试组之前对该设备进行了转化，则不会计入该转化。

返回的&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;图表可能如下所示：

![](assets/aggregate-reporting.PNG)

返回的&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;图表可能如下所示。 如果要忽略绝对数字并只关注测试区段趋势，请在复选框中选择&#x200B;**[!UICONTROL Normalized]**。

![](assets/trend-reporting.PNG)
