---
description: 私有数据馈送是一个选项，它允许提供商限制购买者对其数据的访问。 数据提供商和购买者应在创建和订阅私有数据馈送之前查看此信息。
seo-description: A private data feed is an option that lets providers limit buyer access to their data. Data providers and buyers should review this information before creating and subscribing to private data feeds.
seo-title: Private Data Feeds
solution: Audience Manager
title: 专用数据信息源
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
exl-id: 34eb6194-c57b-4836-a6df-6889a2cec703
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 1%

---

# 专用数据信息源 {#private-data-feeds}

私有数据馈送是一个选项，它允许提供商限制购买者对其数据的访问。 数据提供商和购买者应在创建和订阅私有数据馈送之前查看此信息。

<!-- c_marketplace_privatefeed.xml -->

## 提供商的私有数据馈送 {#private-data-feeds-providers}

作为提供商，您的数据馈送可以是公共的或私有的。 通过私有数据馈送，您可以限制买方访问您的数据，包括数据卖方的名称。 您可能希望创建私有数据馈送以提供特殊优惠、折扣，或者在隐私和访问控制很重要时。 通过专用数据馈送，您可以审核和批准买方请求。 批准请求后，馈送看起来就像给购买者的公共数据馈送。 您可以在&#x200B;**[!UICONTROL Audience Marketplace > My Shared Data]**&#x200B;中查看和管理您的所有馈送。 如下所示，此类信息源在状态列中标记为“私有”。

![](assets/my_shared_data.png)

### 管理信息源请求

单击来自[!UICONTROL My Shared Data]的私有数据馈送的名称将会转到包含多个选项卡的页面。 单击选项卡以管理您的私有数据馈送请求。

![](assets/shared_data_tabs.png)

下表定义了每个操作选项卡提供的一个或多个角色。

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 制表符 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">当前订阅者</span></b> </p> </td> 
   <td colname="col2"> <p>列出已订阅私人数据馈送的已批准购买者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">个潜在的订阅者</span></b> </p> </td> 
   <td colname="col2"> <p>列出尚未订阅私人数据馈送的已批准购买者。 </p> <p>批准后，购买者即可像查看公共数据馈送一样查看它。 这为他们提供了一个在订阅之前查看和评估您的馈送的机会。 您还可以向列为潜在订阅者的购买者提供数据馈送折扣。 购买者订阅后，其配置文件将移动到<b><span class="uicontrol">当前订阅者</span></b>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">访问请求</span></b> </p> </td>
   <td colname="col2"> <p>列出私有数据馈送的新订阅请求。 单击此标签以复查、批准或拒绝采购员请求。 </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">已批准的购买者将移动到<b><span class="uicontrol">个潜在的订阅者</span></b>。 </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">被拒绝的购买者移至<b><span class="uicontrol">拒绝访问</span></b>。 </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">个详细信息请求</span></b> </p> </td>
   <td colname="col2"> <p>列出尚未订阅数据馈送并已请求了解有关您的馈送的更多信息的已批准购买者。 </p> <p>批准后，购买者即可像查看公共数据馈送一样查看它。 这为他们提供了一个在订阅之前查看和评估您的馈送的机会。 您还可以向请求访问的买方提供数据馈送折扣。 响应详细信息请求会从此标签中删除采购员配置文件。 如果他们尚未订阅，则购买者配置文件仍在<b><span class="uicontrol">潜在订阅者</span></b>中。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">拒绝访问</span></b> </p> </td> 
   <td colname="col2"> <p>列出私人数据馈送的已拒绝订阅请求。 </p> <p>要重新批准被拒绝的购买者，请将<span class="wintitle">拒绝状态</span>更改为<b><span class="uicontrol">允许</span></b>。 这会将购买者移动到<b><span class="uicontrol">个潜在的订阅者</span></b>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 后续步骤

以下文档可帮助您开始使用私有数据馈送。

