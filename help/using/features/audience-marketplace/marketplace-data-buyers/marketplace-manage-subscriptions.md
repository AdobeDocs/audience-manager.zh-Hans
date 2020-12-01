---
description: 在Marketplace中，数据购买者可以进行研究并订阅公共和私有数据服务。 按照以下步骤订阅公共数据源。
seo-description: 在Marketplace中，数据购买者可以进行研究并订阅公共和私有数据服务。 按照以下步骤订阅公共数据源。
seo-title: 管理数据信息源订阅
solution: Audience Manager
title: 管理数据信息源订阅
topic: DIL API
uuid: 7305adb6-cbb8-4430-8204-2243095c0ba5
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '2186'
ht-degree: 2%

---


# 管理数据信息源订阅 {#manage-data-feed-subscriptions}

[!UICONTROL Marketplace]是数据购买者研究和订阅公共和私有数据服务的位置。 按照以下步骤订阅公共数据源。

## 订阅公共数据源{#subscript-public-data-feed}

[!UICONTROL Marketplace]是数据购买者研究和订阅公共和私有数据服务的位置。 按照以下步骤订阅公共数据源。

<!-- t_subscribe_feed.xml -->

订阅公共数据源：

1. 转至&#x200B;**[!UICONTROL Audience Marketplace > Marketplace]**。 使用搜索功能或浏览列表以查找数据源。

   ![订阅](assets/subscribe1.png)

1. 单击要使用的数据源的名称。 此操作将打开所选源的[计划详细信息页面](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)。

   ![计划详细信息](assets/plan-details.png)

1. 从“订阅”表中选择用例，并：
   * 将&#x200B;**[!UICONTROL Subscription]**&#x200B;滑块移动到&#x200B;**[!UICONTROL On]**。
   * 单击 **[!UICONTROL Review & Subscribe]**. 这将打开[!UICONTROL Terms and Conditions]窗口。

   ![订阅](assets/subscribe3.png)

1. 在[!UICONTROL Terms and Conditions]窗口中：

   * **重要：** 选中 **[!UICONTROL ID sync]** 该复选框。此设置有助于提高与数据提供者的匹配率。
   * 选中条款和条件框并单击&#x200B;**[!UICONTROL Accept]**&#x200B;以完成订阅过程。

   ![订阅](assets/subscribe4.png)

### 后续步骤

订阅数据源后：

* 检查您的[!UICONTROL Traits]文件夹，验证订阅。 请参阅[订阅存储源](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee)。

* 查看账单和付款文档。 请参阅以下相关链接。

### 最佳实践 {#best-practices}

以下是我们建议您在使用[!UICONTROL Audience Marketplace]时遵循的一组最佳实践：

当通过[!UICONTROL Audience Marketplace]探索新的第三方数据集和第二方数据集时，我们建议的第一步是为[!UICONTROL Segments & Overlap]启用数据服务。 这允许用户通过构建细分来评估受众大小并运行重叠报告来浏览受众，从而获得初始数据洞察。 大多数数据提供者免费优惠此用例，因此您无需支付额外费用即可执行此分析。

运行重叠报告时，请遵循以下最佳实践，确保获得有用的结果。

1. 确保您的重叠数据集在数据类型和收集方法方面相似，例如：
   * 访客地理
   * Cookie与移动ID
   * 回顾窗口
   * 脱机与联机活动
   * 数据提供程序刷新数据的频率

1. 重叠可能随时间而略有增加，因此，请确保在运行重叠报告之前允许最多30天通过，以便数据同步。
1. 如果您在多个营销活动中使用来自数据提供商的数据，重叠会增加。
和计划。 这为来自两个数据集的用户提供了更多同步机会。
1. 无法保证您的数据集之间存在重叠。 要使重叠有效，客户数据集中的用户必须与数据关联
在报告时间帧内提供者数据集。 如果客户的媒体数据未提供给数据提供者数据集中的用户，则永远不会出现重叠。
1. 别把低重叠视为坏事。 利用低重叠潜在客户和吸引新用户。

## 订阅专用数据源{#subscript-private-data-feed}

购买者订阅&#x200B;**[!UICONTROL Audience Marketplace > Marketplace]**&#x200B;中的私有数据源和计划。

<!-- t_private_feed.xml -->

>[!TIP]
>
>有时，数据提供商可能会优惠私有数据源的折扣。 提交订阅请求时，您可能想要询问是否可能享受折扣。

要订阅专用数据源，请执行以下操作：

