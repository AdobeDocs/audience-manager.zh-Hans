---
description: 私有数据馈送是允许提供商限制买家访问其数据的选项。 数据提供商和购买者应在创建和订阅专用数据服务之前查看此信息。
seo-description: 私有数据馈送是允许提供商限制买家访问其数据的选项。 数据提供商和购买者应在创建和订阅专用数据服务之前查看此信息。
seo-title: 专用数据信息源
solution: Audience Manager
title: 专用数据信息源
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 1%

---


# 专用数据信息源 {#private-data-feeds}

私有数据馈送是允许提供商限制买家访问其数据的选项。 数据提供商和购买者应在创建和订阅专用数据服务之前查看此信息。

<!-- c_marketplace_privatefeed.xml -->

## 提供商专用数据服务 {#private-data-feeds-providers}

作为提供者，您的数据服务可以是公共的或私有的。 私人数据馈送允许您限制买家访问您的数据，包括数据销售者的姓名。 您可能希望创建专用数据源以优惠特殊交易、折扣或隐私和访问控制重要时。 通过私人数据源，您可以审核和批准买家请求。 在您批准请求后，该源看起来就像是买方的公共数据源。 您可以在中视图和管理所有源 **[!UICONTROL Audience Marketplace > My Shared Data]**。 如下所示，此类型的源在状态列中标记为“私有”。

![](assets/my_shared_data.png)

### 管理源请求

单击中的专用数据源的名 [!UICONTROL My Shared Data] 称可转到包含多个选项卡的页面。 单击选项卡以管理您的专用数据源请求。

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
   <td colname="col2"> <p>列表批准了订阅私人数据源的购买者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 潜在订阅者</span></b> </p> </td> 
   <td colname="col2"> <p>列表批准了未订阅私人数据源的购买者。 </p> <p>批准允许购买者像公开一样视图数据源。 这使他们有机会在订阅之前查看和评估您的源。 您还可以将数据馈送的折扣优惠给列为潜在订阅者的购买者。 购买者订阅后，其用户档案将移至“当前订 <b><span class="uicontrol"> 阅者”</span></b>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 访问请求</span></b> </p> </td>
   <td colname="col2"> <p>列表针对专用数据源的新订阅请求。 单击此选项卡可审核、批准或拒绝采购员请求。 </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">已批准的购买者将移至 <b><span class="uicontrol"> 潜在订阅者</span></b>。 </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">被拒绝买家将转为“已拒 <b><span class="uicontrol"> 绝访问</span></b>”。 </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 详细信息请求</span></b> </p> </td>
   <td colname="col2"> <p>列表批准了尚未订阅数据源并请求有关您的源的更多信息的购买者。 </p> <p>批准允许购买者像公开一样视图数据源。 这使他们有机会在订阅之前查看和评估您的源。 您还可以将数据馈送的折扣优惠给请求访问的买家。 响应详细信息请求会从此标签中删除采购员用户档案。 如果他们尚未订阅，则买方用户档案仍在潜在订 <b><span class="uicontrol"> 阅者中</span></b>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 拒绝访问</span></b> </p> </td> 
   <td colname="col2"> <p>列表拒绝了订阅对专用数据源的请求。 </p> <p>要重新批准已拒绝的买家，请将“拒绝 <span class="wintitle"> 状态”更改为</span> “允 <b><span class="uicontrol"> 许”</span></b>。 这会将买方转移到潜 <b><span class="uicontrol"> 在订户</span></b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 后续步骤

以下文档可以帮助您开始使用专用数据服务。

* [创建公共或专用数据源](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [审核、批准或拒绝私有源请求](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [购买者专用数据服务](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## 购买者专用数据服务 {#private-data-feeds-for-buyers}

作为购买者，私有数据馈送在Marketplace中的显 [示方式](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) 与任何其他优惠一样。 但是，在这种情况下，源列表不显示特征、唯一用户和用户重叠的摘要信息。 此外，数据销售者还可以选择在列表的列中显示或隐 [!UICONTROL Provider] 藏其姓 [!UICONTROL Marketplace] 名。 在卖家批准您的订阅请求后，您便可使用私有源中的所有数据（其工作方式与公共源类似）。 以 [!UICONTROL Marketplace] 下示例列表了作为采购员可供您使用的3种不同源类型。

![](assets/buyer_marketplace.png)

源类型包括：

下表说明了这些不同的源类型如何显示或隐藏数据。

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
   <td colname="col2"> <p>提供程序的名称、特征和唯一数据显示在列表中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 无品牌的私有</span></b> </p> </td> 
   <td colname="col2"> <p>提供者的名称设置为“私有卖家”，您看不到特征计数、唯一数据和特征重叠数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 品牌专用</span></b> </p> </td> 
   <td colname="col2"> <p>提供者的名称显示在列表中，但您看不到特征计数、唯一数据和特征重叠数据。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 后续步骤

请参阅 [订阅专用数据源](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) ，请求访问。

## 如何建立数据提供者与数据买家的共享关系 {#set-up-sharing-relationship}

### 步骤1 —— 启用——数据提供者和数据购买者

这一过程的第一步需要Adobe咨询或客户关怀部门的介入。 数据提供商和数据购买者应联系Adobe咨询或客户关怀部门以请求启用。

### 第2步——数据提供程序——创建新数据源

在您的Audience Manager帐户中，使用以下项创建新的cookie数据源：

* **Audience Manager** ID作为入站密钥；
* 选中 **了“启用** 共享”选项。

![](assets/create-datasource.png)

单击“保 **存**”后，将在“特征存储”>“第 **三方数据”中自动创建新子文件夹**。

![](assets/folder-structure.png)

### 第3步——数据提供者——标识共享的特征

在此步骤中，您确定要与合作伙伴共享的特征。 您可以创建新特征或编辑现有特征。 无论如何，您都需要以下特征：

* 与您作为步骤2的一部分创建的数据源关联。
* 要存储在新创建的子文件夹中，位于第三方数据下。

阅读有关创建 [特征和编](/help/using/features/traits/create-onboarded-rule-based-traits.md) 辑 [特征的更多信息](/help/using/features/traits/manage-trait-rules.md#edit-trait)。

### 第4步——数据提供程序——创建数据馈送

接下来，创建一个数据源，与数据购买者共享您的特征。 有关如何 [创建数据馈送的说明](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) ，请参阅创建公共或专用数据馈送。

>[!IMPORTANT]
>
>在设置中，选择专用选项。 如果将此字段设置为“公共”，则任何Audience Marketplace客户都可订阅您的源。

![](assets/create-data-feed.png)

### 第5步——数据采购员——请求访问

转到 **Audience Marketplace> Marketplace**。 搜索上一步中由数据提供程序创建的数据馈送。 单击 **请求访问**。 数据提供方指定的联系人现在将收到电子邮件通知。 另请参 [阅订阅专用数据源](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

### 第6步——数据提供程序——授予访问权限

转到“ **Audience Marketplace”>“我的共享** ”，然后搜索您在步骤4中创建的源。 单击进入新的访问请求，然后单 **击“允许访问** ”以批准该请求。 另请参阅审 [核、批准或拒绝私有源请求](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)。

### 第7步——数据购买者——开启订阅

在数据提供者授予对数据源的访问权后，您可以在Audience Marketplace>市场中查看您帐户 **中的源**。 查看详细信息，打开“订阅”按钮，然后单击“审 **阅并订阅”**。 有 [关在何处查找第](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) 3方特征的信息，请参阅订阅存储。

请注意，这些特征只能在数据提供者的帐户中进行编辑。




