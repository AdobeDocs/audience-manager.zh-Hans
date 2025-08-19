---
description: Audience Marketplace数据购买者同意报告使用数据馈送中包含的特征提供的所有广告展示次数，这些特征按每千广告展示次数(CPM)的成本定价。 CPM的使用截止日期是每个日历月的第5天，其中包括上个月的数据。 固定费用订阅者无需报告使用情况。
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: 面向数据信息源购买者的账单
keywords: 分部级别报告、分部级别报告、分部级别报告
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# 面向数据信息源购买者的账单 {#billing-for-data-feed-buyers}

Audience Marketplace数据购买者同意报告使用数据馈送中包含的特征提供的所有广告展示次数，这些特征按每千个广告展示次数([!DNL CPM])的成本定价。 [!DNL CPM]的使用截止日期是每个日历月的第5天，其中包括上个月的数据。 固定费用订阅者无需报告使用情况。

<br> 

## 如何报告CPM使用情况 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace]数据购买者同意报告使用数据馈送中包含的特征提供的所有广告展示次数，这些特征按每千个广告展示次数([!DNL CPM])的成本定价。 [!DNL CPM]的使用截止日期是每个日历月的5天，其中包括上个月的数据。 固定费用订阅者无需报告使用情况。

[!UICONTROL Audience Marketplace]提供两种报告[!DNL CPM]使用情况的方法：

