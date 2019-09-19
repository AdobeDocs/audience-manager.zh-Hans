---
description: 测试组报告部分返回有关测试组转换的信息，从而便于比较测试段的有效性。 为数据可视化提供了大量过滤器和维度。
seo-description: 测试组报告部分返回有关测试组转换的信息，从而便于比较测试段的有效性。 为数据可视化提供了大量过滤器和维度。
seo-title: 测试组报告
solution: Audience Manager
title: 测试组报告
topic: DIL API
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 测试组报告 {#test-group-reporting}

测试组报告部分返回有关测试组转换的信息，从而便于比较测试段的有效性。 为数据可视化提供了大量过滤器和维度。

[!UICONTROL Audience Lab] 返回您创建的测试区段的详细报告信息，并允许您将报告数据另存为文 [!DNL CSV] 件。 您可以在和之间 **[!UICONTROL Aggregate Reporting]** 进行选 **[!UICONTROL Trend Reporting]**&#x200B;择。

**[!UICONTROL Aggregate Reporting]** 返回测试段的绝对数。 **[!UICONTROL Trend Reporting]** 返回特定时间段内 *的趋势图*。 通过四个选项卡可以自定义报告：

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
   <td colname="col2"> <p>返回属于已转换的特定测试区段的设备的百分比。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 转换器</span></b> </p> </td> 
   <td colname="col2"> <p>返回显示测试组中所选转换特征的设备数。 <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 观看此视频</a> ，了解如何创建转化特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 转化总数</span></b> </p> </td> 
   <td colname="col2"> <p>返回测试区段生成的转换数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 测试区段总体</span></b> </p> </td> 
   <td colname="col2"> <p>返回属于测试段的设备数。 在“总 <b><span class="uicontrol"> 人口”</span></b><b><span class="uicontrol"> 或“实时人口”之间切换</span></b>。 差异在报告常见问题解 <a href="../../faq/faq-reporting.md"> 答中说明</a> 。 </p> </td>
  </tr>
 </tbody>
</table>

您可以选择要为其生成报表的特定转换特征，也可以选择所有组合的特征。 您可以定义应返回信息的日期范围并将报告导出为文 [!DNL CSV] 件。

>[!NOTE]
>
>* 测试组的报告将在其开始日期后的某一天填充。
>* 只有在测试开始日期之后和设备添加到测试段之后，才对设备计算转换。 如果该设备在分配测试组之前发生了转换，则不会计算转换。


返回的 **[!UICONTROL Aggregate Reporting]** 图表可能如下：

![](assets/aggregate-reporting.PNG)

返回的 **[!UICONTROL Trend Reporting]** 图表可能与下面的图表类似。 如果 **[!UICONTROL Normalized]** 要忽略绝对数并只关注测试段趋势，请在复选框中选择。

![](assets/trend-reporting.PNG)