1. 单击[!UICONTROL Marketplace]中的数据源名称。
1. 单击 **[!UICONTROL Request Access]**. 这将打开请求对话框。
1. 在“请求”对话框中，为提供者写一份说明，表明您对其数据源感兴趣，然后单击&#x200B;**[!UICONTROL Send]**。 卖家将审核您的消息，批准或拒绝您的请求。 等待批准时，该数据源的[!UICONTROL Marketplace]列表中显示“已请求”。

   * **[!UICONTROL Request approved]**:列表中的状 [!UICONTROL Marketplace] 态将变为“已授予访问权限”，您将收到自动通知。此时，您可以订阅源。 有关说明，请参阅[订阅公共数据源](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)。
   * **[!UICONTROL Request denied]**:“已请求”文本将从源 [!UICONTROL Marketplace] 列表中删除。您可以再次尝试订阅或选择其他源。

## 购买者的数据馈送折扣{#buyer-discount}

在[!UICONTROL Audience Marketplace]中，提供商可以优惠购买者在[!DNL CPM]或统一费率数据馈送的发布价格上享受折扣。 但是，折扣额在[!DNL Marketplace]源列表中对买家不可见。 但是，在订阅专用数据源或请求有关特定源的更多信息时，您也可以要求折扣。

## 申请折扣{#request-discount}

<!-- marketplace-buyer-discounts.xml -->

<table id="table_3C6E58F593BA48EC89ACBD9A26E4E74F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 采购员状态 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>当前订阅者</b> </p> </td> 
   <td colname="col2"> <p>如果您已订阅专用数据源并希望申请折扣： </p> 
    <ol id="ol_A58D419EBB9349E9B1225202535130F6"> 
     <li id="li_D0DDC8AC6E9C4675AA4630D63FE8F071"> <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe"> 取</a> 消订阅数据源。 </li> 
     <li id="li_05A5379F2A944FB28AB39C196DDE3A1D">与数据提供商联系并申请折扣价。 </li> 
     <li id="li_B1B5AA6F6CC64512A02D5E8861A5F266">如果提供商为您提供折扣，请在下个月的1<sup>st</sup>天重新订阅源。 </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>新的专用数据馈送订阅者</b> </p> </td> 
   <td colname="col2"> <p>在您的订阅请求中要求折扣。 请参阅<a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed">订阅专用数据源</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>潜在订阅者</b> </p> </td> 
   <td colname="col2"> <p><a href="../../../features/audience-marketplace/marketplace-private-feeds.md">潜在用户</a>是已请求访问私有数据馈送、已接收卖家批准但尚未订阅该馈送的数据买家。 作为潜在订户请求折扣： </p> 
    <ol id="ol_9CECDA92E7894B20AC8A777D78962188"> 
     <li id="li_618B64160CF24549AFCA73E006DCA35A">转到<b><span class="uicontrol">Audience Marketplace&gt; Marketplace</span></b>。 </li> 
     <li id="li_FE52A06B30FC4858B48AF81954365FE9">单击您已获得批准的源的名称。 </li> 
     <li id="li_763C050AC9464BE380D00F6085B6E540">单击<b><span class="uicontrol">请求更多详细信息</span></b>。 在向卖家索要详细信息时要求折扣。 </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## 查看折扣源{#review-discounted-feeds}

要查看折扣源，请执行以下操作：

1. 转至&#x200B;**[!UICONTROL Audience Marketplace > Marketplace]**。
1. 单击您已订阅的源的名称。
1. 查看[!UICONTROL Plan Details]表中的[!UICONTROL Price]和[!UICONTROL Your Price]列。 如果订阅源已折扣：

   * 原价标有红线。
   * [!UICONTROL Your Price]列中的费用将低于[!UICONTROL Price]列中的费用。

在示例中，采购员在&#x200B;**[!UICONTROL Software Audience Feed]**&#x200B;中的[!UICONTROL Segments and Overlap]计划上可享受10%的折扣。

![](assets/buyer-discount.png)

## 查找订阅的信息源数据 {#find-subscribed-data-fee}

数据馈送的数据（特征）显示在其自己的特征存储文件夹中。 转到&#x200B;**[!UICONTROL Audience Data > Traits]**&#x200B;并展开&#x200B;**[!UICONTROL 3rd-Party Data]**&#x200B;文件夹以视图并处理订阅源中的特征。 查找以数据提供程序命名的子文件夹。 这些文件夹包含以单个数据源和源提供的列表特征命名的文件夹。

<!-- marketplace-feed-storage.xml -->

![](assets/subscribe5.png)

## 取消订阅数据源{#unsubscribe}

数据购买者取消订阅&#x200B;**[!UICONTROL Audience Marketplace > Marketplace]**&#x200B;中的数据馈送和计划。

