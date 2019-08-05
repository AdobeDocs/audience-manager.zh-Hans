---
description: Audience Marketplace数据购买者同意，根据每千个广告印象(CPM)的成本，使用数据馈送中包含的特征报告所有广告印象。CPM使用将在每个日历月的第天到期，并包含上个月的数据。付费用户无需报告使用情况。
seo-description: Audience Marketplace数据购买者同意，根据每千个广告印象(CPM)的成本，使用数据馈送中包含的特征报告所有广告印象。CPM使用将在每个日历月的第天到期，并包含上个月的数据。付费用户无需报告使用情况。
seo-title: 数据馈送购买者计费
solution: Audience Manager
title: 数据馈送购买者计费
keywords: 细分级别报告、细分级别、细分级别
uuid: d723667-282b-4160-9909-579721af4016
translation-type: tm+mt
source-git-commit: dab5b255f966e63d51cc4d236d37bb0cb4eb960c

---


# 数据馈送购买者计费 {#billing-for-data-feed-buyers}

Audience Marketplace数据购买者同意报告使用每千个广告印象([!DNL CPM])定价的数据馈送中所包含的所有广告印象。[!DNL CPM] 使用将在每个日历月的第天到期，并包含上个月的数据。付费用户无需报告使用情况。

<br> 

## 如何报告CPM使用情况 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 数据购买者同意报告使用每千个广告印象([!DNL CPM])定价的数据馈送所提供的所有广告印象。[!DNL CPM] 使用期限为每个日历月的天，并包含上个月的数据。付费用户无需报告使用情况。

[!UICONTROL Audience Marketplace] 提供了两种报告 [!DNL CPM] 使用情况的方法：

