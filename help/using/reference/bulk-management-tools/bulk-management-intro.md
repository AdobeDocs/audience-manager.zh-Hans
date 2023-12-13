---
description: 批量管理工具允许您通过一次操作同时创建和管理多个对象。 您可以使用批量管理工具处理数据源、派生的信号、目标、文件夹、区段和特征。
keywords: baaam；BAAAM；下载baaam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: 开始使用批量管理工具
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: e8d81f648f5a46495193fe6631c8a7f73e290493
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---


# 开始使用批量管理工具{#getting-started-with-bulk-management}

此 [!DNL Bulk Management Tools] 允许您通过一次操作同时创建和管理多个对象。 您可以使用 [!DNL Bulk Management Tools] 使用 [!UICONTROL data sources]， [!UICONTROL derived signals]， [!UICONTROL destinations]， [!UICONTROL folders]， [!UICONTROL models]， [!UICONTROL segments]、和 [!UICONTROL traits].

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[RBAC组权限](../../features/administration/administration-overview.md) 分配于 [!DNL Audience Manager] 用户界面在 [!UICONTROL Bulk Management Tools].

## 概述 {#overview}

此功能使用 [!DNL Microsoft Excel] 带有宏的电子表格，这些宏可对 [!DNL Audience Manager] API。 API提供了一些方法和服务，允许您批量进行更改。 您不必知道如何编写代码或使用我们的API即可使用它。 此工作表包含执行特定批量更改功能的列标题和标签。 要进行批量更改，只需将预定义标题添加到特定工作表，提供要批量更改的信息，然后单击操作按钮即可。 工作表和API为您完成其余工作。

## 下载 {#download}

下载最新的工作表 **[此处](assets/BAAAM_V2_20210609.xlsm)** （上次更新于2021年6月）。

## 先决条件 {#prereqs}

要使用 [!DNL Bulk Management Tools]，您需要以下各项：

* 您的 [!DNL Experience Cloud] 登录。 作为客户，您应该已经拥有这些凭据。
* 此 [!DNL Bulk Management Tools] 工作表。 [下载工作表](assets/BAAAM_V2_20210609.xlsm) 以获取最新版本。
* [!DNL Microsoft Excel] 运行于 [!DNL macOS] 或64位 [!DNL Microsoft Windows]. 我们建议您使用最新版本的 [!DNL Microsoft Excel].
* 打开工作表时，您必须 **启用宏** 对于 [!DNL Bulk Management Tools] 去工作。

## 身份验证要求和选项 {#auth-reqs}

批量更改需要身份验证。 执行任何操作前，您必须登录。 由于工作表会发起API调用，因此您需要将其配置为在您的用户帐户中进行身份验证。

**API身份验证要求**

的第二个版本 [!DNL Bulk Management Tools]2019年10月发布的SSF简化了身份验证过程。 此版本中的身份验证步骤概述如下：

1. 打开电子表格并导航到 **[!UICONTROL Config]** 工作表。
2. 按照工作表中列出的步骤操作。
   ![](assets/baaam-authentication.png)
3. 完成这些步骤后，您有权进行批量更改。

在进行批量更改时，您仍必须确认您有权进行更改，但API身份验证是自动进行的。

**域身份验证选项**

域身份验证使您可以选择测试批量请求，或将其直接应用于您的生产帐户。 对测试版环境进行批量更改不会影响您的生产帐户。 生产更改会立即生效。 批量管理工作表允许您在以下环境中工作：

* 测试版
* 生产

## 操作和操作 {#actions-ops}

此 [!UICONTROL Bulk Management Tools] 工作表由验证按钮、“活动”标签、“活动”按钮和 **[!UICONTROL Headers]** 选项卡。 此 **[!UICONTROL Headers]** 选项卡包含操作选项卡使用的预格式化的列标题。 操作选项卡包含执行所选批量操作的宏。 要执行批量操作，请将一组标题复制到相应的操作选项卡中，输入标题数据，然后单击操作按钮。

之后 [身份验证](#auth-reqs)，单击操作按钮即可开始。

![](assets/baaam-worksheet.png)

下表列出了您可以执行的操作以及可以使用 [!UICONTROL Bulk Management Tools] 工作表。

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 操作 </th> 
   <th colname="col2" class="entry"> 对象 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>批量操作显示在工作表底部的选项卡中，包括： </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">请求 </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">更新 </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">创建 </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">预估 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">删除 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>您可以批量更改的对象位于 <b><span class="uicontrol"> 标题</span></b> 选项卡并包括： </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 数据源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 派生的信号</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 目标</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 模型</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特征文件夹</a> 和区段文件夹 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 区段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特征</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**批量操作示例**

例如，我们来看看如何同时创建多个特征。 要在批量操作中创建多个特征，您需要：

1. 单击 **[!UICONTROL Headers]** 制表符并复制 [!UICONTROL Create a Trait] 选项。
2. 单击 **[!UICONTROL Create]** 制表符并粘贴从行1列A开始的标签。
3. 提供与每个列标题相关的信息，然后单击 **[!UICONTROL Create Traits]**. 此操作提示您确认身份验证。 确认身份验证后，批量作业将运行。 检查工作表的左下角以获取作业状态通知。


>[!NOTE]
>
>处理大型请求时，工作表可能会变得无响应，并且似乎处于不活动状态。 在这些情况下，不要管它。 批量请求完成后，工作表将变得响应。 如果工作表长时间没有响应，请参阅 [疑难解答部分](../../reference/bulk-management-tools/bulk-troubleshooting.md).
