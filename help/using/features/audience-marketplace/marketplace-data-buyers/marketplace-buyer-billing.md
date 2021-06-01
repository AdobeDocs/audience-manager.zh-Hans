---
description: Audience Marketplace数据购买者同意使用数据馈送中包含的特征来报告提供的所有广告展示次数，该特征以每千个广告展示次数(CPM)的成本为基础进行定价。 CPM使用情况在每个日历月的第5天到期，并包含上个月的数据。 固定费用订阅者无需报告使用情况。
seo-description: Audience Marketplace数据购买者同意使用数据馈送中包含的特征来报告提供的所有广告展示次数，该特征以每千个广告展示次数(CPM)的成本为基础进行定价。 CPM使用情况在每个日历月的第5天到期，并包含上个月的数据。 固定费用订阅者无需报告使用情况。
seo-title: 面向数据信息源购买者的账单
solution: Audience Manager
title: 面向数据信息源购买者的账单
keywords: 区段级别报表、区段级别、区段级别
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2064'
ht-degree: 1%

---

# 面向数据信息源购买者的账单 {#billing-for-data-feed-buyers}

Audience Marketplace数据购买者同意使用数据馈送中包含的特征来报告提供的所有广告展示次数，该特征以每千个广告展示次数([!DNL CPM])为基础进行定价。 [!DNL CPM] 使用情况在每个日历月的第5天到期，并包含上个月的数据。固定费用订阅者无需报告使用情况。

<br> 

## 如何报告CPM使用情况{#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 数据购买者同意使用数据馈送中包含的特征来报告提供的所有广告展示次数([!DNL CPM])，该特征以每千个广告展示次数的成本为基础进行定价。[!DNL CPM] 使用情况在每个日历月的5天到期，并包含上个月的数据。固定费用订阅者无需报告使用情况。

[!UICONTROL Audience Marketplace] 提供了两种报告使用情况 [!DNL CPM] 的方法：

