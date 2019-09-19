---
description: 受众市场数据购买者同意使用数据馈送中包含的特征报告所提供的所有广告印象，这些特征以每千个广告印象(CPM)的成本为基础。 CPM使用将于每个日历月的第5天到期，并包含上个月的数据。 固定费用订阅者无需报告使用情况。
seo-description: 受众市场数据购买者同意使用数据馈送中包含的特征报告所提供的所有广告印象，这些特征以每千个广告印象(CPM)的成本为基础。 CPM使用将于每个日历月的第5天到期，并包含上个月的数据。 固定费用订阅者无需报告使用情况。
seo-title: 数据馈送购买者的计费
solution: Audience Manager
title: 数据馈送购买者的计费
keywords: 分部级报告、分部级别、分部级别
uuid: d7236667-282b-4160-9909-579721af4016
translation-type: tm+mt
source-git-commit: a8320894c0efcf46bd3236494e1aa7b1eded24d1

---


# 数据馈送购买者的计费 {#billing-for-data-feed-buyers}

Audience Marketplace数据购买者同意使用数据馈送中包含的特征报告所提供的所有广告印象([!DNL CPM])，该特征以每千个广告印象的成本为基准。 [!DNL CPM] 使用情况在每个日历月的第5天到期，并包括上个月的数据。 固定费用订阅者无需报告使用情况。

<br> 

## 如何报告CPM使用情况 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 数据购买者同意使用数据馈送中包含的基于每千个广告印象([!DNL CPM])成本的特征报告所有提供的广告印象。 [!DNL CPM] 使用情况在每个日历月的5天到期，并包括上个月的数据。 固定费用订阅者无需报告使用情况。

[!UICONTROL Audience Marketplace] 提供两种报告使用情况 [!DNL CPM] 的方法：

