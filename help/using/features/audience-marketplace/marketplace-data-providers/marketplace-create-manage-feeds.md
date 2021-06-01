---
description: 数据馈送需要名称、描述、数据源和计划类型。 在保存并激活信息源之前，信息源处于禁用状态。 在“Audience Marketplace”>“我的共享数据”中设置公共或专用数据馈送。 仅供数据销售者使用。
seo-description: 数据馈送需要名称、描述、数据源和计划类型。 在保存并激活信息源之前，信息源处于禁用状态。 在“Audience Marketplace”>“我的共享数据”中设置公共或专用数据馈送。 仅供数据销售者使用。
seo-title: 创建、定价和管理数据信息源
solution: Audience Manager
title: 创建、定价和管理数据信息源
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 2%

---

# 创建、定价和管理数据信息源 {#create-price-and-manage-data-feeds}

## 创建公共或专用数据馈送{#create-public-private-data-feed}

数据馈送需要名称、描述、数据源和计划类型。 在保存并激活信息源之前，信息源处于禁用状态。 在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data]**&#x200B;中设置公共或专用数据馈送。 仅供数据销售者使用。

<!-- t_data_feed.xml -->

您必须具有管理员权限，才能创建公共或专用数据馈送。
要创建数据馈送，请执行以下操作：

1. 单击 **[!UICONTROL New Data Feed]**.
1. 命名数据馈送。 数据购买者可以根据名称搜索您的信息源。
1. 提供简短描述（最多255个字符）。

   应该能够准确描述您的馈送。 例如，您可以包含营销类别、人口统计和地理覆盖范围（例如，[!DNL US]或北美地区）的文本。 描述文本是可搜索的，可帮助购买者查找或评估您的信息源。 良好的描述是吸引数据馈送订阅者的重要部分。
1. 从&#x200B;**[!UICONTROL Data Source]**&#x200B;选项中选择数据源。 数据馈送仅限于单个数据源。 您无法将多个数据源分配给同一数据馈送。

   >[!IMPORTANT]
   >
   >属于此数据源的任何当前和将来特征都将作为此数据源的一部分与您的数据购买者共享。

1. 在[!UICONTROL Plan Types]中，选择要使用的选项，然后单击&#x200B;**[!UICONTROL Add Plan]**。

   信息源可以包含多个计划。 计划可以包含多个用例。 有关详细信息，请参阅[数据馈送的规划类型](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types)。

1. 单击&#x200B;**[!UICONTROL Save]**&#x200B;保存数据馈送&#x200B;*，而不激活*。
1. 要保存和激活数据馈送，请执行以下操作：
   1. 将&#x200B;**[!UICONTROL Availability]**&#x200B;滑块移动到&#x200B;**[!UICONTROL Active]**。
   1. 单击 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* 无法删除保存和激活的数据馈送。
   >* 购买者只能查看活动馈送。


### 可选：创建专用数据馈送

在[!UICONTROL Settings]部分中，将滑块移动到：

* **[!UICONTROL Private]** 和 **[!UICONTROL Branded]**:买方列表 [!UICONTROL Marketplace] 在提供方列中显示卖方的名称，并隐藏所有其他数据。

* **[!UICONTROL Private]** 和 **[!UICONTROL Unbranded]**:采购员列表 [!UICONTROL Marketplace] 仅显示数据馈送名称和描述。数据提供程序名称显示为[!UICONTROL Private Seller]。

要了解私有馈送对购买者的外观，请参阅[私有数据馈送](../../../features/audience-marketplace/marketplace-private-feeds.md)中的“购买者”部分。

## 停用订阅者的数据馈送 {#deactivate-data-feed}

作为[!UICONTROL Audience Marketplace]数据提供商，您可以撤消购买者对订阅数据馈送的访问权限。 您可能由于延迟付款/不支付费用等原因或不当使用特征数据而希望从馈送中删除购买者。

<!-- marketplace-deactiva4te-subscribers.xml -->

要撤消订阅者：

1. 在[!UICONTROL My Shared Data]中，找到订阅者正在使用的馈送。

   >[!NOTE]
   >
   >具有逾期帐户的数据馈送带有三角形/感叹号图标。

1. 在[!UICONTROL Subscribers]列中，单击用于计数该馈送订阅者的蓝色数字。 这将打开订阅详细信息页面。
1. 将&#x200B;**[!UICONTROL Subscription]**&#x200B;滑块移动到&#x200B;**[!UICONTROL Off]**。 这将打开确认对话框窗口。
1. 在[!UICONTROL Confirmation]弹出窗口中，单击&#x200B;**[!UICONTROL Yes]**&#x200B;停用订阅，或单击&#x200B;**[!UICONTROL Cancel]**&#x200B;退出而不进行订阅更改。

### 停用订阅者后会发生什么情况

撤销对数据馈送的访问权限，会向数据购买者帐户中的所有管理员用户发送通知电子邮件。 电子邮件包含一个列出已吊销特征的附件。 此列表可帮助订阅者从其区段和模型中查找和删除已停用的特征。

### 计费和信息源停用

在您删除了对数据馈送的访问权限后，订阅者将对上个月或当月的费用负责，具体取决于您停用该馈送的时间。

## 数据馈送{#plan-types}的规划类型