* [创建公共或私有数据馈送](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [审核、批准或拒绝专用信息源请求](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [面向购买者的专用数据馈送](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## 面向购买者的专用数据馈送 {#private-data-feeds-for-buyers}

作为购买者，私有数据馈送会像任何其他选件一样出现在[Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)中。 但是，在这种情况下，信息源列表不会显示特征、独特用户和用户重叠的摘要信息。 此外，数据销售商可以选择在[!UICONTROL Provider]列表的[!UICONTROL Marketplace]列中显示或隐藏其名称。 在销售商批准您的订阅请求后，您即可使用私有馈送中的所有数据（其工作方式与公共馈送类似）。 下面的[!UICONTROL Marketplace]示例列出了可作为购买者使用的3种不同的信息源类型。

![](assets/buyer_marketplace.png)

信息源类型包括：

该表介绍了这些不同的馈送类型如何显示或隐藏数据。

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 信息源类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">公共</span></b> </p> </td> 
   <td colname="col2"> <p>提供商的名称、特征和唯一数据会显示在列表中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">私有，没有品牌</span></b> </p> </td> 
   <td colname="col2"> <p>提供商的名称被设置为“私人销售商”，您将看不到特征计数、唯一数据和特征重叠数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol">私有品牌</span></b> </p> </td> 
   <td colname="col2"> <p>提供商的名称会显示在列表中，但您看不到特征计数、唯一数据和特征重叠数据。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 后续步骤

请参阅[订阅私有数据馈送](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)以请求访问权限。

## 如何建立数据提供者和数据购买者之间的共享关系 {#set-up-sharing-relationship}

### 步骤1 — 启用 — 数据提供程序和数据购买者

此流程的第一步需要Adobe Consulting或客户关怀团队的干预。 数据提供商和数据购买者应联系Adobe Consulting或客户关怀团队以请求启用。

### 步骤2 — 数据提供程序 — 新建数据Source

在您的Audience Manager帐户中，使用以下内容创建新的Cookie数据源：

* **Audience Manager ID**&#x200B;作为入站密钥；
* **共享已启用**&#x200B;选项已选中。

![](assets/create-datasource.png)

单击&#x200B;**保存**&#x200B;后，将在&#x200B;**特征存储>第三方数据**&#x200B;中自动创建新的子文件夹。

![](assets/folder-structure.png)

### 步骤3 — 数据提供程序 — 识别要共享的特征

在此步骤中，您将确定要与合作伙伴共享的特征。 您可以创建新特征或编辑现有特征。 无论如何，您需要以下特征：

* ，以与您在步骤2中创建的数据源关联。
* 要存储在新创建的子文件夹中的第三方数据下。

阅读有关[创建特征](/help/using/features/traits/create-onboarded-rule-based-traits.md)和[编辑特征](/help/using/features/traits/manage-trait-rules.md#edit-trait)的更多信息。

### 步骤4 — 数据提供程序 — 创建数据馈送

接下来，创建一个数据馈送以将您的特征与数据购买者共享。 有关如何创建数据馈送的说明，请参阅[创建公共或私有数据馈送](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md)。

>[!IMPORTANT]
>
>在设置中，选择专用选项。 如果您将此字段设置为“公共”，则任何Audience Marketplace客户都可以订阅您的信息源。

![](assets/create-data-feed.png)

### 步骤5 — 数据购买者 — 请求访问

转到&#x200B;**Audience Marketplace >市场**。 搜索在上一步中由数据提供程序创建的数据馈送。 单击&#x200B;**请求访问**。 数据提供商方的指定联系人现在将收到电子邮件通知。 另请参阅[订阅私有数据馈送](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed)。

### 步骤6 — 数据提供程序 — 授予访问权限

转到&#x200B;**Audience Marketplace >我的共享数据**，然后搜索您在步骤4中创建的信息源。 单击进入新的访问请求，然后单击&#x200B;**允许访问**&#x200B;以批准该请求。 另请参阅[审核、批准或拒绝专用信息源请求](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)。

### 步骤7 — 数据购买者 — 启用订阅

数据提供商授予数据馈送的访问权限后，您可在&#x200B;**Audience Marketplace > Marketplace**&#x200B;中查看帐户中的馈送。 查看详细信息，打开订阅按钮，然后单击&#x200B;**查看和订阅**。 有关在何处查找第三方特征的信息，请参阅[订阅的数据馈送的存储空间](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee)。

请注意，这些特征只能在数据提供商的帐户中进行编辑。
