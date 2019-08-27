---
description: 介绍用于基于文件的ID同步的必填字段、语法和命名约定。根据这些规范命名和组织文件内容。
seo-description: 介绍用于基于文件的ID同步的必填字段、语法和命名约定。根据这些规范命名和组织文件内容。
seo-title: ID 同步文件的名称和内容要求
solution: Audience Manager
title: ID 同步文件的名称和内容要求
uuid: bfe42af9-9149-4da3-830e-f227 c4 e610 c2
translation-type: tm+mt
source-git-commit: 5624eac36a7f2b8892136688f89fc22af241fc3a

---


# ID 同步文件的名称和内容要求 {#name-and-content-requirements-for-id-synchronization-files}

介绍用于基于文件的ID同步的必填字段、语法和命名约定。根据这些规范命名和组织文件内容。

>[!NOTE]
>
>文本样式（`monospaced text`、*斜体*、括号 `[ ]` `( )` 等）本文档中提供了代码元素和选项。请参阅[代码和文本元素的样式约定](../../../reference/code-style-elements.md)，以了解更多信息。

## 文件名语法和示例 {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

ID文件名包含以下必需和可选元素：

`adobe_id_`*`[c2c_id_]`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>将文件标识为ID同步文件的静态前缀。在将设备ID与其他设备ID或客户ID(DPUUID)匹配时使用此前缀。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_ id</code> </p> </td> 
   <td colname="col2"> <p>一个静态前缀，它将文件标识为基于People的目标的ID同步文件。在匹配客户ID(DpuUID)时使用此前缀可为基于People的目标散列电子邮件地址。  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTEDPID</i></code> </td> 
   <td colname="col2"> 主数据提供者ID是文件名中DPID的父ID。此外，数据文件中的第一个用户ID与主ID相对应。后续的DPID是属于主的其他标识符。同步将文件名中的DPID映射到文件中的UUID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>数据提供者ID。这些ID代表与主DPID相关联的实体或数据源。同步将文件名中的DPID映射到文件中的UUID。 </p> <p>文件名中DPID的数量必须与数据文件中的UUID数匹配。例如，您的文件名包含主DPID和3DPII。您的数据文件必须包含个对应的UUID列，如下面的文件内容部分所述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>10秒，UNIX时间戳。时间戳有助于使每个文件名唯一。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . synchronization</code> </p> </td> 
   <td colname="col2"> <p>表示正常的完全同步。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. SIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>整数。将大文件拆分为多个较小文件时使用。这有助于改善处理时间。数字指示您要发送的原始文件的哪部分。请参阅下面的文件名示例。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>指定使用可选的gzip压缩压缩文件。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 文件名示例

以下示例显示格式化正确的文件名称。您的文件名可能类似。

<ul class="simplelist"> 
 <li> <code> adobe_ id_111_222_333_444_1454444149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> 对于基于人员的目标的ID同步文件命名(c2c前缀)，请参阅 [工作流A-基于与脱机数据](../../../features/destinations/people-based-destinations-workflow-combined.md) 组合的所有在线活动或 [工作流B-基于仅脱机数据的个性化](../../../features/destinations/people-based-destinations-workflow-offline.md)。

## 文件内容语法和示例 {#file-content-syntax}

ID文件的内容包括以下元素：

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

文件包含用户ID([!DNL UUID])。在每行中，将ID与选项卡分开。以下示例显示了格式正确的ID文件。您的内容可能类似。

```
abc123 def456 ghi789 xyz987
```

## 同步将DPuID与UUID匹配 {#sync-matches-dpuuids-uuids}

ID同步文件的目的是将您自己的数据源中的 [DPUUID](../../../reference/ids-in-aam.md) 与 [!DNL Audience Manager] UUID同步。同步映射 [!DNL DPUUID]s从主视图 [!DNL DPID] 到s与 [!DNL DPID][!DNL Audience Manager][!DNL UUID]s相关。您将ID放入文件名中的位置决定了这些标识符之间的映射方式。例如，使用下面显示的两个示例文件：

* **文件1：**`adobe_id_0_12345_1476312152.sync`

* **文件2：**`adobe_id_12345_67890_1476312876.sync`

<br/>

给定示例名称和内容时，ID如下图所示：

**文件1** ( [下载示例文件](assets/adobe_id_0_12345_1476312152.sync))

| DPID0= Adobe Audience Manager UI | DPID12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2KzkToKfyAagwaJoshWAjXL-TtrJ6 E4 NJamr38 |
| 67412682083411995725538770443620307584 | XYZ3017BBLR4DafjWFM6D4Gb4Lln_ T5jk_ f7Rdecqns9WFNA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryID8CzFKee-GE034 LI-53Jde0 UDcyCivD0 A2 OLM |
| 66552757407517449462805881945288602094 | XYZ3017QVBdDD-BlJS28 dpXXQfmxXFxe3_55 BVQJMLRegu2 M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60KuhpCa_ ek-BtCN2 iu1 iVaAuto0 d412zbyCmd |

步骤1：ID同步过程会将 [!DNL DPUUID]s从 [!DNL DPID] 12345与左侧列中的 [!DNL Audience Manager][!DNL UUID]s同步。请注意，文件名中 [!DNL DPID] 的“0”表示 [!DNL Audience Manager][!DNL UUID]s。<br/>


**文件2** ( [下载示例文件](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2KzkToKfyAagwaJoshWAjXL-TtrJ6 E4 NJamr38 | 4598060374 |
| XYZ3017BBLR4DafjWFM6D4Gb4Lln_ T5jk_ f7Rdecqns9WFNA7h70 | 4581274262 |
| XYZ3017PryID8CzFKee-GE034 LI-53Jde0 UDcyCivD0 A2 OLM | 4392434426 |
| XYZ3017QVBdDD-BlJS28 dpXXQfmxXFxe3_55 BVQJMLRegu2 M | 2351382994 |
| XYZ3017q9r60KuhpCa_ ek-BtCN2 iu1 iVaAuto0 d412zbyCmd | 4601584763 |

步骤2： [!DNL DPUUID]s from [!DNL DPID] 12345已在Audience Manager [!DNL UUID]的步骤中进行同步。此ID同步的用途是将 [!DNL DPUUID]s从 [!DNL DPID] 67890同步到Audience Manager中的Audience Manager [!DNL UUID]。

<br/>

## 其他格式要求 {#other-format-reqs}

用户ID不能：

* 在ID本身中具有选项卡。选项卡仅用于在数据文件中分离单独的ID。
* 包含个人可识别信息([!UICONTROL PII])。
* 使用 [!DNL URL] 编码。仅传入未编码的ID。

任何以选项卡或空格结尾的行都不会进行处理或识别。作为规则，请确保清晰地保持行的结尾。