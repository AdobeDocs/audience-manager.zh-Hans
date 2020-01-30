---
description: 有关将离线数据导入Audience manager的常见问题解答。
keywords: ftp or s3;s3 or ftp
seo-description: 有关将离线数据导入Audience manager的常见问题解答。
seo-title: 入站客户数据摄取常见问题解答
solution: Audience Manager
title: 入站客户数据摄取常见问题解答
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 22336b052af1c438136e4a6cfd6ad88393503f16

---


# 入站客户数据摄取常见问题解答{#inbound-customer-data-ingestion-faq}

有关将离线数据导入Audience manager的常见问题解答。

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**您能否总结入门过程？**

入门过程由2个核心组件组成，这些组件在“批量数据传 [输过程”中进行了说明](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)。 这包括：

* ID同步
* 入站数据文件( [!DNL .sync] 文件或 [!DNL .overwrite] 文件)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

以下是查看文档后您可能发现有帮助的问题和答案列表。

>[!NOTE]
>
>为了简化演示，本节中的示例被简化或缩短。 有关文件格式和语法的详细规范，请参阅入站数据摄取文档。

<br> 

**您能否总结部署过程？**

我们建议：

* 与数据提供者一起根据规范设置每日入站数据文件的格 [!DNL Adobe] 式。
* 将测试数据文件传输到以进 [!DNL Adobe] 行格式验证。
* 与顾问一 [!DNL Adobe] 起制作一个适用于解释数据文件内容的分类。
* 在分阶段／开发环境中，确认ID同步配置为正确获取数据提供者的访客ID并将其实时传输到服 [!DNL Audience Manager] 务器。
* 将DIL/ID同步部署到生产。 ID同步将由Adobe顾问配置为DIL代码中的模块。
* 将生产数据文件传输到 [!DNL Audience Manager]。 鉴于ID同步映射的依赖性，在生产代码部署后一周内开始传输数据可能是有意义的，但是，在代码投入生产后，您可以立即开始传输数据文件。

<br> 

**我应使用哪种FTP模式传输压缩或加密文件？**

