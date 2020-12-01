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

Audience Marketplace数据购买者同意使用数据馈送中包含的根据每千个广告展示次数([!DNL CPM])定价的特征报告所有提供的广告展示次数。 [!DNL CPM] 使用情况在每个日历月的第5天到期，并包含上个月的数据。固定费用订阅者无需报告使用情况。

<br> 

## 如何报告CPM使用情况{#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 数据购买者同意使用数据馈送中包含的按每千个广告展示次数()定价的特征报告所有提供的广[!DNL CPM]告展示次数。[!DNL CPM] 使用情况在每个日历月的5天到期，并包含上个月的数据。固定费用订阅者无需报告使用情况。

[!UICONTROL Audience Marketplace] 优惠报告使用情况的 [!DNL CPM] 两种方式：

* **细分报告**:这是推荐的使 [!DNL CPM] 用报告方法。当您报告[!DNL CPM]段级别的使用情况时，数据馈送级别报告部分会根据[CPM数据馈送成本属性](#cost-attribution)中描述的算法自动填写相应的使用量。
* **数据馈送级报告**:此方法要求您根据CPM数 [!DNL CPM] 据源的成本归因中描述的算法，逐 [个报告每个数据源的使用情况](#cost-attribution)。但是，与段级报告相比，此方法更加繁琐且容易出错。

<br> 

## 在区段级别{#segment-level-report}报告CPM使用情况

[!UICONTROL Segment Usage]选项卡允许您报告区段级别的使用情况，同时显示按它们映射到的目标分组的区段。

在报告段级别[!DNL CPM]使用后，[!UICONTROL Audience Marketplace]会根据[CPM数据源的成本属性](#cost-attribution)自动分配相应数据源的正确使用。

要报告[!DNL CPM]在段级别的使用情况，请执行以下操作：

1. 转至&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 选择&#x200B;**[!UICONTROL Segment Usage]**&#x200B;选项卡。
1. 填写区段的使用情况。 如果您只需要报告其中某些区段的使用情况，可以使用[!UICONTROL Search]框来筛选区段。
1. 单击 **[!UICONTROL Edit Segments Usage]**.
1. 在[!UICONTROL Usage]列中输入[!DNL CPM]使用量。
1. 完成后，单击&#x200B;**[!UICONTROL Save]**&#x200B;并查看确认对话框。

   ![确认段使用](assets/confirm-segment-usage.png)

1. 单击 **[!UICONTROL Confirm]**.

另请观看我们的视频演示，了解如何报告区段级别的使用情况：

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 数据馈送级别{#feed-level-report}的报告CPM使用情况

数据馈送级别报告更加繁琐，容易出错，因为您必须单独计算每个数据馈送的[!DNL CPM]使用情况。 我们建议您[在段级别](#segment-level-report)报告CPM使用情况。

要报告[!DNL CPM]在段级别的使用情况，请执行以下操作：

1. 转至&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
2. 选择&#x200B;**[!UICONTROL Feed Usage]**&#x200B;选项卡。
3. 使用[!UICONTROL Search]框过滤数据源并标识需要报告其使用情况的数据源。
4. 单击 **[!UICONTROL Edit Feeds Usage]**.
5. 根据CPM数据源的[成本属性](#cost-attribution)计算每个数据源的[!DNL CPM]使用情况，并在[!UICONTROL Usage]列中输入它。
6. 完成后，单击&#x200B;**[!UICONTROL Save]**&#x200B;并查看确认对话框。

   ![确认——源使用](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**.

<br> 

## 批量报告

要减少报告[!DNL CPM]使用时的错误和开销，您可以使用批量报告选项下载包含数据源和区段的[!DNL CSV]文件，填写使用情况，然后将其上传回[!DNL Audience Manager]。 您可以使用批量报告报告源和段使用情况。

要批量更新[!DNL CPM]使用情况：

1. 转至&#x200B;**[!UICONTROL Audience Marketplace > Payables]**。
1. 根据要更新的报告类型，选择&#x200B;**[!UICONTROL Feed Usage]**&#x200B;或&#x200B;**[!UICONTROL Segment Usage]**&#x200B;选项卡。
1. 单击&#x200B;**[!UICONTROL Edit Feeds Usage]**&#x200B;或&#x200B;**[!UICONTROL Edit Segments Usage]**。
1. 单击&#x200B;**[!UICONTROL download the current usage]**&#x200B;以确保使用有效的CSV文件。
1. 在计算机上打开文件并填写使用情况报告。
1. 单击&#x200B;**[!UICONTROL Choose a CSV file]**&#x200B;以上传更新的使用情况报告。

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 上传文件后立即对其进行验证，如果检测到文件中有任何错误，则会提示您。

<br> 

### 批量报告验证错误

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 输入无效 | [!DNL Audience Manager] 检测到文件模式 [!DNL CSV] 中的更改，如缺少列或列标题的更改。 | 避免更改表结构。 |
| 未找到” | 对于[!UICONTROL Segment Level Reporting],[!DNL Audience Manager]无法识别[!UICONTROL Segment ID]和[!UICONTROL Destination ID]组合。 对于[!UICONTROL Feed Level Reporting],[!DNL Audience Manager]无法识别[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]组合。 | 对于[!UICONTROL Segment Level Reporting]，检查[!UICONTROL Segment ID]和[!UICONTROL Destination ID]组合的有效性。 对于[!UICONTROL Feed Level Reporting]，检查[!UICONTROL Data Provider Name]、[!UICONTROL Feed Name]和[!UICONTROL Use Case]组合的有效性。 |
| 找到重复记录 | [!DNL Audience Manager] 检测到具有不同印象值的重复记录。 | 查看报告，并确保不报告同一数据源或区段的不同使用值。 |
| 不支持值 | [!DNL Audience Manager] 在列中检测到非数 [!DNL Audience Manager] 值。 | 查看报告，确保仅在[!DNL Audience Manager]列中输入数值。 |
| 缺少必填字段的标题 | [!DNL Audience Manager] 检测到必填字段缺少表标题。对于[!UICONTROL Segment Level Reporting]，必填字段为：[!UICONTROL Segment ID], [!UICONTROL Destination ID]。 对于[!UICONTROL Feed Level Reporting]，必填字段为：[!UICONTROL Data Provider Name]、[!UICONTROL Data Feed Name]、[!UICONTROL Use Case] | 查看报告并确保未篡改表标题。 |

>[!NOTE]
>从[!DNL CSV]使用情况报告中删除行对现有使用情况报告没有任何影响。 [!DNL Audience Manager] 仅处理报告中包含的字段。

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
   <p> 报告展示总数，不使用小数。 Audience Manager根据您报告的总数自动计算CPM。</p><p>如果您需要报告1,234,567个印象，请完全按此报告。 您无需将展示总数除以1,000即可计算CPM。</p><p>使用Adobe Target或分析目标等工具优化您的网络或应用程序内容（内容优化）时使用的特征不会计入CPM计划的使用总数。 数据提供商通常使用统一费用计划对内容优化进行补偿。</p><p>有关详细信息，请参阅<a href="#cost-attribution">CPM数据源的成本属性</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>坚持每月报告间隔</b> </p> </td> 
   <td colname="col2"> <p>报告系统在每月5日之后关闭。 如果到那时未能报告CPM使用情况，则必须将该金额添加到下个月的报告中。 例如，假设您在10月使用1000个展示次数，错过10月报告截止日期，在11月使用1000个展示次数。 在这种情况下，您将在12月1日到5日之间报告10月和11月的总数（2000年）。</p><p><b>提示</b>:您应始终尝试在下月的第1天至第5天之间报告上个月的CPM使用情况。</p><p>您可以在新日历月的第5天报告CPM使用情况，但不建议这样做。 报告CPM在每月5日之前的使用情况为Audience Manager提供检查和处理数据的时间。</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM数据服务的成本归因{#cost-attribution}

在[!UICONTROL Audience Marketplace]中，您必须针对每个区段每月自行报告印象金额。 我们建议报告[!DNL CPM]在细分级别使用，以便自动完成成本归因。

<!-- marketplace_cpm_billing.xml -->

### 帐单摘要{#billing-summary}

您必须提交每个日历月的第1天至第5天之间的[!DNL CPM]数据馈送印象金额。 为正确执行此操作，我们建议您[在段级别](#segment-level-report)报告CPM使用情况。

>[!TIP]
>当您报告区段级别的[!DNL CPM]使用情况时，数据馈送级别报告部分会自动填写相应的使用量。

如果您需要[!UICONTROL Report CPM Usage at Data Feed Level]，您必须单独编译上一个日历月中每个订阅源发送的所有印象，并根据本文所述的计费分配报告这些印象。

在报告上一个日历月的[!DNL CPM]编号后，[!DNL Adobe]将执行以下操作：

* 根据每个订阅数据源的[!DNL CPM]费率创建发票和帐单。
* 根据您报告的[!DNL CPM]使用情况，向数据提供商（销售商）支付所欠费用。

>[!IMPORTANT]
>
>作为买家，所有报告的印象总数必须真实而准确。 如果在每月的第5天之前未报告印象总数，则必须包括下个月未报告月份的总数。

<br> 

## 根据特征资格规则{#assign-impressions}在信息源级别分配展示次数

[!UICONTROL Activation]用例允许您在相应的数据源中使用特征，在[区段生成器](../../../features/segments/segment-builder.md)中创建区段，并将这些区段映射到目标。 布尔运算符[!UICONTROL AND]、[!UICONTROL OR]和[!UICONTROL NOT]允许您设置特征和区段限定条件。

在[报告数据馈送级别](#feed-level-report)的CPM使用情况时，您必须根据特征限定规则中使用的[!DNL Boolean]运算符，按比例为每个数据馈送分配印象。 下表列表了如何按布尔规则或特征类型正确分配展示次数。

>[!TIP]
>[报告段级别的CPM使用情况](#segment-level-report)，让Audience Manager自动完成数据馈送级别报告。

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
   <td colname="col2"> <p>在使用布尔值<span class="wintitle"> AND</span>条件的基于规则的区段中，将100%的已传递印象总数应用于所有提供者特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或者</span> </p> </td> 
   <td colname="col2"> <p>在使用布尔型OR条件的基于规则的区段中，将已传递印象总数的加权分配应用于所有提供者特征。 加权分配采用以下公式计算：</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>在使用布尔值<span class="wintitle"> NOT</span>条件的基于规则的区段中，将100%的已传递印象总数应用于所有提供者特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法段 </p> </td> 
   <td colname="col2"> <p>将100%的已传递印象总数应用到包含算法特征的区段中的所有提供商源。 </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 帐单示例{#billing-examples}

以下示例旨在说明如何在数据馈送级别执行[!DNL CPM]使用分配。

>[!IMPORTANT]
>我们建议您[在区段级别](#segment-level-report)报告CPM使用情况，以自动完成此过程。

让我们考虑以下情形：

![billing-examples](assets/billing-examples.png)

<br> 

### 案例1:具有资格和资格规则的细分

此区段包含来自单独数据提供者的3个特征。 由于区段资格基于[!UICONTROL AND]条件，访客必须从所有三个源中实现特征才能获得区段资格。

![](assets/billing-segment-and.png)

如果条件为[!UICONTROL AND]，您必须将当月收到的展示数的100%分配给所有三个数据提供者。 在[!UICONTROL Audience Marketplace > Payables]部分，您将每个提供商的展示次数评为1,000,000。

此示例适用于使用[!DNL Boolean] [!UICONTROL NOT]运算符的段或包含算法特征的段。

<br> 

### 案例2:具有或资格规则的细分

此区段包含来自单独数据提供者的3个特征。 由于区段资格基于[!UICONTROL OR]条件，访客必须实现三个特征中的至少一个才能符合区段资格。

我们无法判断哪个特质对印象负责，因为资格是基于[!UICONTROL OR]条件的。 因此，在[!UICONTROL Audience Marketplace > Payables]部分中，您可以根据特征群体对每个提供商的总展示次数进行加权分配。

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 案例3:具有建模和激活用例的细分

此示例描述基于两个数据源用例的归因——建模和激活。 在本示例中，我们将看到两个数据提供者，其中包含以下信息：

![数据馈送](assets/feed-use-cases.png)

在下表中，区段X包含两个特征，即T1和T2，区段规则为T1或T2，其中：

* T1是数据源A的一个特征；
* T2是基于Data Feed A和Data Feed B的第三方特征建模的算法特征。

区段将映射到目标，并且使用[区段级别报告](#segment-level-report)在一个月内为此区段输入1,000,000印象。

在这100万张印象中：

* T1占细分人口的40%，对于Feed A，这意味着40万次展示。
* T2占细分人口的60%，对于Feed A和Feed B而言，这意味着600,000个印象。

在数据馈送级别，展示次数的分配方式是：

* 数据馈送A从特征T2接收600,000次展示（该展示基于来自数据馈送A和数据馈送B的特征，因此二者都接收展示），从特征T1接收400,000次展示（来自数据馈送A的特征），总计1,000,000次展示。
* 数据源B从特征T2接收600,000个印象（请参阅上面的说明），从特征T1接收0个印象。

按数据馈送和用例进行的一览表细分如下：

![feed-breaksion](assets/feed-breakdown-alt.png)

<br> 

## 统一费用数据源的计费和印象分配{#billing-flat-fee}

统一费用数据馈送每月向您收取固定金额，而不管订阅开始的时间或您使用的展示次数。 部分月份使用情况或间隔不按比例收费。 与CPM计费一样，Adobe将为您的订阅数据馈送生成发票，并按每月固定费率向您收费。

例如，假设您在月中时决定启用某个饲料中的特定特征。 无论您是何时开始订阅或激活特定特征，您仍将按每月全额收费。