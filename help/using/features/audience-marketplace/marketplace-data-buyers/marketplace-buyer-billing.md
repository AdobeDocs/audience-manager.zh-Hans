---
description: Audience Marketplace数据购买者同意，根据每千个广告印象(CPM)的成本，使用数据馈送中包含的特征报告所有广告印象。CPM使用将在每个日历月的第天到期，并包含上个月的数据。付费用户无需报告使用情况。
seo-description: Audience Marketplace数据购买者同意，根据每千个广告印象(CPM)的成本，使用数据馈送中包含的特征报告所有广告印象。CPM使用将在每个日历月的第天到期，并包含上个月的数据。付费用户无需报告使用情况。
seo-title: 数据馈送购买者计费
solution: Audience Manager
title: 数据馈送购买者计费
keywords: 细分级别报告、细分级别、细分级别
uuid: d723667-282b-4160-9909-579721af4016
translation-type: tm+mt
source-git-commit: a02ef4cfa987c05e3db173f8e6e9a635d1ecd1fd

---


# Billing for Data Feed Buyers {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] 使用将在每个日历月的第天到期，并包含上个月的数据。付费用户无需报告使用情况。

## How to Report CPM Usage {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 数据购买者同意报告使用每千个广告印象([!DNL CPM])定价的数据馈送所提供的所有广告印象。[!DNL CPM] 使用期限为每个日历月的天，并包含上个月的数据。付费用户无需报告使用情况。

[!UICONTROL Audience Marketplace] 提供了两种报告 [!DNL CPM] 使用情况的方法：