请参 [阅入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

<br> 

**我能否先上传入站数据文件（[!DNL .sync]或[!DNL .overwrite]文件），然后再将[!DNL Audience Manager]代码部署到生产中？**

能。只要您使用跨设备数据源存储您上传的CRM数据，Audience manager就始终会存储这些数据。 事实上，在Audience manager于2019年10月启动的Profile Merge Rules增强功能（允许仅脱机使用案例）之后，您无需将Audience manager代码部署到生产中即可上传数据并对数据执行操作。 请参阅：

* [配置文件合并规则增强概述](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* 基于人员的目标- [基于仅线下数据的个性化](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

<br> 

**我应该在几点钟传输文件？**

[!DNL Audience Manager] 一天中多次检查和处理文件。 随时上传数据。

<br> 

**上载文件中的数据可用于定位需要多长时间？**

48小时后，数据可供定位。 此外，请勿将“成功上传”电子邮件解释为数据可用的声明。 这只表示已 [!DNL Audience Manager] 经选取了文件并完成了第一步处理。

<br> 

**我应该多久发送一次文件，这些文件应是完整文件还是增量文件？**

作为最佳实践，为新访客和数据已更改的访客每天发送增量文件一次。 许多 [!DNL Audience Manager] 客户每月发送一次完整文件。 但是，这些文件间隔和增量是灵活的。 您应该按增量发送数据，并在有时发送数据，这对您来说是有意义的。

<br> 

**Audience Manager在服务器上保存我的文件多长时间？**

FTP文件在处理后即被删除。 [!DNL S3] 文件将在30天后删除。 由于格式、语法或其他错误而无法处理的文件将被删除。 另请参阅隐私 [和数据保留常见问题解答](../faq/faq-privacy.md)。

<br> 

**完整文件和增量文件之间有何区别？**

* **** 完整：完整文件将覆盖所有现有访客资料，并用文件中的数据替换这些资料。 完整文件由附加到文件 `.overwrite` 名的标记标识。 您可以使用文 `.overwrite` 件重置访客特征或删除陈旧的过时特征。

   >[!NOTE]
   >
   >文件 [!DNL .overwrite] 仅覆盖与此数据 [!DNL Audience Manager] 提供者关联的配置文件数据。 换句话说，与访客关 [!DNL Adobe Analytics] 联的所有数据在文件处理完成后 [!DNL .overwrite] 将保持不变。

* **** 增量：增量文件会向现有访客配置文件添加新数据。 增量文件由附加到文件 `.sync` 名的标记标识。 在增量文件中发送不会擦除或覆盖现有配置文件。

以下用例演示了这些文件类型如何影响存储的访客配置文件。

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>增量和完整</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">第1天文 <code> .sync</code> 件内容： <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">第2天 <code> .overwrite</code> 文件内容： <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> 第3天访客资料ID 123包含 <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>仅增量</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">第1天文 <code> .sync</code> 件内容： <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">第2天 <code> .sync</code> 文件内容： <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">第3天访客资料ID 123包含 <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

有关完整和增量文件类型的详细信息，请参阅：

* [入站数据的Amazon S3名称和文件大小要求……](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**如果我向从未执行页面ID同步的访客发送ID文件，会发生什么情况？**

在处理过程 [!DNL Audience Manager] 中，您只需跳过该记录并转到下一个记录。 如果将DPID（数据提供者ID）设置为跨设备DPID，则保存在ID同步之前摄取的数据，并在ID同步发生不久后可供使用。

<br> 

**时间戳是什么，它用于什么，您能提供一个示例吗？**

时间戳用于记录和记录保存。 格式正确的入站文件名使用的语法需要这些参数。 请参阅：

* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**什么是数据提供者ID(DPID)，我如何获得它？**

您的Adobe顾问将为您的特定数据源分配一个三位数或四位数的DPID。 此ID是唯一的，不会更改。

<br> 

**每日数据文件可以有多大？**

请参 [阅入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。

<br> 

**Audience manager是否支持文件压缩？**

是的，请参阅:

* [入站数据传输文件的文件压缩](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [入站数据文件的 Amazon S3 名称要求](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**我的数据源数据库中的主键是电子邮件地址。 这是否被视为个人身份识别信息？**

能。[!DNL Audience Manager] 不会将电子邮件地址存储在我们的数据库中。 在启动ID同步之前，应为访客分配随机ID或电子邮件地址的单向哈希版本。

<br> 

**数据文件内容是否区分大小写？ ID同步如何？**

数据文件有两个基本组件：用户ID(请参阅“文件变量已定 [义”中的用户ID](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined))和配置文件数据，通常以键值对或代码的形式显示。 用户ID区分大小写。 通常，配置文件或键值数据不区分大小写。

<br> 

**我应该使用FTP还是[!DNL Amazon S3]传输文件？**

作为最佳实践，我们建议 [!DNL Amazon S3] 这样做，因为过程更简单。 [!DNL Audience Manager] 无论如何传输FTP [!DNL S3] 文件，这样，如果您自己放置文件，流程就会更加 [!DNL Amazon S3] 简化。 此外，同时上传到FTP的客户共享FTP的带宽，因此他们预计上传速度会更慢。 [!DNL Amazon S3] 也是复制和分发的，因此它通常比FTP服务器更安全、更可靠。 有关详细信息，请参 [阅关于Amazon S3](../reference/amazon-s3.md)。

<br> 

**Audience Manger如何处理入站文件？**

[!DNL Audience Manager] 用于 [!DNL Amazon Simple Queue Service (SQS)] 入站数据处理。 下面是其工作原理：

1. [!DNL Audience Manager] 客户将其入站数据上传到 [!DNL Amazon S3] 存储段。

2. 数据进入队 [!DNL Amazon SQS] 列，等待被处理 [!DNL Audience Manager]。

3. [!DNL Audience Manager] 从队列中最多读取119000个条目， [!DNL Amazon SQS] 并将它们分成多达3个批。 每批中的文件将同时处理。

<br> 

**我需要同时上传多个文件。 文件是否将同时处理？**

看情况。 [!DNL Audience Manager] 从队列中最多读取119000个条目， [!DNL Amazon SQS] 并将它们分成多达3个批。 只有当文件以同一批处理结束时，才会同时处理它们。 但是，由于每天摄取的数据量很大， [!DNL Audience Manager] 无法保证任何文件处理顺序。

>[!MORELIKETHIS]
>
>* [描述的批数据传输流程](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