* **细分级别报告**：这是建议 [!DNL CPM] 的使用报告方法。当您在区段级别报告 [!DNL CPM] 使用情况时，数据源级别报告部分会根据CPM数据源成本归因中 [所述的算法自动填充相应的使用金额](#cost-attribution)。
* **数据馈送级别报告**：此方法要求您根据CPM数据源的费用归因中所述的算法单独报告每个数据馈送的 [!DNL CPM][使用情况](#cost-attribution)。但是，与区段级报告相比，此方法比较繁琐，容易出错。

<br> 

## 报告区段级别的CPM使用情况 {#segment-level-report}

[!UICONTROL Segment Usage] 此选项卡允许您报告区段级别使用情况，同时显示按其映射到的目标分组的区段。

在区段级别报告 [!DNL CPM] 使用后， [!UICONTROL Audience Marketplace] 根据CPM数据源 [](#cost-attribution)的成本归因自动分配相应的数据以提供正确的使用。

要在区段级别报告 [!DNL CPM] 使用情况，请执行以下操作：

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;转至。
2. 选择 **[!UICONTROL Segment Usage]** 选项卡。
3. 填写区段使用情况。如果您只需要对部分区段进行报告，则可以使用 [!UICONTROL Search] 该框过滤区段。
4. 单击 **[!UICONTROL Edit Segments Usage]**.
5. 在列中输入 [!DNL CPM] 使用金额 [!UICONTROL Usage] 。
6. 完成后单击 **[!UICONTROL Save]** ，查看确认对话框。
   ![确认区段使用](assets/confirm-segment-usage.png)
7. 单击 **[!UICONTROL Confirm]**.

<br> 

## 报告数据馈送级别的CPM使用情况 {#feed-level-report}

数据源级别报告比较繁琐，容易出错，因为您必须单独计算每个数据源的 [!DNL CPM] 使用情况。我们建议您改为 [在区段级别](#segment-level-report) 报告CPM使用情况。

要在区段级别报告 [!DNL CPM] 使用情况，请执行以下操作：

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;转至。
2. 选择 **[!UICONTROL Feed Usage]** 选项卡。
3. 使用 [!UICONTROL Search] 该框过滤数据服务，并识别您需要报告的数据源。
4. 单击 **[!UICONTROL Edit Feeds Usage]**.
5. 根据CPM [!DNL CPM] 数据源的 [成本归因计算每个数据馈送的使用情况](#cost-attribution)，并在 [!UICONTROL Usage] 列中输入它。
6. 完成后单击 **[!UICONTROL Save]** ，查看确认对话框。

   ![确认源使用](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**.

<br> 

## 批量报告

为了减少报告 [!DNL CPM] 使用时的错误和开销，您可以使用批量报告选项下载包含数据源和区段的 [!DNL CSV] 文件，填写使用情况并将其上传回 [!DNL Audience Manager]。您可以使用批量报告报告源和区段使用情况。

批量更新 [!DNL CPM] 使用情况：

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;转至。
1. 根据要更新的报告类型，选择 **[!UICONTROL Feed Usage]** 或 **[!UICONTROL Segment Usage]** 选项卡。
1. 单击 **[!UICONTROL Edit Feeds Usage]****[!UICONTROL Edit Segments Usage]**&#x200B;或。
1. 单击 **[!UICONTROL download the current usage]** 以确保您使用有效的CSV文件。
1. 在计算机上打开文件并填写使用情况报告。
1. 单击 **[!UICONTROL Choose a CSV file]** 以上传更新后的使用情况报告。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 在上传文件后对其进行验证，并在检测到文件中的任何错误时提示您。

<br> 

### 批量报告验证错误

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 输入无效 | [!DNL Audience Manager] 检测到 [!DNL CSV] 文件架构中的更改，如缺少列或列标题更改。 | 避免更改表结构。 |
| 未找到” | 对于 [!UICONTROL Segment Level Reporting]， [!DNL Audience Manager] 无法识别 [!UICONTROL Segment ID] 和 [!UICONTROL Destination ID] 组合。对于 [!UICONTROL Feed Level Reporting]， [!DNL Audience Manager] 无法识别 [!UICONTROL Data Provider Name]、 [!UICONTROL Feed Name][!UICONTROL Use Case] 和组合。 | 对于 [!UICONTROL Segment Level Reporting]，请检查和 [!UICONTROL Segment ID][!UICONTROL Destination ID] 组合的有效性。对于 [!UICONTROL Feed Level Reporting]，检查 [!UICONTROL Data Provider Name]和 [!UICONTROL Feed Name][!UICONTROL Use Case] 合并的有效性。 |
| 找到的记录重复 | [!DNL Audience Manager] 检测到具有不同印象值的重复记录。 | 查看报告并确保您没有报告相同数据源或区段的不同使用值。 |
| 不支持的值 | [!DNL Audience Manager] 检测到 [!DNL Audience Manager] 列中的非数值。 | 查看报告并确保只在 [!DNL Audience Manager] 列中输入数值。 |
| 必填字段标题缺失 | [!DNL Audience Manager] 检测到必填字段的缺少表标题。对于 [!UICONTROL Segment Level Reporting]，必填字段有： [!UICONTROL Segment ID][!UICONTROL Destination ID].对于 [!UICONTROL Feed Level Reporting]，必填字段有： [!UICONTROL Data Provider Name][!UICONTROL Data Feed Name][!UICONTROL Use Case] | 查看报告并确保表标题未被篡改。 |

>[!NOTE]
>从 [!DNL CSV] 使用报告中删除行对现有使用情况报告没有任何影响。[!DNL Audience Manager] 仅处理报表中包含的字段。

<br> 

## [!DNL CPM] 报告最佳实践

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>始终报告展示次数</b> </p> </td> 
   <td colname="col2"> <p>对于CPM印象总数： </p>
   <p> 报告展示总数，而不使用小数点。Audience Manager会根据您报告的总数字自动计算CPM。</p><p>如果需要报告1,234,567印象，请准确报告。您无需将印象总数除以1,000即可计算CPM。</p><p>使用Adobe Target或Analytics目标等工具优化Web或应用程序内容(内容优化)的特征不会计入CPM计划的使用总数。数据提供商通常使用平面费用计划进行内容优化。</p><p>有关更多信息，请参阅 <a href="#cost-attribution">CPM数据源</a> 成本归因。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>坚持按月报告间隔</b> </p> </td> 
   <td colname="col2"> <p>报告系统在每个月的第5日之后关闭。如果您未能在那时报告CPM使用情况，则必须将该金额添加到下个月的报告中。例如，假设10月在10月内使用了1000次展示，在11月的报告截止日期中使用了1000次印象。在这种情况下，您将报告十二月和十一月(2000)在第一和第五日之间的总计(2000)。</p><p><b>提示</b>：您应始终在下个月的第天和第5日之间报告上一个月的CPM使用情况。</p><p>您可以在新日历月的第5日报告CPM使用情况，但不建议这样做。在每个月的第5日之前报告CPM使用情况可让Audience Manager时间检查和处理数据。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM数据源成本归因 {#cost-attribution}

您必须每月 [!UICONTROL Audience Marketplace] 为每个区段单独报告印象数量。我们建议在细分级别报告 [!DNL CPM] 使用情况，以便自动完成成本归因。

<!-- marketplace_cpm_billing.xml -->

### 帐单摘要 {#billing-summary}

您必须在每个日历月的第一天和第五天之间提交 [!DNL CPM] 数据馈送印象金额。为此，我们建议您 [在区段级别报告CPM使用情况](#segment-level-report)。

>[!TIP]
>当您在区段级别报告 [!DNL CPM] 使用情况时，数据源级别报告部分会自动填入相应的使用金额。

如果需要 [!UICONTROL Report CPM Usage at Data Feed Level]，您必须单独编译上一个日历月为每个源提供的所有展示次数，并根据本文所述的计费分配报告这些印象。

在您为上一日历月报告 [!DNL CPM] 编号后， [!DNL Adobe] 将执行以下操作：

* 创建发票并根据每个订阅数据源 [!DNL CPM] 的费率向您收费。
* 根据您的报告 [!DNL CPM] 使用付费数据提供商(卖家)费用。

>[!IMPORTANT]
>
>作为购买者，所有报告的印象总数必须真实准确。如果您未能在每个月的第天之前报告印象总数，则必须包含下个月未报告月份的总计。

<br> 

## 根据特征资格规则在馈送级别分配印象 {#assign-impressions}

[!UICONTROL Activation] 使用用例，您可以使用相应数据源中的特征在 [区段生成器](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) 中创建区段，并将这些区段映射到目标。Boolean运算符 [!UICONTROL AND][!UICONTROL OR]，允许 [!UICONTROL NOT] 您设置特征和区段资格条件。

当您 [在数据馈送级别](#feed-level-report)报告CPM使用情况时，必须根据特征资格规则中使用 [!DNL Boolean] 的操作符为每个数据馈送分配比例显示。下表列出了如何按Boolean规则或特征类型正确分配印象。

>[!TIP]
>[在细分级别](#segment-level-report) 报告CPM使用情况，以由Audience Manager自动完成数据馈送级别报告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 规则资格逻辑或类型 </th> 
   <th colname="col2" class="entry"> 帐单分发 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>将100%附带的印象总数应用于基于规则的区段中使用Boolean <span class="wintitle"> AND</span> 条件的所有提供者特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或者</span> </p> </td> 
   <td colname="col2"> <p>在使用Boolean OR条件的基于规则的区段中，将呈现的印象总数加权分配给所有提供者特征。加权分配使用以下公式进行计算：</p><p><code>(特征人口/区段人群)*展示次数* CPM成本</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>在使用Boolean <span class="wintitle"> NOT</span> 条件的基于规则的区段中，将100%附带的印象总数应用于所有提供商特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法细分 </p> </td> 
   <td colname="col2"> <p>将100%附带的印象总数应用于包含算法特征的区段中的所有提供者源。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 帐单示例 {#billing-examples}

以下示例旨在说明 [!DNL CPM] 如何在数据馈送级别进行使用分配。

>[!IMPORTANT]
>我们建议您 [在区段级别](#segment-level-report) 报告CPM使用情况，以自动完成此过程。

下面我们来看一下以下情景：

![帐单示例](assets/billing-examples.png)

<br> 

### 案例1：具有和资格规则的细分

此区段包含来自不同数据提供商的个特征。由于细分资格基于某 [!UICONTROL AND] 个条件，因此访客必须从所有三个源中认识到特征才能获得该区段。

![](assets/billing-segment-and.png)

[!UICONTROL AND] 有了条件，您必须将当月内收到的所有印象分配给所有三家数据提供商。[!UICONTROL Audience Marketplace > Payables] 在此部分中，您将为每个提供商提供1,000,000次印象。

此示例适用于使用 [!DNL Boolean][!UICONTROL NOT] 运算符或包含算法特征的区段的区段。

<br> 

### 案例2：具有或资格规则的细分

此区段包含来自不同数据提供商的个特征。由于细分资格基于某 [!UICONTROL OR] 个条件，因此访客必须至少认识到有资格获得该区段的三个特征之一。

我们无法判断有哪些特征会引起印象，因为资格基于条件 [!UICONTROL OR] 。因此 [!UICONTROL Audience Marketplace > Payables] ，在部分中，您根据特征人群加权分配了总印象的加权分配。

![帐单区段或](assets/billing-segment-or.png)

<br> 

### 案例3：具有建模和激活用例的细分

此示例描述了基于两个数据源用例-建模和激活的归因。在示例中，我们将查看两个数据提供程序，其中包括以下信息：

![数据源](assets/feed-use-cases.png)

在下表中，区段X包含两个特征T和T2，其中带有区段规则T1OR T2，其中包括：

* T是数据馈送A的特征；
* T是建模特征，它建模在数据源A和数据源B中的第三方特征之后。

区段会被映射到目标，并使用 [区段级报表](#segment-level-report)在一个月内为该区段输入1,000,000次印象。

1，000,000印象中：

* T占区段人口的40%，为Feed A转换为400,000印象。
* T占区段人口的60%，对Feed A和Feed B转换为600,000印象。

在数据馈送级别，展示次数的方式是：

* 数据馈送A从特征T接收600,000次印象T2(这是基于数据馈送A和数据Feed B的特征，因此都收到了印象)和来自特征T1(数据馈送A的特征)的400,000印象，总计1,000,000印象。
* 数据馈送B从特征T中接收600,000次印象(参见上面的说明)和来自特征T的0印象。

数据馈送和使用案例的一览划分如下：

![feed-breaksation](assets/feed-breakdown-alt.png)

<br> 

## 付费数据馈送计费和印象分配 {#billing-flat-fee}

付费数据服务每月向您收取固定金额，无论订阅开始或您使用的印象数量如何。部分月使用情况或间隔不按比例收费。与CPM计费一样，Adobe将生成发票并为您订阅的数据服务每月支付固定费用。

例如，假设您决定在月中旬开启某个源中的特定特征。无论您何时开始订阅或激活特定特征，您仍将按月费计费。