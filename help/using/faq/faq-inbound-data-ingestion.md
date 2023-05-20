---
description: 有关将离线数据纳入 Audience Manager 的常见问题解答。
keywords: ftp或s3；s3或ftp
seo-description: Frequently asked questions about bringing offline data into Audience Manager.
seo-title: Inbound Customer Data Ingestion FAQ
solution: Audience Manager
title: 入站客户数据摄取常见问题解答
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Onboarding Offline Data
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 89%

---

# 入站客户数据摄取常见问题解答{#inbound-customer-data-ingestion-faq}

有关将离线数据纳入 Audience Manager 的常见问题解答。

 

**能否概述一下载入流程？**

载入流程包括[将批量数据发送到 Audience Manager 概述](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)中所述的两个步骤：

* 步骤 1：同步用户 ID；
* 步骤 2：按照文件格式要求，创建并传输入站数据文件。

 

**能否概述一下部署流程？**

我们建议执行以下操作：

* 与您的数据提供商合作，根据 Adobe 规范对日常入站数据文件进行格式化。有关文件命名和语法要求，请参阅以下文档：
   * [ID 同步文件的名称和内容要求](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [入站数据文件内容：语法、无效字符、变量和示例](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [入站数据文件的 Amazon S3 名称和文件大小要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* 与您的 [!DNL Adobe] 顾问合作，将测试数据文件传输到 [!DNL Adobe] 以进行格式验证。
* 与您的 [!DNL Adobe] 顾问合作，生成适用于解释数据文件内容的分类。
* 在暂存/开发环境中，确认已将 ID 同步配置为正确选取数据提供商的访客 ID 并将其实时传输到 [!DNL Audience Manager] 服务器。
* 将 DIL/ID 同步部署到生产环境。您的 Adobe 顾问已将 ID 同步配置为 DIL 代码中的模块。
* 将生产数据文件传输到 [!DNL Audience Manager]。考虑到对 ID 同步映射的依赖性，虽然可以在将代码部署到生产环境后立即开始传输数据文件，但是在生产代码部署后的一周内开始传输数据可能更合适。

 

**我应使用哪种 FTP 模式传输压缩文件或加密文件？**

请参阅[入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

>[!WARNING]
>
>我们正在逐步停止对 FTP 配置的支持。虽然现有 FTP 集成仍支持入站数据文件摄取，但我们仍强烈建议使用 Amazon S3 载入离线数据以进行新集成。有关详细信息，请参阅[入站数据文件的 Amazon S3 名称和文件大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

 

**我能否先上传入站数据文件（[!DNL .sync] 或 [!DNL .overwrite] 文件），然后再将 [!DNL Audience Manager] 代码部署到生产环境中？**

能。只要您使用 [!UICONTROL cross-device data source] 為了儲存您上傳的CRM資料，Audience Manager一律會儲存資料。 事實上，請遵循 [!UICONTROL Profile Merge Rules] 2019年10月推出的Audience Manager增強功能允許僅限離線使用的使用案例，您無需將Audience Manager程式碼部署至生產環境，即可上傳資料和執行動作。 请参阅：

* [配置文件合并规则增强功能概述](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] - [以僅限離線資料為基礎的個人化](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

**我应该在一天中的哪个时刻传输文件？**

[!DNL Audience Manager] 一天中会多次检查和处理文件。您随时都能上传数据。

 

**需要多长时间才能定位已上传文件中的数据？**

在 48 小时后方可定位数据。此外，请勿将“成功上传”电子邮件理解为数据可用。该电子邮件仅意味着 [!DNL Audience Manager] 已选取文件并完成了处理的第一步。

 

**我应该多久发送一次文件？这些文件应该是完整文件还是增量文件？**

最佳做法是每天为新访客和数据已更改的访客发送一次增量文件。许多 [!DNL Audience Manager] 客户会每月发送一次完整文件。但是，这些文件间隔时间和增量是灵活的。您应在合适的时间以增量形式发送数据。

 

**Audience Manager 会将我的文件在服务器上保存多长时间？**

FTP 文件在处理后即会被删除。[!DNL S3] 文件将在 30 天后被删除。因格式、语法或其他错误而无法处理的文件将被删除。另请参阅[隐私和数据保留常见问题解答](../faq/faq-privacy.md)。

 

**完整文件和增量文件之间有何区别？**

* **完整：**&#x200B;完整文件会覆盖所有现有访客配置文件，并使用文件中的数据替换它们。完整文件由附加到文件名的 `.overwrite` 标记来标识。您可以使用 `.overwrite` 文件重置访客特征或删除已过时的失效特征。

   >[!NOTE]
   >
   >[!DNL .overwrite] 文件只会覆盖与此数据提供商关联的 [!DNL Audience Manager] 配置文件数据。换言之，在处理 [!DNL .overwrite] 文件之后，与访客关联的所有 [!DNL Audience Manager] 数据均将保持不变。

* **增量：**&#x200B;增量文件会向现有访客配置文件中附加新数据。增量文件由附加到文件名的 `.sync` 标记来标识。发送增量文件不会擦除或覆盖现有配置文件。

以下用例演示了这些文件类型如何影响存储的访客配置文件。

| 用例 | 描述 |
|---|---|
| 增量文件和完整文件 | <ul><li>第 1 天 `.sync` 文件内容：`visitor123 = a,b,c`</li><li>第 2 天 `.overwrite` 文件内容：`visitor123 = c,d,e`</li><li>第 3 天访客配置文件 ID 123 内容：`c,d,e`</li></ul> |
| 仅增量文件 | <ul><li>第 1 天 `.sync` 文件内容：`visitor123 = a,b,c`</li><li>第 2 天 `.sync` 文件内容：`visitor123 = c,d,e`</li><li>第 3 天访客配置文件 ID 123 内容：`a,b,c,d,e`</li></ul> |

有关完整和增量文件类型的更多信息，请参阅：

* [入站数据文件的 Amazon S3 名称和文件大小要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**如果我发送的文件中包含从未执行过页面上 ID 同步的访客的 ID，会发生什么情况？**

在处理期间，[!DNL Audience Manager] 会跳过该记录并继续处理下一个记录。如果将 [DPID（数据提供商 ID）](../reference/ids-in-aam.md)设置为跨设备 DPID，则会保存在 ID 同步之前摄取的数据，该数据在 ID 同步后可即刻使用。

 

**时间戳是什么，它有何用途？能否提供一个示例？**

时间戳用于日志和记录保存。格式正确的入站文件名所用的语法要求使用时间戳。请参阅：

* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**什麼是 [!DNL Data Provider ID (DPID)] 我要如何取得？**

Adobe 顾问将为您的特定数据源分配一个三位数或四位数的 [DPID（数据提供商 ID）](../reference/ids-in-aam.md)。此 ID 是唯一的，不会更改。

 

**日常数据文件可以有多大？**

请参阅[入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

 

**Audience Manager 是否支持文件压缩？**

是的，请参阅：

* [入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**我的数据源数据库中的主键是电子邮件地址。这是否被视为个人身份信息？**

是的。[!DNL Audience Manager] 不会在其数据库中存储电子邮件地址。在起始ID同步之前，應為訪客指派隨機產生的ID或電子郵件地址的單向雜湊版本。

 

**数据文件内容是否区分大小写？ID 同步呢？**

数据文件有两个基本组成部分：[!UICONTROL User ID]（请参阅[定义的文件变量](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)中的 [!UICONTROL User ID]）和配置文件数据（通常采用键值对或代码形式）。[!UICONTROL User ID] 区分大小写。通常，配置文件或键值数据不区分大小写。

 

**我应该使用 FTP 还是 [!DNL Amazon S3] 来传输文件？**

作为最佳做法，我们建议您使用 [!DNL Amazon S3]，因为该过程更简单。不管如何，[!DNL Audience Manager] 都会将 FTP 文件传输到 [!DNL S3]，因此，如果您自行将文件放置到 [!DNL Amazon S3] 上，可以简化该过程。此外，如果多个客户同时上传到 FTP，则他们会共享 FTP 的带宽，因此上传速度会较慢。[!DNL Amazon S3] 也是可复制和分发的，因此它通常比 FTP 服务器更安全、更可靠。有关更多信息，请参阅[关于 Amazon S3](../reference/amazon-s3.md)。

>[!WARNING]
>
>我们正在逐步停止对 FTP 配置的支持。雖然現有FTP整合仍支援傳入資料檔案擷取，但強烈建議使用 [!DNL Amazon S3] 載入離線資料以進行新整合。 有关详细信息，请参阅[入站数据文件的 Amazon S3 名称和文件大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)。

 

**Audience Manger 如何处理入站文件？**

[!DNL Audience Manager] 使用 [!DNL Amazon Simple Queue Service (SQS)] 进行入站数据处理。下面是其工作原理：

1. [!DNL Audience Manager] 客户将其入站数据上传到 [!DNL Amazon S3] 存储段。
1. 数据进入 [!DNL Amazon SQS] 队列，等待 [!DNL Audience Manager] 处理。
1. [!DNL Audience Manager] 从 [!DNL Amazon SQS] 队列中最多读取 119000 个条目，并将它们分成 3 批。每批文件会同时进行处理。

 

**我需要同时上传多个文件。是否会同时处理这些文件？**

视情况而定。[!DNL Audience Manager] 从 [!DNL Amazon SQS] 队列中最多读取 119000 个条目，并将它们分成 3 批。只有当文件位于同一批次中时，系统才会同时处理它们。但是，由于 [!DNL Audience Manager] 每天摄取的数据量很大，因此我们不能保证任何文件处理顺序。

>[!MORELIKETHIS]
>
>* [批量数据传输流程说明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