* **细分级报告**:这是推荐的使 [!DNL CPM] 用情况报告方法。 在细分级 [!DNL CPM] 别报告使用情况时，数据馈送级别报告部分会根据CPM数据馈送的成本归因中描述的算法自动填充相应的使用量 [](#cost-attribution)。
* **数据馈送级别报告**:此方法要求您根据CPM数据 [!DNL CPM] 源的成本归因中所述的算法，单独报告每 [个数据源的使用情况](#cost-attribution)。 但是，与细分级报告相比，此方法更加繁琐且容易出错。

<br> 

## 在细分级别报告CPM使用情况 {#segment-level-report}

该选 [!UICONTROL Segment Usage] 项卡允许您报告区段级别使用情况，同时显示按它们映射到的目标分组的区段。

在细分级 [!DNL CPM] 别报告使用情况后， [!UICONTROL Audience Marketplace] 根据CPM数据源的成本归因，自动分配相应的数据源，以 [正确的使用情况](#cost-attribution)。

要报告区段 [!DNL CPM] 级别的使用情况，请执行以下操作：

1. 转到 **[!UICONTROL Audience Marketplace > Payables]**。
1. 选择选 **[!UICONTROL Segment Usage]** 项卡。
1. 填写区段的使用情况。 如果您只需 [!UICONTROL Search] 报告其中某些区段的使用情况，则可以使用该框来筛选区段。
1. 单击 **[!UICONTROL Edit Segments Usage]**.
1. 在列 [!DNL CPM] 中输入使用 [!UICONTROL Usage] 量。
1. 完 **[!UICONTROL Save]** 成后单击并查看确认对话框。

   ![确认段使用](assets/confirm-segment-usage.png)

1. 单击 **[!UICONTROL Confirm]**.

另请观看我们的视频演示，了解如何报告细分级别的使用情况：

>[!VIDEO](https://video.tv.adobe.com/v/25522/?captions=chi_hans)

 

## 在数据馈送级别报告CPM使用情况 {#feed-level-report}

数据馈送级别报告更加繁琐，并且容易出错，因为您必须单独计算每个数 [!DNL CPM] 据馈送的使用情况。 我们建议您改 [为在区段级别报告CPM使用情况](#segment-level-report) 。

要报告区段 [!DNL CPM] 级别的使用情况，请执行以下操作：

1. 转到 **[!UICONTROL Audience Marketplace > Payables]**。
2. 选择选 **[!UICONTROL Feed Usage]** 项卡。
3. 使用该 [!UICONTROL Search] 框可过滤数据源并识别需要报告其使用情况的数据源。
4. 单击 **[!UICONTROL Edit Feeds Usage]**.
5. 根据 [!DNL CPM] CPM数据源的成本归因计算每个数据 [源的使用情况](#cost-attribution)，并在列中输 [!UICONTROL Usage] 入它。
6. 完 **[!UICONTROL Save]** 成后单击并查看确认对话框。

   ![确认信息源使用](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**.

<br> 

## 批量报告

要减少报告使用情况时的错 [!DNL CPM] 误和开销，您可以使用批量报告选项下载包含数据源和区段的文件，填写使用情况，然后将其上传回 [!DNL CSV][!DNL Audience Manager]。 您可以使用批量报告报告源和区段使用情况。

要批量更新 [!DNL CPM] 使用情况，请执行以下操作：

1. 转到 **[!UICONTROL Audience Marketplace > Payables]**。
1. 根据 **[!UICONTROL Feed Usage]** 要更 **[!UICONTROL Segment Usage]** 新的报告类型，选择或选项卡。
1. 单击 **[!UICONTROL Edit Feeds Usage]** 或 **[!UICONTROL Edit Segments Usage]**。
1. 单 **[!UICONTROL download the current usage]** 击以确保使用有效的CSV文件。
1. 打开计算机上的文件并填写使用情况报告。
1. 单击 **[!UICONTROL Choose a CSV file]** 以上传更新的使用情况报告。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 上传文件后立即验证该文件，并在检测到文件中有任何错误时提示您。

<br> 

### 批量报告验证错误

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 输入无效 | [!DNL Audience Manager] 检测到文件架构中 [!DNL CSV] 的更改，如缺少列或对列标题的更改。 | 避免更改表结构。 |
| 未找到” | 因 [!UICONTROL Segment Level Reporting]为， [!DNL Audience Manager] 无法识别 [!UICONTROL Segment ID] 和 [!UICONTROL Destination ID] 组合。 因 [!UICONTROL Feed Level Reporting]为， [!DNL Audience Manager] 无法识别 [!UICONTROL Data Provider Name]、 [!UICONTROL Feed Name]和 [!UICONTROL Use Case] 组合。 | 对于 [!UICONTROL Segment Level Reporting]，请检查和组合的 [!UICONTROL Segment ID] 有效性 [!UICONTROL Destination ID] 。 对 [!UICONTROL Feed Level Reporting]于，检查组合、组合 [!UICONTROL Data Provider Name]的 [!UICONTROL Feed Name]有效性 [!UICONTROL Use Case] 。 |
| 找到重复记录 | [!DNL Audience Manager] 检测到具有不同印象值的重复记录。 | 查看报告，并确保不报告同一数据馈送或区段的不同使用值。 |
| 不支持值 | [!DNL Audience Manager] 检测到列中的非数值 [!DNL Audience Manager] 值。 | 查看报告并确保仅在列中输入数值 [!DNL Audience Manager] 。 |
| 必填字段的标题缺失 | [!DNL Audience Manager] 检测到必填字段缺少表标题。 对 [!UICONTROL Segment Level Reporting]于，必填字段为： [!UICONTROL Segment ID], [!UICONTROL Destination ID]。 对 [!UICONTROL Feed Level Reporting]于，必填字段为： [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name][!UICONTROL Use Case] | 查看报告并确保未篡改表标题。 |

>[!NOTE]
>从使用情况报告 [!DNL CSV] 中删除行对现有的使用情况报告没有任何影响。 [!DNL Audience Manager] 仅处理报告中包含的字段。

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
   <td colname="col1"> <p><b>始终报告展示总数</b> </p> </td> 
   <td colname="col2"> <p>对于CPM印象总数： </p>
   <p> 报告展示总数，不使用小数。 Audience manager会根据您报告的总数自动计算CPM。</p><p>如果您需要报告1,234,567个印象，请完全这样报告。 您无需将展示总数除以1,000即可计算CPM。</p><p>用于使用Adobe Target或Analytics目标等工具优化您的Web或应用程序内容（内容优化）的特征不会计入CPM计划的使用总数。 通常，数据提供商会通过统一费用计划获得内容优化补偿。</p><p>有关更 <a href="#cost-attribution">多信息，请参阅CPM数据源的成本归因</a> 。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>遵守每月报告间隔</b> </p> </td> 
   <td colname="col2"> <p>报告系统每月五号后关闭。 如果到那时未能报告CPM使用情况，则必须将该金额添加到下个月的报告中。 例如，假设您在10月使用1000次展示，错过10月报告截止日期，在11月使用1000次展示。 在本例中，您将在12月1日至5日报告10月和11月的总数（2000年）。</p><p><b>提示</b>:您应始终尝试在下月的第1天至第5天之间报告上个月的CPM使用情况。</p><p>您可以在新日历月的第5天报告CPM使用情况，但不建议这样做。 在每月5日之前报告CPM使用情况，让Audience manager有时间检查和处理数据。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM数据源的成本归因 {#cost-attribution}

在 [!UICONTROL Audience Marketplace] 中，您必须针对每个区段每月自我报告印象金额。 我们建议在 [!DNL CPM] 细分级别报告使用情况，以便自动完成成本归因。

<!-- marketplace_cpm_billing.xml -->

### 开单摘要 {#billing-summary}

您必须提 [!DNL CPM] 交每个日历月第1天至第5天之间的数据馈送印象金额。 为正确执行此操作，我们建议您在区 [段级别报告CPM使用情况](#segment-level-report)。

>[!TIP]
>在区段级 [!DNL CPM] 别报告使用情况时，数据馈送级别报告部分会自动填写相应的使用情况金额。

如果需要，您必 [!UICONTROL Report CPM Usage at Data Feed Level]须单独编译上一个日历月中为每个订阅源交付的所有印象，并根据本文所述的计费分配报告这些印象。

在您报告 [!DNL CPM] 上一个日历月的编号后， [!DNL Adobe] 将执行以下操作：

* 根据每个订阅数据馈送的费率 [!DNL CPM] 创建发票和帐单。
* 根据您所报告的使用情况，向数据提供商（销售商）支付所欠费 [!DNL CPM] 用。

>[!IMPORTANT]
>
>作为买家，所有报告的印象总数必须真实而准确。 如果在每月的第5天之前未报告印象总数，则必须包括下个月未报告月份的总数。

<br> 

## 根据特征资格规则在信息源级别分配展示次数 {#assign-impressions}

使用 [!UICONTROL Activation] 案例，您可以在相应的数据源中使用特征，在 [Segment Builder中创建区段](../../../features/segments/segment-builder.md) ，并将这些区段映射到目标。 布尔运算符 [!UICONTROL AND]、 [!UICONTROL OR]和 [!UICONTROL NOT] 允许您设置特征和段资格条件。

在数据 [馈送级别报告CPM使用情况时](#feed-level-report)，您必须根据特征资格规则中使用的操作符，按比例分配每个数据馈送 [!DNL Boolean] 的展示次数。 下表列出了如何按布尔规则或特征类型正确分配展示次数。

>[!TIP]
>[在细分级别报告CPM使用情况](#segment-level-report) ，以使Audience manager自动完成数据馈送级别报告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 规则资格逻辑或类型 </th> 
   <th colname="col2" class="entry"> 帐单分发 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 和</span> </p> </td> 
   <td colname="col2"> <p>将100%的已交付印象总数应用到使用Boolean <span class="wintitle"> AND条件的基于规则的区段中的所有提供者特征</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或者</span> </p> </td> 
   <td colname="col2"> <p>对使用Boolean OR条件的基于规则的区段中的所有提供者特征应用已交付印象总数的加权分配。 加权分配乃使用以下公式计算：</p><p><code>（特征人口／区段人口）*展示次数* CPM成本</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>将100%的已交付印象总数应用到使用Boolean <span class="wintitle"> NOT条件的基于规则的区段中的所有提供者特征</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法段 </p> </td> 
   <td colname="col2"> <p>将100%的交付印象总数应用到包含算法特征的区段中的所有提供商源。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 计费示例 {#billing-examples}

以下示例旨在说明如何在数 [!DNL CPM] 据馈送级别进行使用分配。

>[!IMPORTANT]
>我们建议您改 [为在区段级别报告CPM使用情况](#segment-level-report) ，以自动完成此过程。

让我们考虑以下情形：

![billing-examples](assets/billing-examples.png)

<br> 

### 案例1:具有和资格规则的细分

此区段包含来自不同数据提供者的3个特征。 由于区段资格基于某个条 [!UICONTROL AND] 件，访客必须从所有三个源中实现特征才能获得区段资格。

![](assets/billing-segment-and.png)

有了某 [!UICONTROL AND] 个条件，您必须将当月收到的印象的100%分配给所有三个数据提供商。 在该部 [!UICONTROL Audience Marketplace > Payables] 分中，您将每个提供商的印象记为1,000,000。

此示例适用于使用运算符的 [!DNL Boolean] 段或 [!UICONTROL NOT] 包含算法特征的段。

<br> 

### 案例2:具有或资格规则的细分

此区段包含来自不同数据提供者的3个特征。 由于区段资格基于某个条 [!UICONTROL OR] 件，因此访客必须实现三个特征中的至少一个才能符合区段资格。

我们无法判断哪个特质对印象负责，因为资格是基于某个条 [!UICONTROL OR] 件的。 因此，在此部分中，您 [!UICONTROL Audience Marketplace > Payables] 为每个提供者提供基于特征人口的总印象的加权分配。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 案例3:具有建模和激活用例的细分

此示例基于两个数据馈送用例（建模和激活）描述归因。 在本例中，我们查看两个数据提供者，其中包含以下信息：

![数据馈送](assets/feed-use-cases.png)

在下表中，区段X包含两个特征，即T1和T2，区段规则为T1或T2，其中：

* T1是数据源A的一个特征；
* T2是基于Data Feed a和Data Feed b的第三方特征建模的算法特征。

区段将映射到目标，并且使用区段级别报告在一个月内为此区段输入1,000,000 [个印象](#segment-level-report)。

在这1,000,000个印象中：

* T1占细分人口的40%，这意味着Feed a有400,000个印象。
* T2占细分人口的60%，这意味着Feed a和Feed b的印象为600,000。

在数据馈送级别，展示次数的分配方式是：

* 数据馈送A从特征T2接收600,000次展示（该展示基于来自数据馈送A和数据馈送B的特征，因此两者都会接收展示），从特征T1接收400,000次展示（来自数据馈送A的特征），总展示数为1,000,000次。
* 数据馈送B从特征T2接收600,000次展示（请参阅上面的说明），从特征T1接收0次展示。

按数据馈送和用例的一览表细分如下：

![feed-breakdown](assets/feed-breakdown-alt.png)

<br> 

##  统一费用数据源的计费和印象分配 {#billing-flat-fee}

统一费用数据馈送每月向您收取固定金额，而不管订阅何时开始或您使用的展示次数。 部分月份使用情况或间隔不按比例收费。 与CPM开单一样，Adobe将为您的订阅数据馈送生成发票，并按每月统一的费用向您开具帐单。

例如，假设您在月中旬决定打开某个源中的某些特征。 无论您是在何时开始订阅或激活特定特征，您仍将按每月全额计费。