* **区段级别报表**:这是推荐的使 [!DNL CPM] 用情况报告方法。在区段级别报告[!DNL CPM]使用情况时，数据馈送级别报告部分会根据[CPM数据馈送成本归因](#cost-attribution)中描述的算法自动填充相应的使用额。
* **数据馈送级别的报告**:此方法要求您根据CPM数 [!DNL CPM] 据馈送的成本归因 [中描述的算法，逐个报告每个数据馈送](#cost-attribution)的使用情况。但是，与区段级别的报表相比，此方法更加繁琐，而且容易出错。

<br> 

## 区段级别{#segment-level-report}的报表CPM使用情况

[!UICONTROL Segment Usage]选项卡允许您报告区段级别的使用情况，同时显示按区段映射到的目标分组的区段。

在报告区段级别的[!DNL CPM]使用情况后， [!UICONTROL Audience Marketplace]会根据[CPM数据馈送的成本归因](#cost-attribution)自动分配相应的数据馈送正确的使用情况。

要报告区段级别的[!DNL CPM]使用情况，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 选择&#x200B;**[!UICONTROL Segment Usage]**&#x200B;选项卡。
1. 填写区段的使用情况。 如果您只需要报告其中某些区段的使用情况，则可以使用[!UICONTROL Search]框过滤区段。
1. 单击 **[!UICONTROL Edit Segments Usage]**.
1. 在[!UICONTROL Usage]列中输入[!DNL CPM]使用量。
1. 完成后，单击&#x200B;**[!UICONTROL Save]**&#x200B;并查看确认对话框。

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. 单击 **[!UICONTROL Confirm]**.

另请观看我们的视频演示，了解如何报告区段级别的使用情况：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 数据馈送级别{#feed-level-report}的报表CPM使用情况

数据馈送级别的报告更加繁琐，而且容易出现错误过程，因为您必须单独计算每个数据馈送的[!DNL CPM]使用情况。 我们建议您改为[在区段级别](#segment-level-report)报告CPM使用情况。

要报告区段级别的[!DNL CPM]使用情况，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
2. 选择&#x200B;**[!UICONTROL Feed Usage]**&#x200B;选项卡。
3. 使用[!UICONTROL Search]框过滤数据馈送，并确定需要报告其使用情况的数据馈送。
4. 单击 **[!UICONTROL Edit Feeds Usage]**.
5. 根据[CPM数据馈送的成本归因](#cost-attribution)计算每个数据馈送的[!DNL CPM]使用情况，并在[!UICONTROL Usage]列中输入。
6. 完成后，单击&#x200B;**[!UICONTROL Save]**&#x200B;并查看确认对话框。

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**.

<br> 

## 批量报告

为了减少报告[!DNL CPM]使用情况时出现的错误和开销，您可以使用批量报告选项下载包含数据馈送和区段的[!DNL CSV]文件，填写使用情况，然后将其上载回[!DNL Audience Manager]。 您可以使用批量报表来报告信息源和区段使用情况。

要批量更新[!DNL CPM]使用情况，请执行以下操作：

1. 转到&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 选择&#x200B;**[!UICONTROL Feed Usage]**&#x200B;或&#x200B;**[!UICONTROL Segment Usage]**&#x200B;选项卡，具体取决于要更新的报表类型。
1. 单击&#x200B;**[!UICONTROL Edit Feeds Usage]**&#x200B;或&#x200B;**[!UICONTROL Edit Segments Usage]**。
1. 单击&#x200B;**[!UICONTROL download the current usage]**&#x200B;以确保使用有效的CSV文件。
1. 在计算机上打开文件并填写使用情况报告。
1. 单击&#x200B;**[!UICONTROL Choose a CSV file]**&#x200B;以上传更新的使用情况报表。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 上载文件后会立即验证该文件，并在检测到文件中存在任何错误时提示您。

<br> 

### 批量报表验证错误

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 输入无效 | [!DNL Audience Manager] 检测到文件架 [!DNL CSV] 构中的更改，如缺少列或列标题的更改。 | 避免更改表结构。 |
| 未找到” | 对于[!UICONTROL Segment Level Reporting],[!DNL Audience Manager]无法识别[!UICONTROL Segment ID]和[!UICONTROL Destination ID]组合。 对于[!UICONTROL Feed Level Reporting],[!DNL Audience Manager]无法识别[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]组合。 | 对于[!UICONTROL Segment Level Reporting]，检查[!UICONTROL Segment ID]和[!UICONTROL Destination ID]组合的有效性。 对于[!UICONTROL Feed Level Reporting]，检查[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]组合的有效性。 |
| 找到重复记录 | [!DNL Audience Manager] 检测到具有不同展示值的重复记录。 | 查看报表，并确保不针对同一数据馈送或区段报告不同的使用值。 |
| 不支持的值 | [!DNL Audience Manager] 检测到列中的非数值 [!DNL Audience Manager] 。 | 查看报表，并确保只在[!DNL Audience Manager]列中输入数值。 |
| 缺少必填字段的标题 | [!DNL Audience Manager] 检测到必填字段缺少表标题。对于[!UICONTROL Segment Level Reporting]，必填字段为：[!UICONTROL Segment ID]、[!UICONTROL Destination ID]。 对于[!UICONTROL Feed Level Reporting]，必填字段为：[!UICONTROL Data Provider Name]、[!UICONTROL Data Feed Name]、[!UICONTROL Use Case] | 查看报表，并确保表标题未被篡改。 |

>[!NOTE]
>从[!DNL CSV]使用情况报表中删除行对现有使用情况报表没有任何影响。 [!DNL Audience Manager] 仅处理报表中包含的字段。

<br> 

## [!DNL CPM] 报表最佳实践

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>始终报告总展示次数</b> </p> </td> 
   <td colname="col2"> <p>对于CPM展示总数： </p>
   <p> 报告展示总次数，不使用小数。 Audience Manager会根据您报告的总数自动计算CPM。</p><p>如果需要报告1,234,567次展示次数，则报告情况与此完全相同。 您无需将总展示次数除以1,000即可计算CPM。</p><p>使用Adobe Target或Analytics目标等工具优化Web或应用程序内容（内容优化）的特征不会对CPM计划的使用总数产生任何影响。 数据提供商通常会使用固定费用计划对内容优化进行补偿。</p><p>有关更多信息，请参阅<a href="#cost-attribution">CPM数据馈送的成本归因</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>按月报告间隔执行</b> </p> </td> 
   <td colname="col2"> <p>报表系统于每月五日后关闭。 如果您当时未能报告CPM使用情况，则必须将该金额添加到下个月的报表中。 例如，假设您在10月使用1000次展示次数，在10月的报表截止日期之前没有使用，而在11月使用1000次展示次数。 在这种情况下，您将在12月1日至5日期间报告10月和11月的总计（2000年）。</p><p><b>提示</b>:您应始终尝试在下月的第1天至第5天之间报告上个月的CPM使用情况。</p><p>您可以报告迟于新日历月5日的CPM使用情况，但不建议这样做。 在每月5日之前报告CPM使用情况，可为Audience Manager提供检查和处理数据的时间。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM数据馈送{#cost-attribution}的成本归因

在[!UICONTROL Audience Marketplace]中，您必须每月为每个区段自行报告展示数量。 我们建议在区段级别报告[!DNL CPM]使用情况，以便自动完成成本归因。

<!-- marketplace_cpm_billing.xml -->

### 帐单摘要{#billing-summary}

您必须在每个日历月的第1天和第5天之间提交[!DNL CPM]数据馈送展示金额。 要正确执行此操作，我们建议您[在区段级别](#segment-level-report)报告CPM使用情况。

>[!TIP]
>在区段级别报告[!DNL CPM]使用情况时，数据馈送级别报告部分会自动填充相应的使用额。

如果您需要[!UICONTROL Report CPM Usage at Data Feed Level]，则必须单独编译上一个日历月中每个馈送交付的所有展示次数，并根据本文中描述的账单分配进行报告。

在报告上一个日历月的[!DNL CPM]数字后，[!DNL Adobe]将执行以下操作：

* 根据每个订阅数据馈送的[!DNL CPM]费率创建发票和帐单。
* 根据您报告的[!DNL CPM]使用情况，向数据提供商（销售商）支付所欠费用。

>[!IMPORTANT]
>
>作为买方，所有报告的展示次数总计必须真实而准确。 如果您未能在每月的第5天之前报告展示总数，则必须包括下个月未报告月份的总数。

<br> 

## 根据特征鉴别规则{#assign-impressions}在信息源级别分配展示次数

通过[!UICONTROL Activation]用例，您可以在相应的数据馈送中使用特征在[区段生成器](../../../features/segments/segment-builder.md)中创建区段，并将这些区段映射到目标。 布尔运算符[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]允许您设置特征和区段鉴别条件。

当您[在数据馈送级别](#feed-level-report)报告CPM使用情况时，必须根据特征鉴别规则中使用的[!DNL Boolean]运算符，按比例为每个数据馈送分配展示次数。 下表列出了如何按布尔规则或特征类型正确分配展示次数。

>[!TIP]
>[区段级别的报表CPM使用情况](#segment-level-report)，以便数据馈送级别报告由Audience Manager自动完成。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 规则鉴别逻辑或类型 </th> 
   <th colname="col2" class="entry"> 账单分发 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 且</span> </p> </td> 
   <td colname="col2"> <p>在使用布尔值<span class="wintitle"> AND</span>条件的基于规则的区段中，将100%的投放展示次数总计应用于所有提供者特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或者</span> </p> </td> 
   <td colname="col2"> <p>在使用布尔OR条件的基于规则的区段中，将交付展示次数总数的加权分配应用于所有提供者特征。 加权分配使用以下公式计算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>在使用布尔值<span class="wintitle"> NOT</span>条件的基于规则的区段中，将100%的投放展示次数总计应用于所有提供者特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法区段 </p> </td> 
   <td colname="col2"> <p>将100%的投放展示次数总计应用于包含算法特征的区段中的所有提供商馈送。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 帐单示例{#billing-examples}

以下示例用于说明如何在数据馈送级别分配[!DNL CPM]使用情况。

>[!IMPORTANT]
>我们建议您改为在区段级别[报告CPM使用情况](#segment-level-report)，以自动完成此过程。

让我们考虑以下情景：

![计费示例](assets/billing-examples.png)

<br> 

### 用例1:具有和资格规则的区段

此区段包含来自不同数据提供程序的3个特征。 由于区段鉴别基于[!UICONTROL AND]条件，因此访客必须实现所有三个信息源的特征才能符合区段的资格条件。

![](assets/billing-segment-and.png)

对于[!UICONTROL AND]条件，您必须将当月收到的展示次数的100%分配给所有三个数据提供商。 在[!UICONTROL Audience Marketplace > Payables]部分中，您对每个提供商的展示次数为1,000,000。

此示例适用于使用[!DNL Boolean] [!UICONTROL NOT]运算符的区段，或适用于包含算法特征的区段。

<br> 

### 用例2:具有或资格规则的区段

此区段包含来自不同数据提供程序的3个特征。 由于区段鉴别基于[!UICONTROL OR]条件，因此访客必须实现三个特征中的至少一个才能符合区段的鉴别条件。

我们无法判断哪个特征对展示次数负责，因为资格条件基于[!UICONTROL OR]条件。 因此，在[!UICONTROL Audience Marketplace > Payables]部分中，您根据特征人口对每个提供商的总展示次数进行加权分配，以对其进行计数。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 用例3:具有建模和激活用例的区段

此示例描述了基于两个数据馈送用例（建模和激活）的归因。 在此示例中，我们查看了两个数据提供程序，其中包含以下信息：

![数据馈送](assets/feed-use-cases.png)

在下表的进一步内容中，区段X包含两个特征：T1和T2，区段规则为T1或T2，其中：

* T1是数据馈送A的一个特征；
* T2是以数据馈送A和数据馈送B中的第三方特征为模型的算法特征。

该区段会映射到一个目标，并且使用[区段级别报表](#segment-level-report)在一个月内为此区段输入1,000,000个展示次数。

在这1,000,000次展示中：

* T1占区段人口的40%，对于信息源A，这意味着有400,000次展示。
* T2占区段人口的60%，对于信息源A和信息源B，这意味着有600,000次展示。

在数据馈送级别，展示次数的分配方式是：

* 数据馈送A从特征T2接收600,000次展示次数（该特征基于数据馈送A和数据馈送B的特征建模，因此两者均会接收展示次数），从特征T1接收400,000次展示次数（即数据馈送A的特征），总展示次数为1,000,000次。
* 数据馈送B从特征T2接收600,000次展示（请参阅上面的说明），从特征T1接收0次展示。

按数据馈送和用例的概览划分如下：

![信息源划分](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>对于建模用例，您应仅在激活时报告CPM使用情况。 如果您只运行模型，但未激活模型，则无需报告使用情况。

<br> 

## 固定费用数据馈送的账单和展示次数分配{#billing-flat-fee}

无论订阅何时开始或您使用多少展示次数，固定费用数据馈送每月都会向您收取固定金额的费用。 部分月份使用或间隔不按比例收费。 与CPM账单一样，Adobe将为您订阅的数据馈送生成发票，并按每月固定费率向您开单。

例如，假设您在月中决定在动态消息中启用某些特征。 无论您是在何时开始订阅或激活特定特征，都将按月全额计费。
