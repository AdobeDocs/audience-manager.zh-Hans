---
description: 私人数据源是允许提供商限制访问其数据的选项。在创建和订阅私人数据服务之前，数据提供商和购买者应查看此信息。
seo-description: 私人数据源是允许提供商限制访问其数据的选项。在创建和订阅私人数据服务之前，数据提供商和购买者应查看此信息。
seo-title: 专用数据信息源
solution: Audience Manager
title: 专用数据信息源
uuid: e4ca59ca-bhone9-4897-9374-8f3 d54 b2 beee
translation-type: tm+mt
source-git-commit: 21b2505ac6cdf97b401bf0b0ac80bf1964f084b8

---


# 专用数据信息源 {#private-data-feeds}

私人数据源是允许提供商限制访问其数据的选项。在创建和订阅私人数据服务之前，数据提供商和购买者应查看此信息。

<!-- c_marketplace_privatefeed.xml -->

## Private Data Feeds for Providers {#private-data-feeds-providers}

作为提供商，您的数据服务可以是公共或私有的。私人数据源允许您限制对数据的访问，包括数据卖家的姓名。您可能需要创建私人数据服务，以提供特殊交易、折扣或隐私和访问控制。通过私人数据源，您可以查看和批准买家请求。批准请求后，源看起来就像是向买家提供的公共数据源。You can view and manage all your feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. 如下所示，此类型的源在状态列中标记为“Private”。

![](assets/my_shared_data.png)

### 管理源请求

Clicking the name of a private data feed from [!UICONTROL My Shared Data] takes you to a page that contains several tabs. 单击选项卡以管理您的专用数据源请求。

![](assets/shared_data_tabs.png)

下表定义了每个操作选项卡提供的角色或函数。

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制表符 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 当前订阅者</span></b> </p> </td> 
   <td colname="col2"> <p>列出已订阅私人数据源的已批准购买者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 潜在订阅者</span></b> </p> </td> 
   <td colname="col2"> <p>列出未订阅私人数据源的已批准购买者。 </p> <p>通过批准，购买者可以像公开一样查看数据源。这使他们有机会在订阅之前查看和评估您的源。您还可以为作为潜在订阅者列出的购买者提供数据服务折扣。Once the buyer subscribes, their profile moves to <b><span class="uicontrol"> Current Subscribers</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 访问请求</span></b> </p> </td>
   <td colname="col2"> <p>列出私人数据源的新订阅请求。单击此选项卡以查看、批准或拒绝买家请求。 </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Approved buyers move to <b><span class="uicontrol"> Potential Subscribers</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Rejected buyers move to <b><span class="uicontrol"> Denied Access</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 详细信息请求</span></b> </p> </td>
   <td colname="col2"> <p>列出尚未订阅数据源的已批准购买者，并请求有关您的源的更多信息。 </p> <p>通过批准，购买者可以像公开一样查看数据源。这使他们有机会在订阅之前查看和评估您的源。您还可以为请求访问的购买者提供数据服务折扣。响应详细信息请求将从此选项卡中删除购买者配置文件。If they haven't subscribed, the buyer profile is still in <b><span class="uicontrol"> Potential Subscribers</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 拒绝访问</span></b> </p> </td> 
   <td colname="col2"> <p>列出专用数据源的拒绝订阅请求。 </p> <p>To re-approve denied buyers, change the <span class="wintitle"> Rejection Status</span> to <b><span class="uicontrol"> Allow</span></b>. This moves the buyer to <b><span class="uicontrol"> Potential Subscribers</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 后续步骤

以下文档可帮助您开始使用私有数据源。

* [创建公共或专用数据源](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [审核、批准或拒绝私人源请求](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [适用于购买者的专用数据馈送](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Private Data Feeds for Buyers {#private-data-feeds-for-buyers}

As a buyer, private data feeds appear in the [Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) like any other offer. 但是，在这种情况下，源列表不显示特征、唯一用户和用户重叠的摘要信息。Also, the data seller has an option to show or hide their name in the [!UICONTROL Provider] column of the [!UICONTROL Marketplace] list. 卖家批准订阅请求后，您可以使用私人源中的所有数据(其工作方式与公共源类似)。The [!UICONTROL Marketplace] example below lists the 3 different feed types available to you as a buyer.

![](assets/buyer_marketplace.png)

源类型包括：

下表描述了这些不同的源类型显示或隐藏数据的方式。

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 信息源类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 公共</span></b> </p> </td> 
   <td colname="col2"> <p>提供商的名称、特征和唯一数据将显示在列表中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 无品牌专用私人</span></b> </p> </td> 
   <td colname="col2"> <p>提供商的名称设置为“私人卖家”，您无法看到特征计数、唯一数据和特征重叠数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 使用品牌专用</span></b> </p> </td> 
   <td colname="col2"> <p>该提供者的名称显示在列表中，但您无法看到特征计数、唯一数据和特征重叠数据。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 后续步骤

请参阅[订阅私人数据源](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 以请求访问权限。

## How to set up the Sharing Relationship between Data Provider and Data Buyer {#set-up-sharing-relationship}

### 步骤-支持-数据提供商和数据购买商

流程中的第一步需要来自Adobe咨询或客户关怀的干预。数据提供商和数据购买者应联系Adobe咨询或客户关怀部门以请求启用。

### 步骤-数据提供程序-创建新数据源

在Audience Manager帐户中，创建一个新的cookie数据源，其中包含：

* **Audience Manager ID** 作为入站密钥；
* The **Share Enabled** option checked.

![](assets/create-datasource.png)

After you click **Save**, a new subfolder is automatically created in **Traits Storage &gt; 3rd Party Data**.

![](assets/folder-structure.png)

### 步骤-数据提供程序-标识用于共享的特征

在此步骤中，您可以识别要与合作伙伴共享的特征。您可以创建新特征或编辑现有特征。在任何情况下，您都需要特征：

* 与作为步骤的一部分创建的数据源关联。
* 存储在新创建的子文件夹中，在第三方数据下。

Read more about [creating traits](/help/using/features/traits/create-onboarded-rule-based-traits.md) and [editing traits](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### 步骤-数据提供程序-创建数据源

接下来，创建数据源，与数据购买者共享特征。Refer to [Create a Public or Private Data Feed](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) for instructions on how to create a data feed.

>[!IMPORTANT]
>
>在设置中，选择专用选项。如果将此字段设置为公共，则任何Audience Marketplace客户都可以订阅您的源。

![](assets/create-data-feed.png)

### 步骤-数据买家-请求访问权限

Go to **Audience Marketplace &gt; Marketplace**. 搜索上一步中由数据提供程序创建的数据源。Click **Request Access**. 数据提供商端的指定联系人现在将收到电子邮件通知。See also, [Subscribe to a Private Data Feed](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### 步骤-数据提供程序-授予访问权限

Go to **Audience Marketplace &gt; My Shared Data** and search for the feed you created in step 4. Click into the new access request and click **Allow Access** to approve the request. See also, [Review, Approve, or Reject Private Feed Requests](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### 步骤-数据买家-开启订阅

After the data provider grants access to the data feed, you can see the feed in your account in **Audience Marketplace &gt; Marketplace**. Review the details, turn the Subscription button ON, and click **Review &amp; Subscribe**. See [Storage for Subscribed Data Feeds](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) for information on where to find the 3rd party traits.

请注意，这些特征只能在数据提供者的帐户中进行编辑。




