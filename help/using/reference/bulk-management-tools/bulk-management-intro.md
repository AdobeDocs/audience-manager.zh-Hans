---
description: 使用批量管理工具，您可以通过单个操作同时创建和管理多个对象。 您可以使用批量管理工具处理数据源、派生信号、目标、文件夹、区段和特征。
keywords: baam;BAAAM
seo-description: 使用批量管理工具，您可以通过单个操作同时创建和管理多个对象。 您可以使用批量管理工具处理数据源、派生信号、目标、文件夹、区段和特征。
seo-title: 批量管理快速入门
solution: Audience Manager
title: 批量管理快速入门
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
translation-type: tm+mt
source-git-commit: be988def0e9cb5cb6b4a926754dd24f9fd1f85fe

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

使用批量管理工具，您可以通过单个操作同时创建和管理多个对象。 您可以使用批量管理工具处理数据源、派生信号、目标、文件夹、模型、区段和特征。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支持 *。*[!DNL Audience Manager]此工具仅出于方便和礼貌而提供。 对于批量更改，我们建议您改用 [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) 。 [在UI中分配的](../../features/administration/administration-overview.md) RBAC组权限 [!DNL Audience Manager] 在UI中被接受 [!UICONTROL Bulk Management Tools]。

## 概述 {#overview}

此功能使用带有宏的Microsoft excel电子表格，这些宏对API进行安全、经过身份验证的 [!DNL Audience Manager] 调用。 API提供了允许您批量更改的方法和服务。 您不必知道如何编写代码或使用我们的API来使用它。 工作表包含执行特定批量更改功能的列标题和选项卡。 要进行批量更改，您只需将预定义的标题添加到特定工作表，提供要批量更改的信息，然后单击操作按钮。 工作表和API将帮您完成其余的工作。

## 下载 {#download}

在此处下载最新的 **[工作表](assets/BAAAM_V2_20191015.xlsm)**。

## 先决条件 {#prereqs}

要使用 [!DNL Bulk Management Tools]，您需要：

* 您的 [!DNL Experience Cloud] 登录名。 作为客户，您应该已经拥有这些凭据。
* 工作 [!DNL Bulk Management Tools] 表。 [下载工作表](/help/using/reference/bulk-management-tools/bulk-management-intro.md#download) ，获取最新版本。
* 运行于或64 [!DNL macOS] 位上的Microsoft Excel [!DNL Microsoft Windows]。
* 打开工作表时，必须 **启用宏** ，才 [!DNL Bulk Management Tools] 能使用。

## 身份验证要求和选项 {#auth-reqs}

批量更改需要身份验证。 在执行任何操作之前，您必须登录。 由于工作表发出API调用，您需要配置它以验证您的用户帐户。

**API身份验证要求**

2019年10月发布的第二版批量管理工具简化了身份验证过程。 此版本中的身份验证步骤概述如下：

1. 打开电子表格并导航到 **Config** 表。
2. 按照工作表中概述的步骤操作。
   ![](assets/baaam-authentication.png)
3. 完成这些步骤后，您将获得批量更改的授权。

进行批量更改时，您仍须确认已获得进行更改的授权，但API身份验证是自动的。

**域身份验证选项**

域身份验证允许您测试批量请求或将它们直接应用到您的生产帐户。 对测试版环境进行批量更改不会影响您的生产帐户。 生产更改会立即生效。 批量管理工作表允许您在以下环境中工作：

* Beta
* 生产

## 操作和操作 {#actions-ops}

工作 [!UICONTROL Bulk Management Tools] 表由身份验证按钮、操作选项卡、操作按钮和选项卡组 **[!UICONTROL Headers]** 成。 该选 **[!UICONTROL Headers]** 项卡包含操作选项卡使用的预格式化列标题。 操作选项卡包含执行所选批量操作的宏。 要执行批量操作，请将一组标题复制到相应的操作选项卡中，输入标题数据，然后单击操作按钮。

验 [证后](#auth-reqs)，单击操作按钮开始。

![](assets/baaam-worksheet.png)

下表列出了您可以执行的操作以及可以使用工作表处理的 [!UICONTROL Bulk Management Tools] 项目。

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
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">估计 </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">删除 </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>您可以批量更改的对象位于“标题”选 <b><span class="uicontrol"> 项卡下</span></b> ，包括： </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 数据源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 派生信号</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 目标</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 型号</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特征文件夹</a> 和区段文件夹 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 区段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特征</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**批量操作示例**

例如，我们来看一下如何同时创建多个特征。 要在批量操作中创建多个特征，您需要：

1. 单击选 **[!UICONTROL Headers]** 项卡并复制选项下的所有 [!UICONTROL Create a Trait] 标签。
2. 单击选 **[!UICONTROL Create]** 项卡并粘贴从第1行A列开始的标签。
3. 提供与每个列标题相关的信息，然后单击 **[!UICONTROL Create Traits]**。 此操作会提示您确认身份验证。 确认身份验证后，将运行批量作业。 检查工作表的左下角以获得任务状态通知。


>[!NOTE]
>
>处理大请求时，工作表可能会变得无响应，并显示为非活动状态。 在这些情况下，别管它。 完成批量请求后，工作表将变为响应式工作表。 如果工作表长时间没有响应，请参阅疑难解答 [部分](../../reference/bulk-management-tools/bulk-troubleshooting.md)。



>[!MORE_LIKE_THIS]
>
>* [下载批量管理工作表](assets/BAAAM_August_2018.xlsm)

