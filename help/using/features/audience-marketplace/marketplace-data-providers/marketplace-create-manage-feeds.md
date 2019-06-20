---
description: 数据源需要名称、描述、数据源和计划类型。在保存和激活源之前，源将被禁用。在“受众市场”>“我的共享数据”中设置公共或私有数据服务。仅适用于数据销售者。
seo-description: 数据源需要名称、描述、数据源和计划类型。在保存和激活源之前，源将被禁用。在“受众市场”>“我的共享数据”中设置公共或私有数据服务。仅适用于数据销售者。
seo-title: 创建、价格和管理数据馈送
solution: Audience Manager
title: 创建、价格和管理数据馈送
topic: DIL API
uuid: e28c20b3-33fc-4455-8ee9-8530d126f741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

数据源需要名称、描述、数据源和计划类型。在保存和激活源之前，源将被禁用。Set up public or private data feeds in [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]. 仅适用于数据销售者。

## Create a Public or Private Data Feed {#create-public-private-data-feed}

数据源需要名称、描述、数据源和计划类型。在保存和激活源之前，源将被禁用。Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. 仅适用于数据销售者。

<!-- t_data_feed.xml -->

您必须具有管理员权限才能创建公共或私有数据源。
要创建数据源，请执行以下操作：

1. 单击 **[!UICONTROL New Data Feed]**.
1. 命名数据源。数据购买者可以根据名称搜索您的源。
1. 提供简短描述(最大255个字符)。

   好描述应该准确描述您的源。For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). 描述文本可搜索，并帮助购买者查找或评估您的源。良好的描述是吸引用户访问数据源的重要部分。
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >属于此数据源的任何当前和未来特征都将与您的数据购买者共享，作为此源的一部分。

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   源可包含多个计划。计划可以包含多个用例。For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. 要保存和激活数据源，请执行以下操作：
   1. Move the **[!UICONTROL Availability]** slider to **[!UICONTROL Active]**.
   1. 单击 **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* 无法删除保存和激活的数据源。
   >* 购买者只能看到活动源。


### 可选：创建专用数据源

[!UICONTROL Settings] 在部分中，将滑块移动到：

* **[!UICONTROL Private]** 以及 **[!UICONTROL Branded]**：买方 [!UICONTROL Marketplace] 列表显示提供商列中的卖家姓名，所有其他数据均隐藏。

* **[!UICONTROL Private]** 以及 **[!UICONTROL Unbranded]**：买方 [!UICONTROL Marketplace] 列表仅显示数据源名称和说明。The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ LIKE_ This]
>
>* [专用数据信息源](../../../features/audience-marketplace/marketplace-private-feeds.md)


## 停用订阅者的数据馈送 {#deactivate-data-feed}

As an [!UICONTROL Audience Marketplace] data provider, you can revoke buyer access to a subscribed data feed. 您可能希望从供给中删除购买者，例如滞纳金/未支付费用或他们使用特征数据不正当。

<!-- marketplace-deactiva4te-subscribers.xml -->

撤销订阅者：

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >具有多个帐户的数据源标有三角形/感叹号图标。

1. In the [!UICONTROL Subscribers] column, click the blue number that counts subscribers for that feed. 此操作将打开订阅详细信息页面。
1. Move the **[!UICONTROL Subscription]** slider to **[!UICONTROL Off]**. 这将打开确认对话框窗口。
1. [!UICONTROL Confirmation] 在弹出窗口中，单击 **[!UICONTROL Yes]** 以取消激活订阅或 **[!UICONTROL Cancel]** 退出，而不会更改订阅。

### 取消激活订阅者后发生的情况

撤销对数据源的访问权限会向数据买家的帐户中的所有管理员用户发送通知电子邮件。电子邮件中包含一个用于列出已吊销特征的附件。此列表可帮助订阅者从其区段和模型中查找和删除禁用的特征。

### 结帐和源取消激活

删除对数据源的访问权限后，用户将负责之前或当月的费用，具体取决于您取消激活源时的具体费用。

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] 是 [!UICONTROL Audience Marketplace] 数据源中的基本组件。作为数据提供商，它们允许您为您的供给创建多个用例和价格选项。此外，为每个数据源创建几个计划可能是一个不错的战略。这为购买者提供了不同选项，供他们在寻找数据模型或发送到目标时选择。

[创建要选择的数据源](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)[!UICONTROL Plan Types]。

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

[!UICONTROL Use Case] 这些设置可让卖家控制购买者如何使用您的数据。

### 区段和重叠

**[!UICONTROL Segments and Overlap]** 用例创建了一个计划，允许买家将特征数据中特征数据 [与特征重叠报告相比较](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)。Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

重叠比较可以帮助买家：

* **扩大受众范围：** 低重叠建议您的特征包含购买者之前未见过的用户。因此，购买者可能希望这些特征将新用户添加到受众细分中。
* **增强现有受众：** 重叠部分表示您的特征包含类似于买家已经知晓的用户。因此，购买者可能希望这些特征有助于为开发的受众做出有针对性的增量改进。

按如下使用此用例：

* 度量单位：收费费用
* 价格：免费($0.00)

### 建模

**[!UICONTROL Modeling]** 使用案例创建了一个计划，允许购买者通过 [算法建模](../../../features/algorithmic-models/understanding-models.md#understanding-models)比较您的特征。购买者可以查看模型结果，以便在共享相似转化属性的数据中找到新受众。按如下使用此用例：

* 度量单位：收费费用
* 价格：折扣或市价价格

### 激活

**[!UICONTROL Activation]** 使用用例，购买者可以将数据发送 [到目标](../../../features/destinations/destinations.md)。使用此用例，购买者无法将数据与重叠报表或算法模型进行比较。按如下使用此用例：

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

帐单和价格选项可控制买家为您的数据付款的方式。

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 结算周期</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> “按月使用”</span></b> 是唯一的选项。计费周期在每个月的第10天结束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 度量单位</span></b> </td> 
   <td colname="col2">按CPM费率或收取简单费用向数据购买者收取费用。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 对于CPM定价，数据购买者需要自助报告使用。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">中等收费的费用，数据购买者不会因为收取固定费用而报告使用情况。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 价格</span></b> </td>
   <td colname="col2"> 卖家向买方收取CPM费率或收取固定费用(以美元为单位)的金额。 </td>
  </tr> 
 </tbody> 
</table>

## Plan Notes {#plan-notes}

**[!UICONTROL Additional Notes]** 在字段中，需要花一些时间来描述源中的每个数据计划。好的简短描述可帮助买家了解数据馈送中每个计划的内容或目的。在搜索或评估新数据源时，购买者可以阅读数据馈送和计划描述。

## Manage Private Data Feed Requests {#manage-private-requests}

用于管理买家的私人馈送请求的提供商工作流程。

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. 单击私人数据源的名称。
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. 在确认弹出窗口中确认或取消选定的操作。

>[!MORE_ LIKE_ This]
>
>* [专用数据信息源](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. 您可以向已提交订阅请求的订阅者或已请求数据源详细信息的订阅者提供折扣。Discounts apply to [!DNL CPM] and flat rate feeds. 当您希望为新客户提供订阅激励措施或奖励客户忠诚度时，折扣可能会很有帮助。

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

要折扣源，请将折扣金额作为%到折扣字段添加，并确认您的更改。Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)