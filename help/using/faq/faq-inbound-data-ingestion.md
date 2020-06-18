---
description: 有关将离线数据引入Audience Manager的常见问题。
keywords: ftp or s3;s3 or ftp
seo-description: 有关将离线数据引入Audience Manager的常见问题。
seo-title: 入站客户数据摄取常见问题解答
solution: Audience Manager
title: 入站客户数据摄取常见问题解答
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 3%

---


# 入站客户数据摄取常见问题解答{#inbound-customer-data-ingestion-faq}

有关将离线数据引入Audience Manager的常见问题。

 

**您能否总结入职流程？**

入门过程包含将批数据发送到 [Audience Manager概述中描述的两个步骤](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* 第1步： 同步用户ID;
* 第2步： 根据文件格式要求创建和传输入站数据文件。

 

**您能否总结部署过程？**

我们建议：

* 请与数据提供商合作，根据Adobe规范格式化每日入站数据文件。 有关文件命名和语法要求，请参阅以下文档：
   * [ID 同步文件的名称和内容要求](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [入站数据文件内容： 语法、无效字符、变量和示例](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [入站数据文件的Amazon S3名称和文件大小要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* 请与顾问 [!DNL Adobe] 合作，将测试数据文件传输到格式 [!DNL Adobe] 验证中。
* 与顾问 [!DNL Adobe] 合作，生成适用于解释数据文件内容的分类。
* 在分阶段／开发环境中，确认ID同步配置为正确提取数据提供者的访客ID并将其实时传输到 [!DNL Audience Manager] 服务器。
* 将DIL/ID同步部署到生产。 ID同步将由Adobe顾问配置为DIL代码中的模块。
* 将生产数据文件传输到 [!DNL Audience Manager]。 考虑到对ID同步映射的依赖性，在生产代码部署后一周内开始传输数据可能是有意义的，但是您可以在代码进入生产后立即开始传输数据文件。

 

**我应使用什么FTP模式传输压缩或加密文件？**

请参 [阅入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

>[!WARNING]
>
>我们正在逐步取消对FTP配置的支持。 虽然现有FTP集成仍支持入站数据文件摄取，但我们强烈建议使用Amazon S3载入离线数据以进行新集成。 有关 [详细信息，请参阅Amazon S3入站数据文件的名称和文件大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 。

 

**我能否先上传入站数据文件（[!DNL .sync]或[!DNL .overwrite]文件），然后再将[!DNL Audience Manager]代码部署到生产中？**

能。只要您使用来存 [!UICONTROL cross-device data source] 储您上传的CRM数据，Audience Manager始终会存储这些数据。 事实上，在2019年10月 [!UICONTROL Profile Merge Rules] Audience Manager启动的增强功能允许仅脱机使用案例之后，您无需将Audience Manager代码部署到生产环境即可上传数据并对其执行操作。 请参阅：

* [用户档案合并规则增强功能概述](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] -基 [于仅线下数据的个性化](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br> 

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**我应该在几点传输我的文件？**

[!DNL Audience Manager] 一天中多次检查和处理文件。 随时上传数据。

 

**从已上载文件获取数据进行定位需要多长时间？**

48小时后，数据可用于定位。 此外，请勿将“成功上传”电子邮件解释为数据可用的语句。 这仅意味着 [!DNL Audience Manager] 已拾取文件并完成了处理的第一步。

 

**我应该多久发送一次文件，这些文件应是完整文件还是增量文件？**

作为最佳实践，对于新访客和数据已更改的访客，每天发送一次增量文件。 许多 [!DNL Audience Manager] 客户每月发送一次完整文件。 但是，这些文件间隔和增量是灵活的。 您应该以增量发送数据，并有时发送对您有意义的数据。

 

**Audience Manager将我的文件保存在服务器上多长时间？**

FTP文件在处理后即被删除。 [!DNL S3] 文件将在30天后删除。 由于格式、语法或其他错误而无法处理的文件将被删除。 另请参阅隐私 [和数据保留常见问题解答](../faq/faq-privacy.md)。

 

**完整文件和增量文件之间有何区别？**

* **完整：** 完整文件会覆盖所有现有访客用户档案，并用文件中的数据替换这些数据。 完整文件由文件名附 `.overwrite` 加的标记来标识。 您可以使用文 `.overwrite` 件重置访客特征或删除过时的过时的过时特征。

   >[!NOTE]
   >
   >文 [!DNL .overwrite] 件只覆盖与 [!DNL Audience Manager] 此数据提供程序关联的用户档案数据。 换言之，与访客关 [!DNL Audience Manager] 联的所有数据在文件处理后 [!DNL .overwrite] 都保持不变。

* **增量：** 增量文件会向现有访客用户档案附加新数据。 增量文件由附加到文 `.sync` 件名的标记进行标识。 在增量文件中发送不会删除或覆盖现有用户档案。

以下用例演示了这些文件类型如何影响存储的访客用户档案。

| 用例 | 描述 |
|---|---|
| 增量和完整 | <ul><li>第1天 `.sync` 文件内容： `visitor123 = a,b,c`</li><li>第2天 `.overwrite` 文件内容： `visitor123 = c,d,e`</li><li>第3天访客用户档案ID 123内容： `c,d,e`</li></ul> |
| 仅增量 | <ul><li>第1天 `.sync` 文件内容： `visitor123 = a,b,c`</li><li>第2天文 `.sync` 件内容： `visitor123 = c,d,e`</li><li>第3天访客用户档案ID 123内容： `a,b,c,d,e`</li></ul> |

有关完整和增量文件类型的详细信息，请参阅：

* [入站数据的Amazon S3名称和文件大小要求……](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**如果我向从未执行过页面ID同步的访客发送ID文件，会发生什么情况？**

在处理过 [!DNL Audience Manager] 程中，跳过该记录并转到下一个记录。 如果将 [DPID（数据提供者ID）](../reference/ids-in-aam.md) 设置为跨设备DPID，则保存在ID同步之前摄取的数据，并在ID同步发生后很快可用。

 

**时间戳是什么，它用于什么，您能提供一个示例吗？**

时间戳用于记录和记录保存。 格式正确的入站文件名使用的语法需要它们。 请参阅：

* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**什么是[!DNL Data Provider ID (DPID)]，如何获得？**

您的Adobe顾问将为您的特定数据源分配一个三位 [或四位数的DPID](../reference/ids-in-aam.md) （数据提供程序ID）。 此ID是唯一的，不会更改。

 

**日常数据文件可以有多大？**

请参 [阅入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

 

**Audience Manager是否支持文件压缩？**

是的，请参阅:

* [入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**我的数据源数据库中的主键是电子邮件地址。 这是否被视为个人可识别信息？**

能。[!DNL Audience Manager] 不在其数据库中存储电子邮件地址。 在启动ID同步之前，应为访客分配随机生成的ID或电子邮件地址的单向哈希版本。

 

**数据文件内容是否区分大小写？ ID同步如何？**

数据文件有两个基本组件： A( [!UICONTROL User ID] 请参 [!UICONTROL User ID] 阅文 [件变量定义](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined))和用户档案数据，通常以键值对或代码的形式。 区 [!UICONTROL User ID] 分大小写。 通常，用户档案或键值数据不区分大小写。

 

**我应该使用FTP还是[!DNL Amazon S3]传输文件？**

作为最佳实践，我们建议 [!DNL Amazon S3] 这样做，因为过程更简单。 [!DNL Audience Manager] 无论如何， [!DNL S3] 都可以传输FTP文件，因此，如果您自己放置文件，流程将更加 [!DNL Amazon S3] 简化。 此外，同时上传到FTP的客户共享FTP的带宽，因此他们预计上传速度会更慢。 [!DNL Amazon S3] 也是复制和分发的，因此它通常比FTP服务器更安全、更可靠。 有关详细信息，请 [参阅关于Amazon S3](../reference/amazon-s3.md)。

>[!WARNING]
>
>我们正在逐步取消对FTP配置的支持。 虽然现有FTP集成仍支持入站数据文件摄取，但我们强烈建议使用 [!DNL Amazon S3] 入站离线数据进行新集成。 有关 [详细信息，请参阅Amazon S3入站数据文件的名称和文件大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 。

 

**受众管理器如何处理入站文件？**

[!DNL Audience Manager] 用于 [!DNL Amazon Simple Queue Service (SQS)] 入站数据处理。 下面是其工作原理：

1. [!DNL Audience Manager] 客户将其入站数据上传到 [!DNL Amazon S3] 时段。
1. 数据进入 [!DNL Amazon SQS] 队列，等待被处理 [!DNL Audience Manager]。
1. [!DNL Audience Manager] 从队列中读取多达19000个条目 [!DNL Amazon SQS] ，并将它们分成多达3批。 每批中的文件将同时处理。

 

**我需要同时上传多个文件。 文件是否将同时处理？**

看情况。 [!DNL Audience Manager] 从队列中读取多达19000个条目 [!DNL Amazon SQS] ，并将它们分成多达3批。 只有在同一批处理您的文件时，才会同时处理它们。 但是，由于日常采集的数据量 [!DNL Audience Manager] 很大，无法保证文件处理顺序。

>[!MORELIKETHIS]
>
>* [描述的批处理数据传输过程](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