[!DNL Plan types] 是数据馈送中的基 [!UICONTROL Audience Marketplace] 本组件。作为数据提供商，您可以为信息源创建多个用例和价格选项。 此外，为每个数据馈送创建一些计划是一个不错的策略。 这为购买者提供了不同的选项，供他们在寻找要建模的数据或将数据发送到目标时进行选择。

[创建要选择](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) 的数据馈 [!UICONTROL Plan Types]送。

![](assets/plan_types.png)

## 计划类型和用例选项{#plan-types-use-cases}

<!-- c_feed_options.xml -->

[!UICONTROL Use Case]设置允许销售者控制购买者如何使用您的数据。

### 区段和重叠

**[!UICONTROL Segments and Overlap]**&#x200B;用例会创建一个计划，让购买者可以在[特征到特征重叠报表](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)中比较特征数据。 此外，购买者还可以将您的数据添加到区段，并与[segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md)和[segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md)报表进行比较。

每个数据馈送必须至少包含一个[!UICONTROL Segments and Overlap]用例。 如果数据馈送中不包含[!UICONTROL Segments and Overlap]用例（单独或与其他用例结合使用），则购买者无法订阅数据馈送中的其他计划。

重叠比较有助于购买者：

* **扩展受众范围：** 重叠程度较低意味着您的特征包含购买者以前从未见过的用户。因此，购买者可能希望这些特征将新用户添加到其受众区段。
* **增强现有受众：** 重叠程度较高意味着您的特征包含的用户与购买者已经了解的用户类似。因此，购买者可能希望这些特征有助于对已开发受众进行有针对性的渐进式改进。

为此用例定价如下：

* 单位：固定费用
* 价格：免费（0.00美元）

### 建模

**[!UICONTROL Modeling]**&#x200B;用例会创建一个计划，让购买者将您的特征与其特征进行比较，并使用[算法建模](../../../features/algorithmic-models/understanding-models.md#understanding-models)。 购买者可查看模型结果，以在您的数据中找到与其自己具有相似转化属性的新受众。 为此用例定价如下：

* 单位：固定费用
* 价格：折扣或市价

### 激活

**[!UICONTROL Activation]**&#x200B;用例允许购买者将数据发送到[目标](../../../features/destinations/destinations.md)。 使用此用例时，购买者无法比较重叠报表或算法模型中的数据。 为此用例定价如下：

* 单位：[!DNL CPM]
* 价格：[!DNL CPM]市场汇率

## 帐单和价格选项 {#billing}

帐单和价格选项可控制购买者如何为您的数据付费。

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选项 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 账单周期</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 每月在阿</span></b> 雷西斯是唯一选择。账单周期在每月第10天结束。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 单位</span></b> </td> 
   <td colname="col2">按CPM费率或固定费用向数据购买者收费。 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> 使用CPM定价，数据购买者需要自行报告使用情况。 </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">使用固定费用定价，数据购买者不会报告使用情况，因为他们的费用是固定的。 </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 价格</span></b> </td>
   <td colname="col2"> 卖方按CPM费率或固定费用价格（以美元为单位）向买方收取的金额。 </td>
  </tr> 
 </tbody> 
</table>

## 计划说明{#plan-notes}

在&#x200B;**[!UICONTROL Additional Notes]**&#x200B;字段中，请花些时间描述馈送中的每个数据计划。 简要的简要说明有助于购买者了解数据馈送中每个计划的内容或用途。 购买者在搜索或评估新数据源时，可以读取数据馈送和计划描述。

## 管理专用数据馈送请求{#manage-private-requests}

用于管理购买者私有馈送请求的提供商工作流。

要审核、批准或拒绝采购员请求，请转到[!UICONTROL My Shared Data]，然后：

<!-- t_private_feed_workflows.xml -->

1. 单击专用数据馈送的名称。
2. 单击&#x200B;**[!UICONTROL Access Requests]**&#x200B;以查看所有希望访问您的数据馈送的购买者。
3. 在每个请求框的[!UICONTROL Allow Access]部分中，单击复选标记以批准请求，或单击X以拒绝访问。
4. 在确认弹出窗口中确认或取消您选择的操作。

## 数据提供商的折扣 {#discounts}

在[!UICONTROL Audience Marketplace]中，折扣允许您降低单个订阅者的数据馈送的发布价格。 您可以向已提交订阅请求的订阅者或已请求数据馈送详细信息的订阅者提供折扣。 折扣适用于[!DNL CPM]和固定费率馈送。 当您想要为新客户提供订阅奖励或奖励客户忠诚度时，折扣会很有帮助。

## 对数据馈送{#apply-discounts}应用折扣

<!-- marketplace-seller-discounts.xml -->

要对馈送进行折扣，请在折扣字段中添加折扣金额(%)，并确认您所做的更改。 数据提供程序可以通过以下任一方式在[!UICONTROL Audience Marketplace]中打折数据馈送：

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

在这些示例中，卖家为[!UICONTROL Software Audience]数据馈送增加了10%的折扣。

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## 查看折扣馈送{#review-discounted-feeds}

数据提供商可以在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**&#x200B;中查看其所有订阅者和折扣馈送。

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [专用数据信息源](../../../features/audience-marketplace/marketplace-private-feeds.md)

