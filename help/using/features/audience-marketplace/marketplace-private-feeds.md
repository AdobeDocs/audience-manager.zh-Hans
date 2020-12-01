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

## 提供者的专用数据服务{#private-data-feeds-providers}

作为提供者，您的数据服务可以是公共的或私有的。 私人数据馈送允许您限制买家访问您的数据，包括数据销售者的姓名。 您可能希望创建专用数据源以优惠特殊交易、折扣或隐私和访问控制重要时。 通过私人数据源，您可以审核和批准买家请求。 在您批准请求后，该源看起来就像是向买方提供的公共数据源。 您可以在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data]**&#x200B;中视图和管理所有源。 如下所示，此类型的源在状态列中标记为“私有”。

![](assets/my_shared_data.png)

### 管理源请求

单击[!UICONTROL My Shared Data]中专用数据源的名称会转到包含多个选项卡的页面。 单击选项卡以管理您的专用数据源请求。

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
   <td colname="col2"> <p>列表批准了未订阅私人数据源的购买者。 </p> <p>批准允许购买者像公开一样视图数据源。 这使他们有机会在订阅之前查看和评估您的源。 您还可以将数据馈送的折扣优惠给列为潜在订阅者的购买者。 购买者订阅后，其用户档案将移至<b><span class="uicontrol">当前订阅者</span></b>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 访问请求</span></b> </p> </td>
   <td colname="col2"> <p>列表针对专用数据源的新订阅请求。 单击此选项卡可审核、批准或拒绝采购员请求。 </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">已批准的购买者将移至<b><span class="uicontrol">潜在订阅者</span></b>。 </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">被拒绝买家将移至<b><span class="uicontrol">已拒绝访问</span></b>。 </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 详细信息请求</span></b> </p> </td>
   <td colname="col2"> <p>列表批准了尚未订阅数据源并请求有关您的源的更多信息的购买者。 </p> <p>批准允许购买者像公开一样视图数据源。 这使他们有机会在订阅之前查看和评估您的源。 您还可以将数据馈送的折扣优惠给请求访问的买家。 响应详细信息请求会从此标签中删除采购员用户档案。 如果买家用户档案尚未订阅，则买家订阅仍位于<b><span class="uicontrol">潜在订阅者</span></b>中。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 拒绝访问</span></b> </p> </td> 
   <td colname="col2"> <p>列表拒绝了订阅对专用数据源的请求。 </p> <p>要重新批准已拒绝的购买者，请将<span class="wintitle">拒绝状态</span>更改为<b><span class="uicontrol">允许</span></b>。 这会将买方移至<b><span class="uicontrol">潜在订户</span></b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 后续步骤

以下文档可以帮助您开始使用专用数据服务。

* [创建公共或专用数据源](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [审核、批准或拒绝私有源请求](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [购买者专用数据服务](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## 购买者专用数据源{#private-data-feeds-for-buyers}

作为买方，专用数据源与任何其他优惠一样显示在[Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)中。 但是，在这种情况下，源列表不显示特征、唯一用户和用户重叠的摘要信息。 此外，数据销售者还可以选择在[!UICONTROL Marketplace]列表的[!UICONTROL Provider]列中显示或隐藏其名称。 在卖家批准您的订阅请求后，您便可使用私有源中的所有数据（其工作方式与公共源类似）。 下面的[!UICONTROL Marketplace]示例列表了作为采购员可用的3种不同源类型。

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

请参阅  [订阅专用数据](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 反馈以请求访问。

## 如何设置数据提供者与数据购买者之间的共享关系{#set-up-sharing-relationship}

### 步骤1 —— 启用——数据提供者和数据购买者

这一过程的第一步需要Adobe咨询或客户关怀部门的介入。 Adobe提供商和数据购买者应联系客户咨询或客户服务部门以请求启用。

### 第2步——数据提供程序——创建新数据源

在您的Audience Manager帐户中，使用以下项创建新的cookie数据源：

* **Audience Manager** ID作为入站密钥；
* 选中&#x200B;**已启用共享**&#x200B;选项。

![](assets/create-datasource.png)

单击&#x200B;**保存**&#x200B;后，将在&#x200B;**特征存储>第三方数据**&#x200B;中自动创建新子文件夹。

![](assets/folder-structure.png)

### 第3步——数据提供者——标识共享的特征

在此步骤中，您确定要与合作伙伴共享的特征。 您可以创建新特征或编辑现有特征。 无论如何，您都需要以下特征：

* 与您作为步骤2的一部分创建的数据源关联。
* 要存储在新创建的子文件夹中，位于第三方数据下。

阅读有关创建traits[和](/help/using/features/traits/create-onboarded-rule-based-traits.md)编辑traits[的更多信息。](/help/using/features/traits/manage-trait-rules.md#edit-trait)

### 第4步——数据提供程序——创建数据馈送

接下来，创建一个数据源，与数据购买者共享您的特征。 有关如何创建数据源的说明，请参阅[创建公共或专用数据源](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md)。

>[!IMPORTANT]
>
>在设置中，选择专用选项。 如果将此字段设置为“公共”，则任何Audience Marketplace客户都可订阅您的源。

![](assets/create-data-feed.png)

### 第5步——数据采购员——请求访问

转到&#x200B;**Audience Marketplace> Marketplace**。 搜索上一步中由数据提供程序创建的数据馈送。 单击&#x200B;**请求访问**。 数据提供方指定的联系人现在将收到电子邮件通知。 另请参阅[订阅专用数据源](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

### 第6步——数据提供程序——授予访问权限

转到&#x200B;**Audience Marketplace>我的共享数据**&#x200B;并搜索您在步骤4中创建的源。 单击进入新的访问请求，然后单击&#x200B;**允许访问**&#x200B;以批准该请求。 另请参阅[审核、批准或拒绝专用源请求](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)。

### 第7步——数据购买者——开启订阅

在数据提供者授予对数据源的访问权后，您可以在&#x200B;**Audience Marketplace> Marketplace**&#x200B;中查看帐户中的数据源。 查看详细信息，打开“订阅”按钮，然后单击&#x200B;**“查看并订阅”**。 有关在何处查找第三方特征的信息，请参阅[订阅存储源](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee)。

请注意，这些特征只能在数据提供者的帐户中进行编辑。




