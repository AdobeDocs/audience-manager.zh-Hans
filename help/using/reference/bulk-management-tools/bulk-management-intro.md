---
description: 批量管理工具允许您通过单一操作同时创建和管理多个对象。您可以使用批量管理工具处理数据源、派生信号、目标、文件夹、细分和特征。
keywords: Baaam；巴哈马群岛
seo-description: 批量管理工具允许您通过单一操作同时创建和管理多个对象。您可以使用批量管理工具处理数据源、派生信号、目标、文件夹、细分和特征。
seo-title: 批量管理入门
solution: Audience Manager
title: 批量管理入门
uuid: 4bc6ae0a-315c-4ce7-a68 e-cc0 c6 c6 aa2 f1
translation-type: tm+mt
source-git-commit: 215054718e9248bd44ba99baeb2a10236701d98e

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

批量管理工具允许您通过单一操作同时创建和管理多个对象。您可以使用批量管理工具处理数据源、派生信号、目标、文件夹、细分和特征。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

## 概述 {#overview}

This feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs. API提供可批量更改的方法和服务。您无需知道如何编写代码或使用API来使用它。工作表包含执行特定批量更改功能的列标题和选项卡。要进行批量更改，只需将预定义的标题添加到特定工作表，提供要批量更改的信息，然后单击操作按钮。工作表和API为您完成其余工作。

## 下载 {#download}

Download the latest worksheet **[here](assets/BAAAM_August_2018.xlsm)**.

## 先决条件 {#prereqs}

To use the [!DNL Bulk Management Tools], you need the following:

* Your [!DNL Audience Manager] user name and password. 作为客户，您应该已经拥有这些凭据。
* API客户端ID和密钥。您的客户经理可以为您提供这些内容。
* [!UICONTROL Bulk Management Tools] 工作表。[下载工作表](/help/using/reference/bulk-management-tools/bulk-management-intro.md#download) 以获取最新版本。

* Microsoft Excel running on [!DNL Windows] or in a [!DNL Microsoft Windows] virtual machine running on [!DNL macOS X]. You must use 32-bit Excel for the [!UICONTROL Bulk Management Tools] to work.

## Actions and operations {#actions-ops}

[!UICONTROL Bulk Management Tools] 工作表包含操作选项卡、操作按钮和 **[!UICONTROL Headers]** 选项卡。**[!UICONTROL Headers]** 选项卡包含操作选项卡使用的预格式化列标题。操作选项卡包含执行选定批量操作的宏。要执行批量操作，请将一组标题复制到相应的操作选项卡中，输入标题数据，然后单击操作按钮。

打开电子表格并单击操作按钮以开始。

![](assets/bamwrkbk.png)

The table below lists the operations you can perform and items you can manipulate with the [!UICONTROL Bulk Management Tools] worksheets.

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
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">估值 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">删除 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>The objects you can change in bulk are located under the <b><span class="uicontrol"> Headers</span></b> tab and include: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 数据源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 派生信号</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 目标</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特征文件夹</a> 和区段文件夹 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 区段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特征</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**批量操作示例**

作为示例，我们来看一下如何一次创建多个特征。要在批量操作中创建多个特征，您需要：

1. Click the **[!UICONTROL Headers]** tab and copy all the labels under the [!UICONTROL Create a Trait] option.

2. Click the **[!UICONTROL Create]** tab and paste the labels starting in row 1, column A.
3. Provide information related to each column header and click **[!UICONTROL Create Traits]**. 此操作提示您登录。Your bulk job runs after you successfully authenticate (see the [authentication requirements](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) below). 检查工作表左下角以获取作业状态通知。

>[!NOTE]
>
>处理大请求时，工作表可能会变得无响应，并且似乎不活动。在这些情况下，只需保留它。批量请求完成后，工作表将变为响应式。If the worksheet does not respond for a long period of time, see the [troubleshooting section](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentication requirements and options {#auth-reqs}

批量更改需要身份验证。当您选择某个操作时，工作表会提示您登录。由于工作表进行了API调用，因此您需要对其进行配置以读取密钥。And, the **[!UICONTROL Domain]** field lets you make bulk changes in a staging/test environment or against your live, production account.

![](assets/bamauth.png)

**API身份验证要求**

要设置API身份验证，您必须：

* 复制机密密钥并将其保存到文本(.txt)文件。
* 使用您的API客户端ID命名文本文件。例如，如果客户端ID为“Bulk-User”，则将密钥保存在标题为“Bulk-User. txt”的文件中。
* 将密钥和工作表一起保存到同一文件夹中。

进行批量更改时，您仍必须输入用户名、口令、客户端ID和域，但API身份验证是自动完成的。

**域身份验证选项**

域身份验证可让您选择测试批量请求，或将其直接应用于生产帐户。对测试环境进行批量更改不会影响生产帐户。制作更改立即生效。**[!UICONTROL Domain]** 该字段接受以下地址，具体取决于您要处理的环境：

* 测试: `api-beta.demdex.com`
* 生产: `api.demdex.com`

>[!MORE_ LIKE_ This]
>
>* [下载批量管理工作表](assets/BAAAM_August_2018.xlsm)

