---
description: 测试组报告部分返回有关测试组转换的信息，从而可以轻松比较测试段的效果。 有许多过滤器和维度可用于数据可视化。
seo-description: 测试组报告部分返回有关测试组转换的信息，从而可以轻松比较测试段的效果。 有许多过滤器和维度可用于数据可视化。
seo-title: 测试组报表
solution: Audience Manager
title: 测试组报表
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 3%

---

# 测试组报表 {#test-group-reporting}

测试组报告部分返回有关测试组转换的信息，从而可以轻松比较测试段的效果。 有许多过滤器和维度可用于数据可视化。

[!UICONTROL Audience Lab] 返回您创建的测试区段的详细报告信息，并允许您将报告数据保存为 [!DNL CSV] 文件。可以在&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;和&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;之间进行选择。

**[!UICONTROL Aggregate Reporting]** 返回测试区段的绝对数。**[!UICONTROL Trend Reporting]** 返回特定期间 *的趋势图*。四个选项卡允许您自定义报告：

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
   <td colname="col2"> <p>返回显示在测试组中选定的转换特征的设备数。 <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 观看此视</a> 频，了解如何创建转化特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 转换总数</span></b> </p> </td> 
   <td colname="col2"> <p>返回测试区段生成的转换数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 测试区段总体</span></b> </p> </td> 
   <td colname="col2"> <p>返回属于测试区段的设备数。 在<b><span class="uicontrol">总人口</span></b>或<b><span class="uicontrol">实时人口</span></b>之间切换。 差异在<a href="../../faq/faq-reporting.md">报告FAQ</a>中说明。 </p> </td>
  </tr>
 </tbody>
</table>

您可以选择要为其生成报表的特定转换特征，也可以选择所有组合的特征。 您可以定义应返回信息的日期范围，并将报告导出为[!DNL CSV]文件。

>[!NOTE]
>
>* 测试组的报告将在其开始日期后的某天填充。
>* 只对测试开始之后和设备添加到测试段之后的设备计算转换。 如果在为设备分配测试组之前对其进行了转换，则不会计算转换。


返回的&#x200B;**[!UICONTROL Aggregate Reporting]**&#x200B;图表可能如下所示：

![](assets/aggregate-reporting.PNG)

返回的&#x200B;**[!UICONTROL Trend Reporting]**&#x200B;图表可能与下面的图表类似。 如果要忽略绝对数并只关注测试段趋势，请在复选框中选择&#x200B;**[!UICONTROL Normalized]**。

![](assets/trend-reporting.PNG)
