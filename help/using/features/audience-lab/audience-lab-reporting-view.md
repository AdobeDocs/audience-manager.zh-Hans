---
description: 测试组报告部分返回有关测试组转换的信息，允许轻松比较测试区段有效性。大量滤镜和维度可用于数据可视化。
seo-description: 测试组报告部分返回有关测试组转换的信息，允许轻松比较测试区段有效性。大量滤镜和维度可用于数据可视化。
seo-title: 测试组报告
solution: Audience Manager
title: 测试组报告
topic: DIL API
uuid: 21303c3e-4c05-4728-a759-96c2 a1 d99 b69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Test Group Reporting {#test-group-reporting}

测试组报告部分返回有关测试组转换的信息，允许轻松比较测试区段有效性。大量滤镜和维度可用于数据可视化。

[!UICONTROL Audience Lab] 返回您创建的测试区段的详细报告信息，并允许您将报表数据保存为 [!DNL CSV] 文件。You can select between **[!UICONTROL Aggregate Reporting]** and **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** 返回测试区段的绝对数字。**[!UICONTROL Trend Reporting]** 返回特定时间段内趋势 *的图表*。您可以使用四个选项卡自定义报表：

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 人口转化率</span></b> </p> </td> 
   <td colname="col2"> <p>返回属于已转换的特定测试区段的设备百分比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 转换器</span></b> </p> </td> 
   <td colname="col2"> <p>返回显示在测试组中选定的转化特征的设备数。<a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 观看此视频</a> ，了解如何创建转化特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 总转化率</span></b> </p> </td> 
   <td colname="col2"> <p>返回测试区段生成的转换数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 测试细分人群</span></b> </p> </td> 
   <td colname="col2"> <p>返回属于测试区段的设备数。Toggle between <b><span class="uicontrol"> Total Population</span></b> or <b><span class="uicontrol"> Real-time Population</span></b>. <a href="../../faq/faq-reporting.md"> 报告常见问题</a> 解答中介绍了差异。 </p> </td>
  </tr>
 </tbody>
</table>

您可以选择用于生成报表的特定转化特征，也可以选择组合的所有特征。You can define a date range for which the information should be returned and export the report as a [!DNL CSV] file.

>[!NOTE]
>
>* 测试组的报告将填充开始日期后的那一天。
>* 仅在测试开始日期之后和设备已添加到测试区段之后，才对设备计数。如果在分配测试组之前对该设备进行了转换，则不会计算转换。


A returned **[!UICONTROL Aggregate Reporting]** chart could look like this:

![](assets/aggregate-reporting.PNG)

A returned **[!UICONTROL Trend Reporting]** chart could look like the one below. Select **[!UICONTROL Normalized]** in the check box if you want to ignore the absolute numbers and simply focus on the test segments trends.

![](assets/trend-reporting.PNG)