---
description: 有关将离线数据引入Audience Manager的常见问题。
keywords: ftp或s3；s或ftp
seo-description: 有关将离线数据引入Audience Manager的常见问题。
seo-title: 入站客户数据摄取常见问题解答
solution: Audience Manager
title: 入站客户数据摄取常见问题解答
uuid: 491e9ec1-4731-46a8-86e7-d8 c613 e6 cenc
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Inbound Customer Data Ingestion FAQ{#inbound-customer-data-ingestion-faq}

有关将离线数据引入Audience Manager的常见问题。

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**您能否总结入门培训流程？**

The onboarding process consists of 2 core components described in [Batch Data Transfer Process Described](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process). 其中包括：

* ID同步
* Inbound Data File ( [!DNL .sync] file or [!DNL .overwrite] file)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

以下是问题和答案列表，在查看文档后您可能会发现有帮助。

>[!NOTE]
>
>本节中的示例针对简单和演示目的进行了简化或缩短。有关文件格式和语法的详细规范，请参阅入站数据摄取文档。

<br> 

**您可以总结部署过程吗？**

我们建议以下各项：

* Work with your data provider to format the daily inbound data file according to [!DNL Adobe] specifications.
* Transfer a test data file to [!DNL Adobe] for format verification.
* Work with your [!DNL Adobe] consultant to produce a taxonomy suitable for interpreting the contents of the data file.
* In the staging/development environment, confirm that the ID sync is configured to properly pick up the data provider's visitor ID and transfer it to the [!DNL Audience Manager] servers in realtime.
* 将DIL/ID部署到生产。ID同步将在DIL代码中由您的Adobe顾问配置为一个模块。
* Transfer production data files to [!DNL Audience Manager]. 鉴于ID同步映射的依赖关系，在生产代码部署后最多可在一周内开始传输数据最有意义，但在代码进入生产后，您可以开始传输数据文件。

<br> 

**我应该使用什么FTP模式传输压缩或加密的文件？**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**我能否先上传入站数据文件（[!DNL .sync]或[!DNL .overwrite]文件），然后再将[!DNL Audience Manager]代码部署到生产中？**

* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>用例 1</b> </p> </td> 
   <td colname="col2"> <p>星期一，当访客ABC登录时CRM数据库中的CRM数据库中识别出的访客启动客户端ID同步。<span class="keyword"> Audience Manager</span> 将访客ABC的映射存储到 <span class="keyword"> Audience Manager</span> 访客123。 </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC“性别”=“male”，“opause_ shopper”=“yes”</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">从存储的ID同步映射识别访客ABC。 </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>用例 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF“性别”=“女性”、“酒类_发烧友”=“yes”</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> 没有此访客的记录(或关联的访客ID)，因此不会处理此记录。 </p> <p>星期二，访客DEF登录。此操作为该访客启动第一个客户端ID同步。This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. 但是，此访客没有与其个人资料关联的CRM数据。<span class="keyword"> 因此，Audience Manager</span> 不会返回和重新处理旧文件。 </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF“性别”=“女性”、“酒类_发烧友”=“yes”、“DMA”=“paris”</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">识别来自存储ID同步映射的访客DEF。 </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>案例3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> . sync</code> 文件包含： </p> <p> 
     <ul class="simplelist"> 
      <li><code> GI123456789</code> </li> 
     </ul> </p> <p> <code> . overwire</code> 文件，包含： </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GII“性别”=“enterprise”ankine_ spareast=“no”</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JLOG“性别”=“grian”warn_ spareast=“yes”</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> 将访客JKL的映射记录保存在上一ID同步的ID789中。 </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">从存储的ID同步映射识别访客JKL。 </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">忽略访客HI的特征关联，因为其ID只在当前批次中同步。To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**我应在哪一天传输文件？**

[!DNL Audience Manager] 一整天检查和处理文件。随时上传您的数据。

<br> 

**从上传的文件中获取数据可用于定位多久？**

数据可在48小时后进行定位。此外，请勿将“成功上传”电子邮件解释为可用数据的声明。This only means that [!DNL Audience Manager] has picked up the file and completed the first step of processing.

<br> 

**我应多久发送文件，这些文件应该是完整的还是递增的？**

作为最佳实践，为新访客和数据已更改的访客每天发送一次增量文件。Many [!DNL Audience Manager] customers send a full file once per month. 但是，这些文件间隔和增量是灵活的。您应以增加的时间和对您有意义的有时发送数据。

<br> 

**Audience Manager会将我的文件保存在服务器上多长时间？**

FTP文件在处理后被删除。[!DNL S3] 文件将在30天后删除。将删除由于格式、语法或其他错误而无法处理的文件。See also, [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**完整和递增文件之间有何区别？**

* **完全：** 完整文件会覆盖所有现有访客资料，并用文件中的数据替换这些档案。Full files are identified by the `.overwrite` tag appended to the file name. You can use a `.overwrite` file to reset visitor traits or remove stale, obsolete traits.

   >[!NOTE]
   >
   >The [!DNL .overwrite] files only overwrite [!DNL Audience Manager] profile data associated to this data provider. In other words, all [!DNL Adobe Analytics] data associated to the visitor remains intact after a [!DNL .overwrite] file has been processed.

* **增量：** 增量文件会向现有访客配置文件附加新数据。Incremental files are identified by the `.sync` tag appended to the file name. 在增量文件中发送不会擦除或覆盖现有配置文件。

以下用例演示这些文件类型如何影响存储的访客配置文件。

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>增量和全部</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Day 2 <code> .overwrite</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> Day 3 visitor profile ID 123 contains <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>仅限增量</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Day 1 <code> .sync</code> file contents: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Day 2 <code> .sync</code> file contents: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">Day 3 visitor profile ID 123 contains <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

有关完整和递增文件类型的更多信息，请参阅：

* [入站数据的Amazon S名称和文件大小要求…](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**如果我向从未执行页面ID同步的访客提供ID，会出现什么情况？**

During processing, [!DNL Audience Manager] simply skips that record and moves on to the next. 如果DPID(数据提供程序ID)设置为跨设备DPID，则在保存ID同步之前摄取的数据会被保存，并可在ID同步后很快使用。

<br> 

**时间戳是什么？它为哪些时间提供了示例？**

时间戳用于记录和记录保留。它们是使用格式正确的入站文件名称所使用的语法。请参阅：

* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**什么是数据提供者ID(DPID)？如何获取它？**

Adobe顾问将为您的特定数据源分配三位或四位数字PID。此ID是唯一的，但不会更改。

<br> 

**每天的数据文件可以有多大？**

See [File Compression for Inbound Data Transfer Files](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Audience Manager是否支持文件压缩？**

是的，请参阅:

* [入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**我的数据源数据库中的主要密钥是电子邮件地址。Is that considered personally identifiable information?**

能。[!DNL Audience Manager] 不会在我们的数据库中存储电子邮件地址。在启动ID同步之前，应为访问者分配随机ID或电子邮件地址的单向散列版本。

<br> 

**数据文件内容是否区分大小写？How about the ID sync?**

数据文件有两个基本组件：唯一用户ID(UUID)和配置文件数据，通常采用键值对或代码的形式。UUID区分大小写。通常情况下，个人资料或密钥值数据不区分大小写。

<br> 

**我应该使用FTP[!DNL Amazon S3]还是传输文件？**

As best practice, we recommend [!DNL Amazon S3] because the process is simpler. [!DNL Audience Manager] 将FTP文件传输到 [!DNL S3] 任何位置，这样，如果您将文件拖放到自己身上，流程会更加 [!DNL Amazon S3] 简化。更重要的是，同时上传至FTP的客户将共享FTP的带宽，因此他们应期望速度更慢。[!DNL Amazon S3] 也会被复制和分发，因此通常比FTP服务器更安全、可靠。For more information, see [About Amazon S3](../reference/amazon-s3.md).

<br> 

**Audience Manger如何处理入站文件？**

[!DNL Audience Manager] 用于 [!DNL Amazon Simple Queue Service (SQS)] 入站数据处理。下面是此操作的原理：

1. [!DNL Audience Manager] 客户将其入站数据上传到 [!DNL Amazon S3] 桶。

2. The data enters the [!DNL Amazon SQS] queue, waiting to be processed by [!DNL Audience Manager].

3. [!DNL Audience Manager] 最多可从 [!DNL Amazon SQS] 队列中读取110000000条目，并在最多批处理中拆分这些条目。同时处理每个批次中的文件。

<br> 

**我需要同时上传多个文件。Will the files be processed simultaneously?**

它取决于。[!DNL Audience Manager] 最多可从 [!DNL Amazon SQS] 队列中读取110000000条目，并在最多批处理中拆分这些条目。仅当文件在同一批次中结束时，才会同时处理文件。However, due to the high amount of data ingested by [!DNL Audience Manager] on a daily basis, we cannot guarantee any file processing order.

>[!MORE_ LIKE_ This]
>
>* [介绍的批量数据传输流程](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md#batch-data-transfer-process)

