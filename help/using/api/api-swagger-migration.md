---
description: 在Audience Manager，我们是工程师、开发人员和代码忍者，就像您一样。 与您一样，我们希望使用可靠、准确的API文档。 因此，我们将在Swagger中重写API内容并将其移至新位置。 这些更改旨在帮助您改进使用Audience Manager API代码的体验。
seo-description: 在Audience Manager，我们是工程师、开发人员和代码忍者，就像您一样。 与您一样，我们希望使用可靠、准确的API文档。 因此，我们将在Swagger中重写API内容并将其移至新位置。 这些更改旨在帮助您改进使用Audience Manager API代码的体验。
seo-title: Audience Manager API代码迁移
solution: Audience Manager
title: Audience Manager API代码迁移
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

在Audience Manager，我们是工程师、开发人员和代码忍者，就像您一样。 与您一样，我们希望使用可靠、准确的文 [!DNL API] 档。 因此，我们将内容重新写入并 [!DNL API] 将其移 [!DNL Swagger] 至新位置。 这些更改旨在帮助您改进使用Audience Manager代码的 [!DNL API] 体验。

## Movin' On Up {#code-migration-details}

<!-- api-swagger-migration.xml -->

Adobe [Audience Manager API文档站点](https://bank.demdex.com/portal/swagger/index.html) ，是我们修订内容的新 [!DNL API] 主页。 我们将尝试在每个版本中重写和移动几 [!DNL API] 组方法。 这意味着您必须同时登记新位置和 [REST API文档](../api/rest-api-main/rest-api-main.md) ，才能找到所有可用的方法。 最终，所有公众 [!DNL API]都将在文档 [!DNL Audience Manager][!DNL API] 站点上。 下表列出了修订的和迁移的 [!DNL API]文件。

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API 类型 </th> 
   <th colname="col2" class="entry"> API方法 </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>算法模型</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> 算法模型</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>受众市场</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> 数据馈送</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> 数据馈送请求</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Data Feed Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> 数据馈送计划</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> 数据源订阅</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>数据源</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> 数据源</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>派生信号</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> 派生信号</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>文件夹</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> 区段文件夹</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> 特征文件夹</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>报表</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> 报表</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>区段</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> 区段</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> 细分测试组</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> 细分测试组草稿API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特征</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> 特征</a> </p> </td> 
  </tr>
 </tbody>
</table>