* **区段级别报表**：这是推荐的[!DNL CPM]使用情况报表方法。 当您在区段级别报告[!DNL CPM]的使用情况时，数据馈送级别的报告部分会自动根据[CPM数据馈送的成本归因](#cost-attribution)中描述的算法填入相应的使用量。
* **数据馈送级别报告**：此方法要求您根据[!DNL CPM]CPM数据馈送的成本归因[中描述的算法，单独报告每个数据馈送的](#cost-attribution)使用情况。 但是，与区段级别的报告相比，此方法更繁琐且容易出错。

<br> 

## 报告CPM在区段级别的使用情况 {#segment-level-report}

[!UICONTROL Segment Usage]选项卡允许您报告区段级别的使用情况，同时显示按区段所映射到的目标分组的区段。

在报告区段级别的[!DNL CPM]使用情况后，[!UICONTROL Audience Marketplace]会根据CPM数据馈送的[成本归因](#cost-attribution)，自动分配相应的数据馈送的正确使用情况。

要报告区段级别的[!DNL CPM]使用情况，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 选择&#x200B;**[!UICONTROL Segment Usage]**&#x200B;选项卡。
1. 填写区段的用法。 如果只需要报告某些区段的使用情况，则可以使用[!UICONTROL Search]框筛选区段。
1. 单击 **[!UICONTROL Edit Segments Usage]**。
1. 在[!DNL CPM]列中输入[!UICONTROL Usage]使用量。
1. 完成后，单击&#x200B;**[!UICONTROL Save]**&#x200B;并查看确认对话框。

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. 单击 **[!UICONTROL Confirm]**。

另请观看我们的视频演示，以了解如何报告区段级别的使用情况：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 报告数据馈送级别的CPM使用情况 {#feed-level-report}

数据馈送级别的报告比较繁琐，并且容易出错，因为您必须单独计算每个数据馈送的[!DNL CPM]使用情况。 我们建议您[改为报告区段级别](#segment-level-report)的CPM使用情况。

要报告区段级别的[!DNL CPM]使用情况，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
2. 选择&#x200B;**[!UICONTROL Feed Usage]**&#x200B;选项卡。
3. 使用[!UICONTROL Search]框筛选数据馈送，并确定需要报告使用情况的数据馈送。
4. 单击 **[!UICONTROL Edit Feeds Usage]**。
5. 根据CPM数据馈送的[!DNL CPM]成本归因[计算每个数据馈送的](#cost-attribution)使用情况，并在[!UICONTROL Usage]列中输入该值。
6. 完成后，单击&#x200B;**[!UICONTROL Save]**&#x200B;并查看确认对话框。

   ![确认信息源使用情况](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**。

<br> 

## 批量报告

为了减少报告[!DNL CPM]使用情况时的错误和开销，您可以使用批量报告选项下载包含数据馈送和区段的[!DNL CSV]文件、填写使用情况并将其上传回[!DNL Audience Manager]。 您可以使用批量报告功能来报告信息源使用情况以及区段使用情况。

要批量更新[!DNL CPM]使用情况，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 选择&#x200B;**[!UICONTROL Feed Usage]**&#x200B;或&#x200B;**[!UICONTROL Segment Usage]**&#x200B;选项卡，具体取决于要更新的报告类型。
1. 单击&#x200B;**[!UICONTROL Edit Feeds Usage]**&#x200B;或&#x200B;**[!UICONTROL Edit Segments Usage]**。
1. 单击&#x200B;**[!UICONTROL download the current usage]**&#x200B;以确保您使用有效的CSV文件。
1. 在计算机上打开文件并填写使用情况报告。
1. 单击&#x200B;**[!UICONTROL Choose a CSV file]**&#x200B;以上传更新的使用情况报告。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager]会在您上传文件后立即验证该文件，并在文件检测到错误时提示您。

<br> 

### 批量报告验证错误

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 输入无效 | [!DNL Audience Manager]在[!DNL CSV]文件架构中检测到更改，如缺少列或更改列标题。 | 避免更改表结构。 |
| 未找到” | 对于[!UICONTROL Segment Level Reporting]，[!DNL Audience Manager]无法识别[!UICONTROL Segment ID]和[!UICONTROL Destination ID]组合。 对于[!UICONTROL Feed Level Reporting]，[!DNL Audience Manager]无法识别[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]组合。 | 对于[!UICONTROL Segment Level Reporting]，检查[!UICONTROL Segment ID]和[!UICONTROL Destination ID]组合的有效性。 对于[!UICONTROL Feed Level Reporting]，检查[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]组合的有效性。 |
| 发现重复记录 | [!DNL Audience Manager]检测到具有不同展示值的重复记录。 | 查看报表，并确保不会为同一数据馈送或区段报告不同的使用值。 |
| 值不受支持 | [!DNL Audience Manager]在[!DNL Audience Manager]列中检测到非数值。 | 查看报告并确保仅在[!DNL Audience Manager]列中输入数值。 |
| 必填字段的标题缺失 | [!DNL Audience Manager]检测到必填字段缺少表标题。 对于[!UICONTROL Segment Level Reporting]，必填字段为： [!UICONTROL Segment ID]，[!UICONTROL Destination ID]。 对于[!UICONTROL Feed Level Reporting]，必填字段为： [!UICONTROL Data Provider Name]、[!UICONTROL Data Feed Name]、[!UICONTROL Use Case] | 查看报告并确保表头未被篡改。 |

>[!NOTE]
>从[!DNL CSV]使用情况报告中删除行对现有使用情况报告没有任何影响。 [!DNL Audience Manager]仅处理报告中包含的字段。

<br> 

## [!DNL CPM]报告最佳实践

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>始终报告展示总数</b> </p> </td> 
   <td colname="col2"> <p>对于CPM展示总数： </p>
   <p> 报告展示总数，但不使用小数。 Audience Manager会根据您报告的总数自动计算CPM。</p><p>如果您需要报告1,234,567次展示，请如实报告。 您无需将展示总数除以1,000即可计算CPM。</p><p>用于使用Adobe Target或Analytics目标等工具优化Web或应用程序内容（内容优化）的特征不会增加CPM计划的总使用量。 数据提供商通常使用固定费用计划获得内容优化的补偿。</p><p>有关详细信息，请参阅<a href="#cost-attribution">CPM数据馈送的成本归因</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>坚持每月报告间隔</b> </p> </td> 
   <td colname="col2"> <p>报表系统在每月5日后关闭。 如果到时未能报告CPM使用情况，则必须将该数量添加到下个月的报表中。 例如，假设您在10月使用1000次展示，错过10月的报告截止日期，在11月使用1000次展示。 在本例中，您报告10月和11月总计（2000年）12月，即1日至5日之间。</p><p><b>提示</b>：您应始终尝试在下个月的第1天和第5天之间报告上个月的CPM使用情况。</p><p>您最迟可以在新日历月5日报告CPM的使用情况，但不建议这样做。 在每月5号之前报告CPM使用情况，可让Audience Manager有时间检查和处理数据。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM数据馈送的成本归因 {#cost-attribution}

在[!UICONTROL Audience Marketplace]中，您必须每月自助报告每个区段的展示金额。 我们建议在区段级别报告[!DNL CPM]使用情况，以便自动进行成本归因。

<!-- marketplace_cpm_billing.xml -->

### 计费摘要 {#billing-summary}

在每个日历月的第1天和第5天之间，您必须提交[!DNL CPM]数据馈送展示金额。 要正确执行此操作，我们建议您[报告区段级别](#segment-level-report)的CPM使用情况。

>[!TIP]
>在区段级别报告[!DNL CPM]使用情况时，数据馈送级别的报告部分会自动填充相应的使用情况金额。

如果您需要[!UICONTROL Report CPM Usage at Data Feed Level]，则必须单独编译每个信息源在上一个日历月交付的所有展示次数，并根据本文中所述的计费分配报告这些展示次数。

在您报告上一个日历月的[!DNL CPM]数字后，[!DNL Adobe]将执行以下操作：

* 根据每个订阅的数据馈送的[!DNL CPM]费率创建发票和账单。
* 根据您报告的[!DNL CPM]使用情况支付数据提供商（销售商）所缺费用。

>[!IMPORTANT]
>
>作为购买者，所有报告的展示总数都必须真实而准确。 如果您没有在每月第5天之前报告展示总计，则必须包含下个月未报告月份的总数。

<br> 

## 根据特征资格规则在信息源级别分配展示 {#assign-impressions}

[!UICONTROL Activation]用例允许您在对应的数据馈送中使用特征在[区段生成器](../../../features/segments/segment-builder.md)中创建区段并将这些区段映射到目标。 布尔运算符[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]允许您设置特征和区段资格条件。

当您[报告数据馈送级别](#feed-level-report)的CPM使用情况时，必须根据特征资格规则中使用的[!DNL Boolean]运算符，按比例为每个数据馈送分配展示次数。 下表列出了如何按布尔规则或特征类型正确分配展示。

>[!TIP]
>[报告CPM在区段级别](#segment-level-report)的使用情况，以使Audience Manager自动完成数据馈送级别的报告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 规则限定逻辑或类型 </th> 
   <th colname="col2" class="entry"> 计费分配 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">和</span> </p> </td> 
   <td colname="col2"> <p>在使用布尔<span class="wintitle">和</span>条件的基于规则的区段中，将投放的展示次数总计100%应用于所有提供程序特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">或</span> </p> </td> 
   <td colname="col2"> <p>在基于规则的区段（使用Boolean OR条件）中，将投放展示次数总计的加权分配应用于所有提供商特征。 加权分配使用以下公式计算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>将100%的投放展示次数合计应用于基于规则的区段中的所有提供程序特征，该区段使用布尔值<span class="wintitle"> NOT</span>条件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法区段 </p> </td> 
   <td colname="col2"> <p>将100%的投放展示总数应用到包含算法特征的区段中的所有提供商馈送。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 计费示例 {#billing-examples}

以下示例旨在说明如何在数据馈送级别进行[!DNL CPM]使用情况分配。

>[!IMPORTANT]
>我们建议您[改为报告区段级别](#segment-level-report)的CPM使用情况，以自动完成此过程。

让我们考虑以下方案：

![计费示例](assets/billing-examples.png)

<br> 

### 案例1：具有AND资格规则的区段

此区段包含来自单独数据提供商的3个特征。 由于区段鉴别基于[!UICONTROL AND]条件，因此访客必须实现所有三个馈送中的特征才能获得该区段的鉴别资格。

![](assets/billing-segment-and.png)

如果具有[!UICONTROL AND]条件，则必须将当月收到的100%展示次数分配给所有三个数据提供程序。 在[!UICONTROL Audience Marketplace > Payables]部分中，您向每个提供商分配了1,000,000次展示。

此示例适用于使用[!DNL Boolean] [!UICONTROL NOT]运算符的区段或包含算法特征的区段。

<br> 

### 案例2：具有OR资格规则的区段

此区段包含来自单独数据提供商的3个特征。 由于区段鉴别基于[!UICONTROL OR]条件，因此访客必须实现三个特征中的至少一个才能获得该区段的鉴别资格。

我们无法分辨哪个特征导致了展示，因为资格鉴定基于[!UICONTROL OR]条件。 因此，在[!UICONTROL Audience Marketplace > Payables]部分中，您将按基于特征群体的总展示次数加权分配为每个提供商评分。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 案例3：具有建模和激活用例的区段

此示例介绍基于两个数据馈送用例的归因 — 建模和激活。 在本例中，我们将查看两个数据提供程序，并提供以下信息：

![数据馈送](assets/feed-use-cases.png)

在下表中，区段X包含两个特征T1和T2，区段规则T1或T2，其中：

* T1是数据馈送A中的特征；
* T2是根据数据馈送A和数据馈送B中的第三方特征建模的算法特征。

该区段已映射到目标，并使用[区段级别报表](#segment-level-report)在一个月内为此区段输入1,000,000次展示。

在这100万次展示中：

* T1占区段人口的40%，这意味着对信息源A的展示次数为400,000。
* T2占区段人口的60%，这意味着对信息源A和信息源B的展示次数为600,000。

在数据馈送级别，展示的分配方式为：

* 数据馈送A从特征T2（基于数据馈送A和数据馈送B的特征建模，因此都接收展示次数）接收600,000次展示，从特征T1（数据馈送A的特征）接收400,000次展示，总计为1,000,000次展示。
* 数据馈送B从特征T2接收600,000次展示（请参阅上面的说明），从特征T1接收0次展示。

按数据馈送和用例划分的概览如下所示：

![信息源划分](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>对于建模用例，您应仅报告激活时的CPM使用情况。 如果只运行模型，但不激活模型，则不需要使用情况报表。

<br> 

## 固定费用数据馈送的计费和展示分配 {#billing-flat-fee}

固定费用数据馈送每月向您收取固定金额，无论订阅何时开始或者您使用多少展示次数。 对于部分月份的使用或间隔，不会按比例分摊费用。 与CPM计费一样，Adobe将为您订阅的数据馈送生成发票，并按每月固定费率对您计费。

例如，假设您决定在月中打开某个信息源中的某些特征。 无论您何时开始订阅或激活了特定特征，仍会按每月完整费率向您计费。
