---
description: Audience Marketplace数据购买者同意使用数据馈送中包含的根据每千个广告展示次数(CPM)定价的特征报告所有提供的广告展示次数。 CPM使用情况在每个日历月的第5天到期，包括上个月的数据。 固定费用订阅者无需报告使用情况。
seo-description: Audience Marketplace数据购买者同意使用数据馈送中包含的根据每千个广告展示次数(CPM)定价的特征报告所有提供的广告展示次数。 CPM使用情况在每个日历月的第5天到期，包括上个月的数据。 固定费用订阅者无需报告使用情况。
seo-title: 面向数据信息源购买者的账单
solution: Audience Manager
title: 面向数据信息源购买者的账单
keywords: Segment-level Reporting, segment-level, segment level
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '2027'
ht-degree: 1%

---


# 面向数据信息源购买者的账单 {#billing-for-data-feed-buyers}

Audience Marketplace数据购买者同意使用数据馈送中包含的按每千个广告展示次数()定价的特征报告所[!DNL CPM]有广告展示。 [!DNL CPM] 使用情况在每个日历月的第5天到期，并包含上个月的数据。 固定费用订阅者无需报告使用情况。

<br> 

## 如何报告CPM使用情况 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 数据购买者同意使用数据馈送中包含的按每千个广告展示次数()定价的特征报告所有提供的广[!DNL CPM]告展示次数。 [!DNL CPM] 使用情况在每个日历月的5天到期，并包含上个月的数据。 固定费用订阅者无需报告使用情况。

[!UICONTROL Audience Marketplace] 优惠报告使用情况的 [!DNL CPM] 两种方式：

