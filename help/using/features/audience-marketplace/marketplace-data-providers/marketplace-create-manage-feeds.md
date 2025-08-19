---
description: 数据馈送需要名称、描述、数据源和规划类型。 在保存并激活馈送之前，馈送处于禁用状态。 在Audience Marketplace >我的共享数据中设置公共或私有数据馈送。 仅适用于数据销售商。
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: 创建、定价和管理数据信息源
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 1%

---

# 创建、定价和管理数据信息源 {#create-price-and-manage-data-feeds}

## 创建公共或专用数据馈送 {#create-public-private-data-feed}

数据馈送需要名称、描述、数据源和规划类型。 在保存并激活馈送之前，馈送处于禁用状态。 在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data]**&#x200B;中设置公共或私有数据馈送。 仅适用于数据销售商。

<!-- t_data_feed.xml -->

您必须具有管理员权限才能创建公共或专用数据馈送。
要创建数据馈送，请执行以下操作：

1. 单击 **[!UICONTROL New Data Feed]**。
1. 命名数据馈送。 数据购买者可以根据名称搜索您的馈送。
1. 提供简要说明（最多255个字符）。

   一个准确的描述应该能够准确地描述您的信息源。 例如，您可以包含营销类别、人口统计和地理覆盖范围的文本（例如，[!DNL US]或北美）。 描述文本可搜索，可帮助购买者查找或评估您的信息源。 良好的描述是吸引订阅者使用数据馈送的重要组成部分。
1. 从&#x200B;**[!UICONTROL Data Source]**&#x200B;选项中选择数据源。 数据馈送仅限于单个数据源。 不能将多个数据源分配给同一数据馈送。

   >[!IMPORTANT]
   >
   >属于此数据源的任何当前和未来特征都将作为此信息源的一部分与您的数据购买者共享。

1. 在[!UICONTROL Plan Types]中，选择要使用的选项，然后单击&#x200B;**[!UICONTROL Add Plan]**。

   信息源可以包含多个计划。 计划可以包含多个用例。 有关详细信息，请参阅[数据馈送的计划类型](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)。

1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;保存您的数据馈送&#x200B;*而不*&#x200B;激活它。
1. 要保存并激活数据馈送，请执行以下操作：
   1. 将&#x200B;**[!UICONTROL Availability]**&#x200B;滑块移动到&#x200B;**[!UICONTROL Active]**。
   1. 单击 **[!UICONTROL Save]**。

   >[!NOTE]
   >
   >* 无法删除已保存和激活的数据馈送。
   >* 购买者只能看到活动信息源。

### 可选：创建专用数据馈送

在[!UICONTROL Settings]部分中，将滑块移动到：

* **[!UICONTROL Private]**&#x200B;和&#x200B;**[!UICONTROL Branded]**：买方的[!UICONTROL Marketplace]列表在提供商列中显示了卖方的名称，并且所有其他数据都已隐藏。

* **[!UICONTROL Private]**&#x200B;和&#x200B;**[!UICONTROL Unbranded]**：购买者的[!UICONTROL Marketplace]列表仅显示数据馈送名称和描述。 数据提供程序名称显示为[!UICONTROL Private Seller]。

若要查看私有信息源对购买者的外观，请参阅[私有数据信息源](../../../features/audience-marketplace/marketplace-private-feeds.md)中的“购买者”部分。

## 停用订阅者的数据馈送 {#deactivate-data-feed}

作为[!UICONTROL Audience Marketplace]数据提供程序，您可以撤销购买者对订阅的数据馈送的访问权限。 您可能希望将买家从馈送中删除，原因包括延迟付款/未支付费用或者他们未正确使用特征数据。

<!-- marketplace-deactiva4te-subscribers.xml -->

要撤销订户，请执行以下操作：

1. 在[!UICONTROL My Shared Data]中，查找订阅服务器正在使用的馈送。

   >[!NOTE]
   >
   >具有逾期帐户的数据馈送使用三角形/感叹号图标进行标记。

1. 在[!UICONTROL Subscribers]列中，单击计算该馈送的订阅者的蓝色数字。 这将打开订阅详细信息页面。
1. 将&#x200B;**[!UICONTROL Subscription]**&#x200B;滑块移动到&#x200B;**[!UICONTROL Off]**。 这将打开一个确认对话框窗口。
1. 在[!UICONTROL Confirmation]弹出窗口中，单击&#x200B;**[!UICONTROL Yes]**&#x200B;以停用订阅，或单击&#x200B;**[!UICONTROL Cancel]**&#x200B;以退出而不更改订阅。

### 停用订阅者后发生的情况

撤销对数据馈送的访问权限会向数据购买者帐户中的所有管理员用户发送通知电子邮件。 电子邮件包含列出吊销特征的附件。 此列表可帮助订阅者在其区段和模型中查找和删除已停用的特征。

### 账单和信息源停用

在删除对数据馈送的访问权限后，订阅者需负责上个月或当月的费用，具体取决于您停用馈送的时间。

## 数据馈送的规划类型 {#plan-types}

