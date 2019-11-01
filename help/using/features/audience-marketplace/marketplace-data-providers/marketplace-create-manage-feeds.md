---
description: 数据馈送需要名称、说明、数据源和计划类型。 在保存并激活源之前，源将处于禁用状态。 在Audience Marketplace >我的共享数据中设置公共或私有数据源。 仅适用于数据销售者。
seo-description: 数据馈送需要名称、说明、数据源和计划类型。 在保存并激活源之前，源将处于禁用状态。 在Audience Marketplace >我的共享数据中设置公共或私有数据源。 仅适用于数据销售者。
seo-title: 创建、定价和管理数据源
solution: Audience Manager
title: 创建、定价和管理数据源
topic: DIL API
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 创建、定价和管理数据源 {#create-price-and-manage-data-feeds}

数据馈送需要名称、说明、数据源和计划类型。 在保存并激活源之前，源将处于禁用状态。 在 [!UICONTROL Audience Marketplace] &gt;中设置公共或专用数据源 [!UICONTROL My Shared Data]。 仅适用于数据销售者。

## 创建公共或专用数据源 {#create-public-private-data-feed}

数据馈送需要名称、说明、数据源和计划类型。 在保存并激活源之前，源将处于禁用状态。 在中设置公共或专用数据源 **[!UICONTROL Audience Marketplace > My Shared Data]**。 仅适用于数据销售者。

<!-- t_data_feed.xml -->

您必须拥有管理员权限才能创建公共或专用数据源。
要创建数据源，请执行以下操作：

1. 单击 **[!UICONTROL New Data Feed]**.
1. 命名数据源。 数据购买者可以根据名称搜索您的源。
1. 提供简要说明（最多255个字符）。

   正确的描述应准确地描述您的源。 例如，您可以包含营销类别、人口统计和地理覆盖范围的文本(例如， [!DNL US] 或北美)。 描述文本是可搜索的，可帮助购买者查找或评估您的源。 良好的描述是吸引订阅者加入数据源的重要部分。
1. 从选项中选择数据 **[!UICONTROL Data Source]** 源。

   >[!IMPORTANT]
   >
   >属于此数据源的任何当前和未来特征都将作为此源的一部分与数据购买者共享。

1. 在 [!UICONTROL Plan Types]中，选择要使用的选项并单击 **[!UICONTROL Add Plan]**。

   源可包含多个计划。 计划可包含多个用例。 有关详细信息，请参 [阅数据馈送的计划类型](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)。

1. 单 **[!UICONTROL Save]** 击可节省数据费 *用* 。
1. 要保存并激活数据馈送，请执行以下操作：
   1. 将滑块移 **[!UICONTROL Availability]** 动到 **[!UICONTROL Active]**。
   1. 单击 **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* 无法删除已保存和已激活的数据源。
   >* 购买者只能看到活动源。


### 可选：创建专用数据源

在部 [!UICONTROL Settings] 分中，将滑块移动到：

* **[!UICONTROL Private]** 和 **[!UICONTROL Branded]**:买方列表 [!UICONTROL Marketplace] 在提供方列中显示卖方姓名，所有其他数据都隐藏。

* **[!UICONTROL Private]** 和 **[!UICONTROL Unbranded]**:采购员列表仅 [!UICONTROL Marketplace] 显示数据馈送名称和说明。 数据提供者名称显示为 [!UICONTROL Private Seller]。

要查看私有源对购买者的外观，请参阅私有数据源中的购买 [者部分](../../../features/audience-marketplace/marketplace-private-feeds.md)。

## 停用订阅者的数据馈送 {#deactivate-data-feed}

作为数 [!UICONTROL Audience Marketplace] 据提供者，您可以撤销买方对订阅数据馈送的访问权。 您可能希望将买方从源中删除，原因包括延迟付款／不支付费用，或者他们使用特征数据不当。

<!-- marketplace-deactiva4te-subscribers.xml -->

要撤销订阅者，请执行以下操作：

1. 在 [!UICONTROL My Shared Data]中，查找订阅者正在使用的源。

   >[!NOTE]
   >
   >带有过期帐户的数据源会用三角形／感叹号图标标记。

1. 在列中， [!UICONTROL Subscribers] 单击该源的订阅者计数的蓝色数字。 此操作将打开订阅详细信息页面。
1. 将滑块移 **[!UICONTROL Subscription]** 动到 **[!UICONTROL Off]**。 此操作将打开确认对话框窗口。
1. 在弹出窗 [!UICONTROL Confirmation] 口中，单 **[!UICONTROL Yes]** 击以取消激活订阅，或者 **[!UICONTROL Cancel]** 在不进行订阅更改的情况下退出。

### 取消激活订阅后会发生什么情况

撤销对数据馈送的访问权向数据购买者帐户中的所有管理员用户发送通知电子邮件。 电子邮件中包含列出已吊销特征的附件。 此列表可帮助订阅者从其区段和模型中查找和删除取消激活的特征。

### 计费和源取消激活

在您删除对数据源的访问权后，订阅者将负责上个月或当月的费用，具体取决于您取消激活数据源的时间。

## 数据馈送的计划类型 {#plan-types}

[!DNL Plan types] 是数据馈送中的基 [!UICONTROL Audience Marketplace] 本组件。 作为数据提供商，您可以为源创建多个使用案例和价格选项。 此外，为每个数据源创建几个计划可能是一个不错的策略。 这为购买者提供了不同的选择选项，供他们在寻找要建模的数据或发送到目标时进行选择。

[创建要选择的数据源](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)[!UICONTROL Plan Types]。

![](assets/plan_types.png)

## 计划类型和用例选项 {#plan-types-use-cases}

<!-- c_feed_options.xml -->

通过 [!UICONTROL Use Case] 这些设置，卖家可以控制买家如何使用您的数据。

### 区段和重叠

用 **[!UICONTROL Segments and Overlap]** 例创建一个计划，让购买者在特征与特征重叠报 [告中比较特征数据](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)。 此外，购买者可以将您的数据添加到区段，并与区 [段到特征](../../../reporting/dynamic-reports/segment-trait-overlap-report.md)[和区段到区段的报表进行比较](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) 。

每个数据馈送必须包括至少一个 [!UICONTROL Segments and Overlap] 用例。 如果数据馈送中不包含用例(单独或与其他用例组合 [!UICONTROL Segments and Overlap] )，则购买者不能订阅数据馈送中的其他计划。

重叠比较有助于购买者：

* **** 扩大受众范围：重叠程度低表明您的特征包含买家之前从未见过的用户。 因此，购买者可能希望这些特征将新用户添加到其受众细分。
* **** 增强现有受众：重叠程度高表明您的特征包含的用户与买家已了解的用户相似。 因此，购买者可能希望这些特征有助于对已开发受众进行有针对性的渐进改进。

为此用例定价如下：

* 单位：固定费用
* 价格：免费（0.00美元）

### 建模

用 **[!UICONTROL Modeling]** 例可创建一个计划，让买家将您的特征与他们的特征与算法建 [模进行比较](../../../features/algorithmic-models/understanding-models.md#understanding-models)。 购买者查看模型结果，在您的数据中找到与自己具有相似转换属性的新受众。 为此用例定价如下：

* 单位：固定费用
* 价格：折扣或市场价

### 激活

通过 **[!UICONTROL Activation]** 用例，购买者可以将数据发送到 [目标](../../../features/destinations/destinations.md)。 在此用例中，购买者无法将数据与重叠报表或算法模型中的数据进行比较。 为此用例定价如下：

* 单位： [!DNL CPM]
* 价格： [!DNL CPM] 市场率

## 帐单和价格选项 {#billing}

帐单和价格选项控制购买者为您的数据付款的方式。

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 计费周期</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Monthly in Eldands</span></b> （月度欠款）是唯一的选择。 结算周期于每月第10天结束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 单位</span></b> </td> 
   <td colname="col2">按CPM费率或固定费用向数据购买者收费。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 使用CPM定价时，数据购买者必须自行报告使用情况。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">由于定价固定不变，数据购买者不会报告使用情况，因为他们收费固定。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 价格</span></b> </td>
   <td colname="col2"> 卖家以CPM费率或统一费用价格向买家收取的金额（以美元为单位）。 </td>
  </tr> 
 </tbody> 
</table>

## 计划说明 {#plan-notes}

在该字 **[!UICONTROL Additional Notes]** 段中，需要一些时间来描述源中的每个数据计划。 简短的简短描述有助于购买者了解数据馈送中每个计划的内容或用途。 购买者在搜索或评估新数据源时可以读取数据馈送和计划说明。

## 管理专用数据馈送请求 {#manage-private-requests}

用于管理来自买方的私有源请求的提供商工作流。

要审核、批准或拒绝采购员请求，请转到 [!UICONTROL My Shared Data] 和：

<!-- t_private_feed_workflows.xml -->

1. 单击专用数据源的名称。
2. 单击 **[!UICONTROL Access Requests]** 查看所有希望访问您的数据源的购买者。
3. 在每个 [!UICONTROL Allow Access] 请求框的部分，单击复选标记以批准请求，或单击X以拒绝访问。
4. 在确认弹出窗口中确认或取消选定的操作。

## 数据提供商的折扣 {#discounts}

在 [!UICONTROL Audience Marketplace]中，折扣允许您降低单个订阅者的数据源的发布价格。 您可以向已提交订阅请求的订阅者或已请求有关数据馈送的详细信息的订阅者提供折扣。 折扣适用于 [!DNL CPM] 统一费率源。 当您希望为新客户提供订阅奖励或奖励客户忠诚度时，折扣会很有帮助。

## 对数据馈送应用折扣 {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

要折扣源，请在折扣字段中添加折扣金额(%)，并确认您的更改。 数据提供商可以从以下任一位置将数据馈 [!UICONTROL Audience Marketplace] 送折扣为：

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

在这些例子中，卖家为数据馈送增加了10% [!UICONTROL Software Audience] 的折扣。

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## 查看折扣源 {#review-discounted-feeds}

数据提供商可以在中查看其所有订阅者和折扣源 **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**。

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [专用数据信息源](../../../features/audience-marketplace/marketplace-private-feeds.md)