* **细分报告**:这是推荐的使 [!DNL CPM] 用报告方法。 当您报告 [!DNL CPM] 细分级别的使用情况时，数据馈送级别报告部分会根据CPM数据馈送的成本归因中描述的算法，自动填 [充相应的使用量](#cost-attribution)。
* **数据馈送级报告**:此方法要求您根据CPM数 [!DNL CPM] 据源的成本归因中描述的算法，逐 [个报告每个数据源的使用情况](#cost-attribution)。 但是，与段级报告相比，此方法更加繁琐且容易出错。

<br> 

## 在区段级别报告CPM使用情况 {#segment-level-report}

该选 [!UICONTROL Segment Usage] 项卡允许您报告区段级别的使用情况，同时显示按它们映射到的目标分组的区段。

报告在 [!DNL CPM] 细分级别使用后， [!UICONTROL Audience Marketplace] 根据CPM数据源的成本归因，自动分配相应的数 [据源的正确使用情况](#cost-attribution)。

要报告区 [!DNL CPM] 段层的使用情况，请执行以下操作：

1. 转到 **[!UICONTROL Audience Marketplace > Payables]**。
1. 选择选 **[!UICONTROL Segment Usage]** 项卡。
1. 填写区段的使用情况。 如果您只需 [!UICONTROL Search] 报告其中某些区段的使用情况，可使用该框来筛选区段。
1. 单击 **[!UICONTROL Edit Segments Usage]**.
1. 在列 [!DNL CPM] 中输入使用 [!UICONTROL Usage] 量。
1. 完 **[!UICONTROL Save]** 成后单击并查看确认对话框。

   ![确认段使用](assets/confirm-segment-usage.png)

1. 单击 **[!UICONTROL Confirm]**.

另请观看我们的视频演示，了解如何报告区段级别的使用情况：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 在数据馈送级别报告CPM使用情况 {#feed-level-report}

数据馈送级别报告更加繁琐，容易出错，因为您必须单独计算每个数据馈送 [!DNL CPM] 的使用情况。 我们建议您改 [为在区段级别报告CPM使用情况](#segment-level-report) 。

要报告区 [!DNL CPM] 段层的使用情况，请执行以下操作：

1. 转到 **[!UICONTROL Audience Marketplace > Payables]**。
2. 选择选 **[!UICONTROL Feed Usage]** 项卡。
3. 使用该 [!UICONTROL Search] 框可过滤数据源并标识您需要报告其使用情况的数据源。
4. 单击 **[!UICONTROL Edit Feeds Usage]**.
5. 根据 [!DNL CPM] CPM数据源的成本属性计算每 [个数据源的使用情况](#cost-attribution)，并在列中输 [!UICONTROL Usage] 入它。
6. 完 **[!UICONTROL Save]** 成后单击并查看确认对话框。

   ![确认——源使用](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**.

<br> 

## 批量报告

要减少报告使用时的错误 [!DNL CPM] 和开销，您可以使用批量报告选项下载包含数据源和区段的 [!DNL CSV] 文件，填写使用情况，然后将其上传回 [!DNL Audience Manager]。 您可以使用批量报告报告源和段使用情况。

要批量更 [!DNL CPM] 新使用情况，请执行以下操作：

1. 转到 **[!UICONTROL Audience Marketplace > Payables]**。
1. 根据 **[!UICONTROL Feed Usage]** 要更 **[!UICONTROL Segment Usage]** 新的报告类型，选择或选项卡。
1. 单击 **[!UICONTROL Edit Feeds Usage]** 或 **[!UICONTROL Edit Segments Usage]**。
1. 单 **[!UICONTROL download the current usage]** 击以确保使用有效的CSV文件。
1. 在计算机上打开文件并填写使用情况报告。
1. 单击 **[!UICONTROL Choose a CSV file]** 以上传更新的使用情况报告。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 上传文件后立即对其进行验证，如果检测到文件中有任何错误，则会提示您。

<br> 

### 批量报告验证错误

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 输入无效 | [!DNL Audience Manager] 检测到文件模式 [!DNL CSV] 中的更改，如缺少列或列标题的更改。 | 避免更改表结构。 |
| 未找到” | 因 [!UICONTROL Segment Level Reporting]为 [!DNL Audience Manager] 无法识别 [!UICONTROL Segment ID] 和 [!UICONTROL Destination ID] 组合。 因 [!UICONTROL Feed Level Reporting]为 [!DNL Audience Manager] 无法识别 [!UICONTROL Data Provider Name]、 [!UICONTROL Feed Name]和组 [!UICONTROL Use Case] 合。 | 对 [!UICONTROL Segment Level Reporting]于，检查组合和组合的 [!UICONTROL Segment ID] 有效 [!UICONTROL Destination ID] 性。 对 [!UICONTROL Feed Level Reporting]于，检查组合、组合 [!UICONTROL Data Provider Name]的 [!UICONTROL Feed Name]有效性 [!UICONTROL Use Case] 。 |
| 找到重复记录 | [!DNL Audience Manager] 检测到具有不同印象值的重复记录。 | 查看报告，并确保不报告同一数据源或区段的不同使用值。 |
| 不支持值 | [!DNL Audience Manager] 在列中检测到非数值 [!DNL Audience Manager] 值。 | 查看报告，并确保只在列中输入数值 [!DNL Audience Manager] 。 |
| 缺少必填字段的标题 | [!DNL Audience Manager] 检测到必填字段缺少表标题。 对 [!UICONTROL Segment Level Reporting]于，必填字段为： [!UICONTROL Segment ID], [!UICONTROL Destination ID]o. 对 [!UICONTROL Feed Level Reporting]于，必填字段为： [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name] [!UICONTROL Use Case] | 查看报告并确保未篡改表标题。 |

>[!NOTE]
>从使用情况报告 [!DNL CSV] 中删除行对现有使用情况报告没有任何影响。 [!DNL Audience Manager] 仅处理报告中包含的字段。

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
   <td colname="col2"> <p>对于CPM印象总计： </p>
   <p> 报告展示总数，不使用小数。 Audience Manager根据您报告的总数自动计算CPM。</p><p>如果您需要报告1,234,567个印象，请完全按此报告。 您无需将展示总数除以1,000即可计算CPM。</p><p>使用Adobe Target或分析目标等工具优化您的网络或应用程序内容（内容优化）时使用的特征不会计入CPM计划的使用总数。 数据提供商通常使用统一费用计划对内容优化进行补偿。</p><p>请参 <a href="#cost-attribution">阅CPM数据源的成本归因</a> ，了解更多信息。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>坚持每月报告间隔</b> </p> </td> 
   <td colname="col2"> <p>报告系统在每月5日之后关闭。 如果到那时未能报告CPM使用情况，则必须将该金额添加到下个月的报告中。 例如，假设您在10月使用1000个展示次数，错过10月报告截止日期，在11月使用1000个展示次数。 在这种情况下，您将在12月1日到5日之间报告10月和11月的总数（2000年）。</p><p><b>提示</b>:您应始终尝试在下月的第1天至第5天之间报告上个月的CPM使用情况。</p><p>您可以在新日历月的第5天报告CPM使用情况，但不建议这样做。 报告CPM在每月5日之前的使用情况为Audience Manager提供检查和处理数据的时间。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM数据服务的成本归因 {#cost-attribution}

在此 [!UICONTROL Audience Marketplace] 中，您必须针对每个细分每月自行报告印象金额。 我们建议在 [!DNL CPM] 细分级别使用报告，以便自动完成成本归因。

<!-- marketplace_cpm_billing.xml -->

### 帐单摘要 {#billing-summary}

您必须提 [!DNL CPM] 交每个日历月的第1天到第5天之间的数据馈送印象金额。 为正确执行此操作，我们建议您在 [区段级别报告CPM使用情况](#segment-level-report)。

>[!TIP]
>在区段级 [!DNL CPM] 别报告使用情况时，数据馈送级别报告部分会自动填写相应的使用情况金额。

如果需要， [!UICONTROL Report CPM Usage at Data Feed Level]您必须单独编译上一个日历月中每个订阅源交付的所有展示次数，并根据本文所述的计费分配报告这些展示次数。

在报告上 [!DNL CPM] 一个日历月的编号后， [!DNL Adobe] 将执行以下操作：

* 根据每个订阅数据源的费率 [!DNL CPM] 创建发票和帐单。
* 根据您所报告的使用情况，向数据提供商（销售商）支付所欠 [!DNL CPM] 费用。

>[!IMPORTANT]
>
>作为买家，所有报告的印象总数必须真实而准确。 如果在每月的第5天之前未报告印象总数，则必须包括下个月未报告月份的总数。

<br> 

## 根据特征资格规则在信息源级别分配展示次数 {#assign-impressions}

用 [!UICONTROL Activation] 例允许您在相应的数据源中使用特征，在Segment Builder中创 [建区段](../../../features/segments/segment-builder.md) ，并将这些区段映射到目标。 布尔运 [!UICONTROL AND]算符 [!UICONTROL OR]、和 [!UICONTROL NOT] 允许您设置特征和段资格条件。

在数据 [源级别报告CPM使用情况时](#feed-level-report)，您必须根据特征资格规则中使用的 [!DNL Boolean] 运算符，按比例为每个数据源分配展示次数。 下表列表了如何按布尔规则或特征类型正确分配展示次数。

>[!TIP]
>[在细分级别报告CPM使用情况](#segment-level-report) ，让Audience Manager自动完成数据馈送级别报告。

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 规则限定逻辑或类型 </th> 
   <th colname="col2" class="entry"> 帐单分发 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 且</span> </p> </td> 
   <td colname="col2"> <p>将100%的已传递印象总数应用到使用布尔型AND条件的基于规则的区段中的所有提供者 <span class="wintitle"> 特征</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或者</span> </p> </td> 
   <td colname="col2"> <p>在使用布尔型OR条件的基于规则的区段中，将已传递印象总数的加权分配应用于所有提供者特征。 加权分配采用以下公式计算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>将100%的已传递印象总数应用于使用布尔型NOT条件的基于规则的区段中的所有提供者 <span class="wintitle"> 特征</span> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法段 </p> </td> 
   <td colname="col2"> <p>将100%的已传递印象总数应用到包含算法特征的区段中的所有提供商源。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 计费示例 {#billing-examples}

以下示例旨在说明如何在 [!DNL CPM] 数据馈送级别进行使用分配。

>[!IMPORTANT]
>我们建议您改 [为在细分级别报告CPM使用情况](#segment-level-report) ，以自动完成此过程。

让我们考虑以下情形：

![billing-examples](assets/billing-examples.png)

<br> 

### 案例1:具有资格和资格规则的细分

此区段包含来自单独数据提供者的3个特征。 由于细分资格基于某个条 [!UICONTROL AND] 件，访客必须从所有三个源中实现特征才能获得该细分。

![](assets/billing-segment-and.png)

在某个 [!UICONTROL AND] 条件下，您必须将当月收到的展示数的100%分配给所有三个数据提供商。 在此部 [!UICONTROL Audience Marketplace > Payables] 分中，您将每个提供商的印象评为1,000,000。

此示例适用于使用运算符的 [!DNL Boolean] 段或 [!UICONTROL NOT] 包含算法特征的段。

<br> 

### 案例2:具有或资格规则的细分

此区段包含来自单独数据提供者的3个特征。 由于区段资格基于条 [!UICONTROL OR] 件，访客必须实现三个特征中的至少一个才能符合区段资格。

我们无法判断哪个特质会造成印象，因为资格是基于某个条 [!UICONTROL OR] 件的。 因此，在此部分中，您 [!UICONTROL Audience Marketplace > Payables] 根据特征人口，对每个提供商的总展示次数进行加权分配。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 案例3:具有建模和激活用例的细分

此示例描述基于两个数据源用例的归因——建模和激活。 在本示例中，我们将看到两个数据提供者，其中包含以下信息：

![数据馈送](assets/feed-use-cases.png)

在下表中，区段X包含两个特征，即T1和T2，区段规则为T1或T2，其中：

* T1是数据源A的一个特征；
* T2是基于Data Feed A和Data Feed B的第三方特征建模的算法特征。

区段将映射到一个目标，并且使用区段级报告在一个月内为此区段输入1,000,000 [个展示次数](#segment-level-report)。

在这100万张印象中：

* T1占细分人口的40%，对于Feed A，这意味着40万次展示。
* T2占细分人口的60%，对于Feed A和Feed B而言，这意味着600,000个印象。

在数据馈送级别，展示次数的分配方式是：

* 数据馈送A从特征T2接收600,000次展示（该展示基于来自数据馈送A和数据馈送B的特征，因此二者都接收展示），从特征T1接收400,000次展示（来自数据馈送A的特征），总计1,000,000次展示。
* 数据源B从特征T2接收600,000个印象（请参阅上面的说明），从特征T1接收0个印象。

按数据馈送和用例进行的一览表细分如下：

![feed-breaksion](assets/feed-breakdown-alt.png)

<br> 

## 统一费用数据源的计费和印象分配 {#billing-flat-fee}

统一费用数据馈送每月向您收取固定金额，而不管订阅开始的时间或您使用的展示次数。 部分月份使用情况或间隔不按比例收费。 与CPM计费一样，Adobe将为您的订阅数据馈送生成发票，并按每月固定费率向您收费。

例如，假设您在月中时决定启用某个饲料中的特定特征。 无论您是何时开始订阅或激活特定特征，您仍将按每月全额收费。