[!DNL Plan types]是[!UICONTROL Audience Marketplace]数据馈送中的基本组件。 作为数据提供商，他们允许您为信息源创建多个用例和价格选项。 此外，为每次数据馈送创建几个计划可能是一个不错的策略。 这给购买者提供不同的选项，供他们在寻找要建模或发送到目标的数据时选择。

[创建数据馈送](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)以选择[!UICONTROL Plan Types]。

![](assets/plan_types.png)

## 规划类型和用例选项 {#plan-types-use-cases}

<!-- c_feed_options.xml -->

通过[!UICONTROL Use Case]设置，卖家可控制买家如何使用您的数据。

### 区段和重叠

**[!UICONTROL Segments and Overlap]**&#x200B;用例会创建一个计划，该计划允许购买者比较[特征到特征重叠报表](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)中的特征数据。 此外，购买者可以将您的数据添加到区段，并与[区段到特征](../../../reporting/dynamic-reports/segment-trait-overlap-report.md)和[区段到区段](../../../reporting/dynamic-reports/segment-segment-overlap-report.md)报表进行比较。

每个数据馈送必须至少包含一个[!UICONTROL Segments and Overlap]用例。 如果馈送不包含[!UICONTROL Segments and Overlap]用例（单独使用或与其他用例组合），则购买者无法订阅数据馈送中的其他计划。

重叠比较可以帮助买家：

* **扩大受众范围：**&#x200B;重叠率较低表明您的特征包含购买者之前未曾看到的用户。 因此，购买者可能希望这些特征能够向其受众区段添加新用户。
* **增强现有受众：**&#x200B;高度重叠表明您的特征包含的用户与购买者已知道的用户相似。 因此，购买者可能希望这些特征有助于对已开发的受众进行有针对性、递增式的改进。

按如下方式为此用例定价：

* 单位：固定费用
* 价格：免费（0.00美元）

### 建模

**[!UICONTROL Modeling]**&#x200B;用例创建了一个计划，该计划允许购买者使用[算法建模](../../../features/algorithmic-models/understanding-models.md#understanding-models)将您的特征与其特征进行比较。 购买者查看模型结果，以查找数据中具有相似转化属性的新受众。 按如下方式为此用例定价：

* 单位：固定费用
* 价格：贴现价或市场利率

### 激活

**[!UICONTROL Activation]**&#x200B;用例允许购买者将数据发送到[目标](../../../features/destinations/destinations.md)。 通过此用例，购买者无法将数据与重叠报表或算法模型进行比较。 按如下方式为此用例定价：

* 度量单位： [!DNL CPM]
* 价格： [!DNL CPM]市场价格

## 计费和价格选项 {#billing}

账单和价格选项控制购买者如何支付您的数据。

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">记帐周期</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol">每月缺款</span></b>是唯一选项。 计费周期于每月10日结束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">度量单位</span></b> </td> 
   <td colname="col2">向数据购买者收取CPM费率或固定费用。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 使用CPM定价时，数据购买者需要自行报告使用情况。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">使用固定费用定价时，数据购买者不会报告使用情况，因为他们按固定费率收费。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">价格</span></b> </td>
   <td colname="col2"> 卖方向买方收取的CPM费率或固定费用价格（以美元计）。 </td>
  </tr> 
 </tbody> 
</table>

## 计划注释 {#plan-notes}

在&#x200B;**[!UICONTROL Additional Notes]**&#x200B;字段中，花一些时间描述馈送中的每个数据计划。 好的简短描述有助于购买者了解数据馈送中每个计划的内容或用途。 购买者可以在搜索或评估新数据源时读取数据馈送和计划描述。

## 管理专用数据馈送请求 {#manage-private-requests}

用于管理购买者的专用馈送请求的提供商工作流。

要审核、批准或拒绝采购员请求，请转到[!UICONTROL My Shared Data]并：

<!-- t_private_feed_workflows.xml -->

1. 单击专用数据馈送的名称。
2. 单击&#x200B;**[!UICONTROL Access Requests]**&#x200B;查看所有希望访问您的数据馈送的购买者。
3. 在每个请求框的[!UICONTROL Allow Access]部分中，单击复选标记以批准请求，或单击X以拒绝访问。
4. 在确认弹出窗口中确认或取消所选操作。

## 数据提供商的折扣 {#discounts}

在[!UICONTROL Audience Marketplace]中，折扣允许您降低单个订阅者的数据馈送的发布价格。 您可以为已提交订阅请求的订阅者或请求获取有关数据馈送详细信息的订阅者提供折扣。 折扣适用于[!DNL CPM]和平均费率馈送。 如果您希望为新客户提供订阅奖励或奖励客户忠诚度，折扣会很有帮助。

## 将折扣应用到数据馈送 {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

要折扣信息源，请将折扣金额作为%添加到折扣字段，并确认您的更改。 数据提供商可通过以下任一方式为[!UICONTROL Audience Marketplace]中的数据馈送提供折扣：

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

在这些示例中，卖方为[!UICONTROL Software Audience]数据馈送添加了10%的折扣。

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## 查看打折信息源 {#review-discounted-feeds}

数据提供商可以在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**&#x200B;中查看其所有订阅者和折扣馈送。

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [专用数据信息源](../../../features/audience-marketplace/marketplace-private-feeds.md)