<!-- t_unsubscribe_feed.xml -->

取消订阅数据源：

1. 单击[!UICONTROL Marketplace]中的数据源名称。
1. 在[!UICONTROL Use Case]部分中，找到要使用的计划并将&#x200B;**[!UICONTROL Subscription]**&#x200B;滑块移动到&#x200B;**[!UICONTROL Off]**。

## 数据源取消激活：发生原因及响应方法{#data-feed-deactivation-reasons}

在[!UICONTROL Audience Marketplace]中，数据提供者可以撤销对您订阅的数据服务的访问权限。 如果你发生了这事，别惊慌。 我们掩护你。 查看本节以了解与数据源取消激活相关的流程和过程。

## 数据源取消激活的常见原因{#reasons-for-deactivation}

<!-- marketplace-subscriber-deactivated.xml -->

如果你所订阅的饲料被关闭，这可能令人费解，甚至令人不安。 但是，由于各种原因，数据提供者可以取消激活数据源。 一些常见原因包括：

* **计费：** 如果您始终延迟支付费用或未支付费用，数据提供商将取消激活源。
* **源更新：数** 据提供者在更新其源分类或成本结构时需要取消激活源。
* **非活动买** 家：如果订阅者在较长时间内没有显示支出，数据提供商保留取消激活源的权利。
* **不活跃的卖家：** 离开的数据提供 [!UICONTROL Audience Marketplace] 商将取消激活并删除其所有数据服务。

>[!TIP]
>
>如果您认为数据源被错误取消激活，请直接与数据提供商联系。 您的[!DNL Adobe]顾问可以帮助您获得联系信息或其他支持。

## 取消激活电子邮件{#deactivation-email}

当数据提供者取消激活您的某个数据服务时，[!DNL Audience Manager]会向您公司中具有[!UICONTROL Administrator]权限的用户发送电子邮件。 有时，电子邮件过滤器会将此邮件归类为垃圾邮件。 因此，您可能会错过此重要通知。 为帮助您识别取消激活消息，此电子邮件包含以下元素：

* **发件人：** 取消激活电子邮件来自 `aam-noreply@adobe.com`。专业提示：请勿回复此电子邮件。

* **主题行：** 订阅 *到数据源名* 称此处取消。

* **附件：** 电子邮件包含标题为“”的附 `list-of-affected-entities-by-feed-revocation.csv`件。这是一种复杂的说法，即依恋列表了取消的饲料中包含的所有特征。 作为数据购买者，您应复查此附件。 它将帮助您从细分和[算法模型](../../../features/algorithmic-models/understanding-models.md)中查找和删除停用特征。

## 已停用特征列表{#deactivation-trait-list}

取消激活电子邮件附带的列表包含以下字段。

