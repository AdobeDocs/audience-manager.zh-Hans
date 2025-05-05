---
description: 介绍用于基于文件的ID同步的必填字段、语法和命名约定。 根据这些规范命名并组织文件内容。
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: ID同步文件的名称和内容要求
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '782'
ht-degree: 3%

---

# ID同步文件的名称和内容要求 {#name-and-content-requirements-for-id-synchronization-files}

介绍用于基于文件的ID同步的必填字段、语法和命名约定。 根据这些规范命名并组织文件内容。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中说明了代码元素和选项。 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 文件名语法和示例 {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID文件名包含以下必需元素和可选元素：

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>将文件标识为ID同步文件的静态前缀。 当设备ID与其他设备ID或客户ID (DPUUID)匹配时，请使用此前缀。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>一个静态前缀，用于将文件标识为People-Based Destinations的ID同步文件。 当将客户ID (DPUUID)匹配到基于人员的目标的哈希电子邮件地址时，请使用此前缀。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>主数据提供程序ID是文件名中DPID的父ID。 此外，数据文件中的第一个用户ID对应于主ID。 后续DPID是属于主数据库的其他标识符。 同步会将文件名中的DPID映射到文件中的UUID。</p> <p>此DPID必须仅包含设备ID，如AAM UUID、GAID、IDFA等。 它不能包含DPUUID。 这样做可能会导致不正确的同步。</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>数据提供程序ID。 这些ID表示与主DPID关联的实体或数据源。 同步会将文件名中的DPID映射到文件中的UUID。 </p> <p>文件名中的DPID数量必须与数据文件中的UUID数量匹配。 例如，假设您的文件名包含一个主DPID和3个DPID。 您的数据文件必须包含4个对应的UUID列，其格式如下面的文件内容部分中所述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>以秒为单位的10位数UNIX时间戳。 时间戳有助于使每个文件名唯一。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>表示正常完全同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。 将大文件拆分为多个小文件时使用。 这有助于缩短处理时间。 该数字表示您传入的原始文件的哪个部分。 请参阅下面的文件名示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>指定使用可选的gzip压缩来压缩文件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 文件名示例

以下示例显示格式正确的文件名。 您的文件名可能类似。

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> 有关基于人员的目标的ID同步文件命名（c2c前缀），请参阅[工作流A — 基于所有在线活动和离线数据相结合的Personalization](../../../features/destinations/people-based-destinations-workflow-combined.md)或[工作流B — 基于仅离线数据的Personalization](../../../features/destinations/people-based-destinations-workflow-offline.md)。

## 文件内容语法和示例 {#file-content-syntax}

ID文件的内容包括以下元素：

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

该文件包含用户ID ([!DNL UUID])。 在每行中，使用制表符分隔ID。 以下示例显示了格式正确的ID文件。 您的内容可能类似。

```
abc123 def456 ghi789 xyz987
```

### 文件内容注意事项 {#considerations}

创建入站文件时，请确保第一列仅填充设备ID，如[!DNL AAM UUID]、[!DNL GAID]、[!DNL IDFA]等。 有关Audience Manager支持的ID的详细说明，请参阅Audience Manager[&#128279;](../../../reference/ids-in-aam.md)中的ID索引。

>[!IMPORTANT]
>
>不要在第一列上使用[DPUUID](../../../reference/ids-in-aam.md)。 这样做可能会导致不正确的同步。

## 同步将DPUUID与UUID匹配 {#sync-matches-dpuuids-uuids}

ID同步文件的用途是从您自己的数据源将[DPUUID](../../../reference/ids-in-aam.md)与[!DNL Audience Manager]个UUID同步。 同步将[!DNL DPUUID]从母版[!DNL DPID]及其相关[!DNL DPID]映射到[!DNL Audience Manager] [!DNL UUID]。在文件名和正文中放置ID的位置决定了这些标识符如何相互映射。 例如，下面显示了两个示例文件：

* **文件1：** `adobe_id_0_12345_1476312152.sync`

* **文件2：** `adobe_id_12345_67890_1476312876.sync`

<br/>

给定示例名称和内容，ID将如下所示映射到一起：

**文件1** （[下载样本文件](assets/adobe_id_0_12345_1476312152.sync)）

| DPID 0 = ADOBE AUDIENCE MANAGER UUID | DPID12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

步骤1：ID同步过程将从[!DNL DPID]12345将[!DNL DPUUID]与左列中的[!DNL Audience Manager] [!DNL UUID]同步。 请注意，文件名中的[!DNL DPID]“0”表示[!DNL Audience Manager] [!DNL UUID]。
<br/>

**文件2** （[下载样本文件](assets/adobe_id_12345_67890_1477846458.sync)）

| [!DNL DPID]12345 | [!DNL DPID]67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

步骤2： [!DNL DPID]中的[!DNL DPUUID]12345已在步骤1中与Audience Manager[!DNL UUID]同步。此ID同步将执行步骤1中将[!DNL DPID]67890的[!DNL DPUUID]与步骤1中的Audience Manager[!DNL UUID]同步。

<br/>

## 其他格式要求 {#other-format-reqs}

用户ID不能：

* 在ID本身中具有选项卡。 制表符仅用于分隔数据文件中的各个ID。
* 包含个人身份信息([!UICONTROL PII])。
* 使用[!DNL URL]编码。 仅传入未编码的ID。

将不会处理或实现任何以制表符或空格结尾的行。 通常，请确保清除行的结尾。
