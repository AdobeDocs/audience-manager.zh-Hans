---
description: 使用批量管理工具，您可以一次创建和管理多个对象。 您可以使用批量管理工具处理数据源、派生的信号、目标、文件夹、区段和特征。
keywords: baaam;BAAAM；下载baaam
seo-description: 使用批量管理工具，您可以一次创建和管理多个对象。 您可以使用批量管理工具处理数据源、派生的信号、目标、文件夹、区段和特征。
seo-title: 开始使用批量管理工具
solution: Audience Manager
title: 开始使用批量管理工具
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 911eab2d661907c6f1e2ffc08603d994bd346395
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 4%

---

# 开始使用批量管理工具{#getting-started-with-bulk-management}

[!DNL Bulk Management Tools]允许您一次创建和管理多个对象，只需一次操作。 您可以使用[!DNL Bulk Management Tools]与[!UICONTROL data sources]、[!UICONTROL derived signals]、[!UICONTROL destinations]、[!UICONTROL folders]、[!UICONTROL models]、[!UICONTROL segments]和[!UICONTROL traits]一起使用。

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[用户界](../../features/administration/administration-overview.md) 面中分配的RBAC [!DNL Audience Manager] 组权限将在中执 [!UICONTROL Bulk Management Tools]行。

## 概述 {#overview}

此功能使用带有宏的[!DNL Microsoft Excel]电子表格，这些宏可对[!DNL Audience Manager] API进行经过验证的安全调用。 API提供了可让您批量进行更改的方法和服务。 您不必知道如何编码或使用我们的API来使用它。 工作表包含执行特定批量更改功能的列标题和选项卡。 要进行批量更改，您只需将预定义的标题添加到特定工作表，提供要批量更改的信息，然后单击操作按钮即可。 工作表和API将为您完成其余的工作。

## 下载 {#download}

下载最新的工作表&#x200B;**[此处](assets/BAAAM_V2_20210609.xlsm)**（上次更新日期：2021年6月）。

## 先决条件 {#prereqs}

要使用[!DNL Bulk Management Tools]，您需要满足以下条件：

* 您的[!DNL Experience Cloud]登录。 作为客户，您应该已经拥有这些凭据。
* [!DNL Bulk Management Tools]工作表。 [下载工](assets/BAAAM_V2_20200502.xlsm) 作表获取最新版本。
* [!DNL Microsoft Excel] 运行 [!DNL macOS] 于或64位 [!DNL Microsoft Windows]。我们建议您使用最新版本的[!DNL Microsoft Excel]。
* 打开工作表时，必须&#x200B;**启用宏**&#x200B;才能使[!DNL Bulk Management Tools]正常工作。

## 身份验证要求和选项{#auth-reqs}

批量更改需要进行身份验证。 执行任何操作之前，必须登录。 由于工作表会发起API调用，因此您需要对其进行配置以在您的用户帐户中进行身份验证。

**API身份验证要求**

2019年10月发布的[!DNL Bulk Management Tools]的第二版简化了身份验证过程。 此版本中的身份验证步骤如下所示：

1. 打开电子表格，然后导航到&#x200B;**[!UICONTROL Config]**&#x200B;工作表。
2. 按照工作表中所述的步骤操作。
   ![](assets/baaam-authentication.png)
3. 完成这些步骤后，您将有权进行批量更改。

进行批量更改时，您仍必须确认您有权进行更改，但API身份验证是自动的。

**域身份验证选项**

域身份验证允许您选择测试批量请求，或直接将批量请求应用到您的生产帐户。 对测试版环境进行批量更改不会影响您的生产帐户。 生产更改会立即生效。 批量管理工作表允许您在以下环境中工作：

* Beta
* 生产

## 操作和操作{#actions-ops}

[!UICONTROL Bulk Management Tools]工作表包含身份验证按钮、操作选项卡、操作按钮和&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡。 **[!UICONTROL Headers]**&#x200B;选项卡包含操作选项卡使用的预格式化列标题。 操作选项卡包含执行所选批量操作的宏。 要执行批量操作，请将一组标头复制到相应的操作选项卡中，输入标头数据，然后单击操作按钮。

在[authenticatie](#auth-reqs)之后，单击操作按钮以开始操作。

![](assets/baaam-worksheet.png)

下表列出了可执行的操作以及可通过[!UICONTROL Bulk Management Tools]工作表处理的项目。

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
   <td colname="col2"> <p>您可以批量更改的对象位于<b><span class="uicontrol">标题</span></b>选项卡下，并且包括： </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 数据源</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> 派生的信号</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> 目标</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> 模型</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> 特征文</a> 件夹和区段文件夹 </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> 区段</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> 特征</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**批量操作示例**

例如，让我们看一看如何一次创建多个特征。 要在批量操作中创建多个特征，您需要：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡，并复制[!UICONTROL Create a Trait]选项下的所有标签。
2. 单击&#x200B;**[!UICONTROL Create]**&#x200B;选项卡，并粘贴从行1，列A开始的标签。
3. 提供与每个列标题相关的信息，然后单击&#x200B;**[!UICONTROL Create Traits]**。 此操作将提示您确认身份验证。 确认身份验证后，将运行批量作业。 检查工作表左下角的作业状态通知。


>[!NOTE]
>
>使用大请求时，工作表可能会变得无响应且似乎不活动。 在这些情况下，就别管它。 批量请求完成后，工作表将变为响应。 如果工作表长时间没有响应，请参阅[疑难解答部分](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