<table id="table_5C3800F9D8AA43EFAB4690959A721F63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字段 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 数据源ID</span></b> </p> </td> 
   <td colname="col2"> <p>已停用数据馈送的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 数据源名称</span></b> </p> </td> 
   <td colname="col2"> <p>已停用数据源的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 特征SID</span></b> </p> </td> 
   <td colname="col2"> <p>已停用特征ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 特征名称</span></b> </p> </td> 
   <td colname="col2"> <p>已停用的特征名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 段SID</span></b> </p> </td> 
   <td colname="col2"> <p>包含已停用特征的区段的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 区段名称</span></b> </p> </td> 
   <td colname="col2"> <p>包含已停用特征的区段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo Model ID</span></b> </p> </td> 
   <td colname="col2"> <p>包含已停用特征的算法模型的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo模型名称</span></b> </p> </td> 
   <td colname="col2"> <p>包含取消激活特征的算法模型的名称。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 删除已停用的特征{#remove-deactivated-traits}

作为数据购买者，您负责从所有有效／使用中或不活动的区段中删除已取消源中的特征。 删除选项包括：

* 使用[REST API](../../../api/rest-api-main/rest-api-main.md)或[批量管理工具](../../../reference/bulk-management-tools/bulk-management-intro.md)进行批量删除。

* 使用[!UICONTROL Segment Builder]手动搜索受影响的区段并删除取消激活的特征。 请参阅[从区段](../../../features/segments/segment-builder.md#segment-builder-controls-traits)删除特征。

>[!NOTE]
>
>从活动算法模型或目标中删除特征会影响规模和定位准确性。 尽可能尝试用新的活动特征替换已吊销的特征。

[从您的帐户中删除所](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe) 有已撤销的特征后，取消订阅已取消激活的数据馈送。如果这是临时取消激活，您可以在数据提供程序完成其所需的更改并重新激活源后重新订阅。 与大多数情况一样，与合作伙伴（数据提供商和[!DNL Adobe]）的良好沟通可以帮助您完成此过程。

## 了解受众市场中的计划详细信息页面 {#marketplace-buyer-details}

单击[!UICONTROL Marketplace]中的数据计划名称时，[!DNL Audience Manager]会提供一些信息，帮助您在订阅数据源时做出明智的选择。

<!-- marketplace-buyer-details.xml -->

![](assets/plan-details-numbered.png)

此页面提供以下信息：

1. **基本计划信息**。这包括信息源，例如：
   * 数据源名称。 例如，如上所示，此源的名称为“示例数据源”。
   * 数据提供者的名称；
   * 数据源ID;
   * 描述;
   * 饲料中的特征数；

1. 计划信息按钮。
   * 单击&#x200B;**[!UICONTROL Explore All Traits]**&#x200B;查看有关所选数据源中所有特征的详细信息。
   * 单击&#x200B;**[!UICONTROL Request More Details]**&#x200B;可向数据提供程序询问有关所选数据源的问题或请求折扣。 此功能会直接将您的评论和问题发送给数据提供者。

1. 数据馈送报告指标。 活动图（和相关指标）显示过去30天的特征重叠数据。 请参阅[市场：有关详细信息，请参阅](marketplace-data-buyers.md#about-marketplace)。
   * **[!UICONTROL 30 Day Overlapped Uniques]**:您帐户中与提供商帐户中的用户重叠的唯一用户数。有关唯一用户的定义，请参阅Audience Manager](/help/using/reference/ids-in-aam.md)中[ ID索引中的AAM UUID。
   * **[!UICONTROL 30 Day Provider Unique Users]**:来自提供商帐户的唯一用户数。
   * **[!UICONTROL Your Unique Users]**:来自您帐户的唯一用户数。

1. **[!UICONTROL Plan Details]** 表. 此表显示了可订阅数据源的用例及其定价模式。 请参阅[了解数据馈送用例](#use-cases)。

1. 计划操作按钮。
   * 单击&#x200B;**[!UICONTROL Cancel]**&#x200B;离开页面而不进行更改。
   * 单击&#x200B;**[!UICONTROL Review & Subscribe]**&#x200B;订阅数据源。 在您将[!UICONTROL Subscription]切换到[!UICONTROL On]之前，此按钮将一直灰显。 另请参阅[订阅公共数据源](#subscript-public-data-feed)和[订阅专用数据源](#subscript-private-data-feed)。

## 了解数据源用例{#use-cases}

作为[!UICONTROL Audience Marketplace]数据购买者，您可以为重叠、建模和激活用例购买数据。 每个用例都针对特定用途而设计，并限制您可以处理数据的方式。 这些用例描述可以帮助您正确决定要购买哪种类型的数据计划。

## 与区段和重叠计划进行比较{#comparisons}

<!-- c_use_cases_for_buyers.xml -->

### 区段和重叠

此用例允许您在[trait-to-trait重叠报告中将您的特征与提供者特征进行比较。](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) 此外，您还可以创建提供者特征或将提供者特征添加到区段，并与区 [段到交易和](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) 区 [段到区段的报表进行更](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) 多比较。重叠比较可以帮助您：

* **扩大受众范围：** 低重叠意味着您的特征包含您以前从未见过的用户。您可能希望这些特征尝试触及新用户。
* **增强现有受众:** 重叠程度高表明您的特征与数据提供者拥有的特征相似。您可能希望这些特征有助于对已开发的受众进行有针对性的增量改进。

### 算法模型

此用例允许您使用[算法建模](../../../features/algorithmic-models/understanding-models.md#understanding-models)根据您的特征评估供应商特征。 例如，我们的算法建模系统使用您的某个特征作为与供应商特征进行比较的基础。 运行模型时，它可以显示供应商特征中的受众是否与您的特征共享相似的转换属性。

### 激活

此用例允许您将数据发送到[目标](../../../features/destinations/destinations.md)。 在[!DNL Audience Manager]中，目标是任何第三方系统（ad server、[!DNL DSP]、[!DNL DMP]、exchange等） 任何其他系统（广告服务器、DSP、广告网络等）。但是，对于[!UICONTROL Activation]用例，您无法运行重叠报告或测试算法模型中的数据。

>[!MORELIKETHIS]
>
>* [CPM数据源的计费和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [统一费用数据源的计费和印象分配](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [如何报告CPM使用情况](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
>* [订阅公共数据源](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)
>* [数据购买者的折扣](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
>* [市场：关于](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)

