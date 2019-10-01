---
description: 介绍用于基于文件的ID同步的必填字段、语法和命名约定。 Name and organize your file contents according to these specifications.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: ID 同步文件的名称和内容要求
solution: Audience Manager
title: ID 同步文件的名称和内容要求
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
translation-type: tm+mt
source-git-commit: 4bc3d7c0a34619e556f58b39b7812a5612050f7f

---


# ID 同步文件的名称和内容要求 {#name-and-content-requirements-for-id-synchronization-files}

Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）in this document indicate code elements and options. 请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## File Name Syntax and Examples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID file names contain the following required and optional elements:

*`[adobe_id_]`* _DPID_DPID.gz *`[c2c_id_]`*`MASTERDPID_DPID`*[]*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*[]

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
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file. 将设备ID与其他设备ID或客户ID(DPUUID)匹配时，请使用此前缀。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>A static prefix that identifies the file as an ID synchronization file for People-Based Destinations. Use this prefix when matching customer IDs (DPUUIDs) to hashed email addresses for People-Based Destinations.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> 主数据提供者ID是文件名中DPID的父ID。 此外，数据文件中的第一个用户ID与主ID相对应。 随后的DPID是属于主设备的其他标识符。 同步将文件名中的DPID映射到文件中的UUID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。 这些ID表示与主DPID关联的实体或数据源。 同步将文件名中的DPID映射到文件中的UUID。 </p> <p>文件名中的DPID数量必须与数据文件中的UUID数量匹配。 例如，假设您的文件名包含主DPID和3个DPID。 数据文件必须包括4个对应的UUID列，格式如下文件内容部分所述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>以秒为单位的10位UNIX时间戳。 时间戳有助于使每个文件名都是唯一的。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>表示正常的完全同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。 将大文件拆分为多个小文件时使用。 这有助于缩短处理时间。 该数字指示要发送的原始文件的哪个部分。 请参阅以下文件名示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>指定使用可选的gzip压缩来压缩文件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 文件名示例

The following examples show properly formatted files names. 您的文件名可能看起来类似。

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_145442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> 有关基于人员的目标的ID同步文件命名（c2c前缀），请参阅 [A —— 基于所有在线活动和脱机数据组合的个性化](../../../features/destinations/people-based-destinations-workflow-combined.md) ，或 [B —— 基于仅脱机数据的个性化](../../../features/destinations/people-based-destinations-workflow-offline.md)。

## File Content Syntax and Examples {#file-content-syntax}

The contents of an ID file include the following elements:

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs (). [!DNL UUID]In each row, separate the IDs with a tab. The following example shows a properly formatted ID file. Your contents could look similar.

```
abc123 def456 ghi789 xyz987
```

## 同步将DPUUID与UUID匹配 {#sync-matches-dpuuids-uuids}

The purpose of an ID sync file is to sync the DPUUIDs from your own Data Sources with  UUIDs. [](../../../reference/ids-in-aam.md)[!DNL Audience Manager]Synchronization maps the s from the master  and its related s to the  s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. [!DNL DPUUID][!DNL DPID][!DNL DPID][!DNL Audience Manager][!DNL UUID]例如，请取下此处显示的两个范例文件：

* **** 文件1: `adobe_id_0_12345_1476312152.sync`

* **** 文件2:  `adobe_id_12345_67890_1476312876.sync`

<br/>

Given the sample name and contents, the IDs map together like this:

**文件1** (下 [载示例文件](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = Adobe Audience Manager UUID | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

第1步：id sync进程将从12345 [!DNL DPUUID]开始 [!DNL DPID] 与左 [!DNL Audience Manager] 列中的 [!DNL UUID]s同步。 请注意， [!DNL DPID] 文件名中的“0”表示 [!DNL Audience Manager][!DNL UUID]s。
<br/>

**文件2** (下 [载示例文件](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

第2步：来 [!DNL DPUUID]自12345 [!DNL DPID] 的URL已在步骤1中与Audience manager同 [!DNL UUID]步。此ID同步的作用是将67890 [!DNL DPUUID]中的 [!DNL DPID] s与步骤1中的Audience Manager [!DNL UUID]同步。

<br/>

## 其他格式要求 {#other-format-reqs}

用户ID不能：

* 在ID本身中包含选项卡。 选项卡仅用于在数据文件中分隔单个ID。
* 包含个人识别信息([!UICONTROL PII])。
* 使用 [!DNL URL] 编码。 仅传递未编码的ID。

任何以制表符或空格结尾的行都不会被处理或实现。 通常，请确保行末尾保持清晰。