* **细分级别报告**：这是建议 [!DNL CPM] 的使用报告方法。When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **数据馈送级别报告**：此方法要求您根据CPM数据源的费用归因中所述的算法单独报告每个数据馈送的 [!DNL CPM][使用情况](#cost-attribution)。但是，与区段级报告相比，此方法比较繁琐，容易出错。

## Report CPM Usage at Segment Level {#segment-level-report}

[!UICONTROL Segment Usage] 此选项卡允许您报告区段级别使用情况，同时显示按其映射到的目标分组的区段。

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;转至。
2. Select the **[!UICONTROL Segment Usage]** tab.
3. 填写区段使用情况。You can use the [!UICONTROL Search] box to filter the segments if you only need to report usage for some of them.
4. 单击 **[!UICONTROL Edit Segments Usage]**.
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.
   ![确认区段使用](assets/confirm-segment-usage.png)
7. 单击 **[!UICONTROL Confirm]**.

## Report CPM Usage at Data Feed Level {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead.

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;转至。
2. Select the **[!UICONTROL Feed Usage]** tab.
3. Use the [!UICONTROL Search] box to filter the data feeds and identify the ones that you need to report usage for.
4. 单击 **[!UICONTROL Edit Feeds Usage]**.
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you're done and review the confirmation dialog.

   ![确认源使用](assets/confirm-feed-usage.png)

7. 单击 **[!UICONTROL Confirm]**.

## 批量报告

To reduce errors and overhead while reporting [!DNL CPM] usage, you can use the bulk reporting option to download a [!DNL CSV] file containing the data feeds and segments, fill in the usage, and upload it back to [!DNL Audience Manager]. 您可以使用批量报告报告源和区段使用情况。

To update [!DNL CPM] usage in bulk:

1. **[!UICONTROL Audience Marketplace > Payables]**&#x200B;转至。
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. Click **[!UICONTROL Edit Feeds Usage]** or **[!UICONTROL Edit Segments Usage]**.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. 在计算机上打开文件并填写使用情况报告。
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 在上传文件后对其进行验证，并在检测到文件中的任何错误时提示您。

### 批量报告验证错误

| 错误消息 | 描述 | 修复了“未定义”错误地 |
| ------------- | -------------| -----|
| 输入无效 | [!DNL Audience Manager] 检测到 [!DNL CSV] 文件架构中的更改，如缺少列或列标题更改。 | 避免更改表结构。 |
| 未找到” | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| 找到的记录重复 | [!DNL Audience Manager] 检测到具有不同印象值的重复记录。 | 查看报告并确保您没有报告相同数据源或区段的不同使用值。 |
| 不支持的值 | [!DNL Audience Manager] 检测到 [!DNL Audience Manager] 列中的非数值。 | Review the report and make sure you only enter numerical values in the [!DNL Audience Manager] column. |
| 必填字段标题缺失 | [!DNL Audience Manager] 检测到必填字段的缺少表标题。For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | 查看报告并确保表标题未被篡改。 |

>[!NOTE]
>Removing rows from the [!DNL CSV] usage report does not have any effect on the existing usage report. [!DNL Audience Manager] 仅处理报表中包含的字段。

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
   <p> 报告展示总数，而不使用小数点。Audience Manager会根据您报告的总数字自动计算CPM。</p><p>如果需要报告1,234,567印象，请准确报告。您无需将印象总数除以1,000即可计算CPM。</p><p>使用Adobe Target或Analytics目标等工具优化Web或应用程序内容(内容优化)的特征不会计入CPM计划的使用总数。数据提供商通常使用平面费用计划进行内容优化。</p><p>See <a href="#cost-attribution">Cost Attribution for CPM Data Feeds</a> for more information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>坚持按月报告间隔</b> </p> </td> 
   <td colname="col2"> <p>报告系统在每个月的第5日之后关闭。如果您未能在那时报告CPM使用情况，则必须将该金额添加到下个月的报告中。例如，假设10月在10月内使用了1000次展示，在11月的报告截止日期中使用了1000次印象。在这种情况下，您将报告十二月和十一月(2000)在第一和第五日之间的总计(2000)。</p><p><b>提示</b>：您应始终在下个月的第天和第5日之间报告上一个月的CPM使用情况。</p><p>您可以在新日历月的第5日报告CPM使用情况，但不建议这样做。在每个月的第5日之前报告CPM使用情况可让Audience Manager时间检查和处理数据。</p> </td>
  </tr> 
 </tbody> 
</table>

## Cost Attribution for CPM Data Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report impression amounts each month, for each of your segments. We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### Billing Summary {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. To do this correctly, we recommend that you [Report CPM Usage at Segment Level](#segment-level-report).

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>作为购买者，所有报告的印象总数必须真实准确。如果您未能在每个月的第天之前报告印象总数，则必须包含下个月未报告月份的总计。

## Assign Impressions at Feed Level Based on Trait Qualification Rules {#assign-impressions}

[!UICONTROL Activation] 使用用例，您可以使用相应数据源中的特征在 [区段生成器](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) 中创建区段，并将这些区段映射到目标。The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

When you [Report CPM Usage at Data Feed Level](#feed-level-report), you must allocate impressions proportionally for each data feed, according to the [!DNL Boolean] operators used in the trait qualification rules. 下表列出了如何按Boolean规则或特征类型正确分配印象。

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
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> AND</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 或者</span> </p> </td> 
   <td colname="col2"> <p>在使用Boolean OR条件的基于规则的区段中，将呈现的印象总数加权分配给所有提供者特征。加权分配使用以下公式进行计算：</p><p><code>(特征人口/区段人群)*展示次数* CPM成本</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> NOT</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>算法细分 </p> </td> 
   <td colname="col2"> <p>将100%附带的印象总数应用于包含算法特征的区段中的所有提供者源。 </p> </td> 
  </tr>
 </tbody>
</table>

## Billing Examples {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead, to have this process done automatically.

下面我们来看一下以下情景：

![帐单示例](assets/billing-examples.png)

### 案例1：具有和资格规则的细分

此区段包含来自不同数据提供商的个特征。Since segment qualification is based on an [!UICONTROL AND] condition, visitors have to realize the traits from all three feeds to qualify for the segment.

![](assets/billing-segment-and.png)

[!UICONTROL AND] 有了条件，您必须将当月内收到的所有印象分配给所有三家数据提供商。[!UICONTROL Audience Marketplace > Payables] 在此部分中，您将为每个提供商提供1,000,000次印象。

This example applies to segments that use [!DNL Boolean] [!UICONTROL NOT] operators or for segments that contain algorithmic traits.

### 案例2：具有或资格规则的细分

此区段包含来自不同数据提供商的个特征。Since segment qualification is based on an [!UICONTROL OR] condition, visitors have to realize at least one of the three traits to qualify for the segment.

We cannot tell which trait is responsible for an impression because qualification is based on an [!UICONTROL OR] condition. As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![帐单区段或](assets/billing-segment-or.png)

>[!MORE_ LIKE_ This]
>
>* [付费数据馈送计费和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## Billing and Impression Allocation for Flat Fee Data Feeds {#billing-flat-fee}

付费数据服务每月向您收取固定金额，无论订阅开始或您使用的印象数量如何。部分月使用情况或间隔不按比例收费。与CPM计费一样，Adobe将生成发票并为您订阅的数据服务每月支付固定费用。

例如，假设您决定在月中旬开启某个源中的特定特征。无论您何时开始订阅或激活特定特征，您仍将按月费计费。