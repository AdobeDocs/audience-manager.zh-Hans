---
description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-title: 自定义合作伙伴集成
solution: Audience Manager
title: 自定义合作伙伴集成
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。

## Oracle Data Cloud {#oracle-data-cloud}

**描述**

Audience Manager 通过入站数据文件从 Oracle Data Cloud for Audience Marketplace 中提取 Cookie 和移动 ID 数据。以下自定义集成规范只涉及包含移动ID的入站数据文件(IDFA和Android设备ID)。

<br> 

**集成特定信息**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

除了入站数据文件的标准实施字段外，以下突出显示了以下元素。有关所有其他标准字段和文件名元素的说明，请参阅以上链接的两个页面中的文件名语法和文件内容语法。

<br> 

**文件命名**

OCR文件名构造为：

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

`odc` 文件名元素将文件标识为从Oracle Data Cloud导入，并指示Audience Manager入站文件验证程序处理该文件。

<br> 

**文件内容**

ODC入站数据文件中的字段必须按照以下顺序显示：

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

The `ID type` can be:

* IDFA
* Android设备ID

>[!IMPORTANT]
>
>请勿在同一个入站数据文件中发送IDFA和Android设备ID。

<br> 

**OCR入站文件示例**

Download the [sample file](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). 此文件符合特征ID38838的多个IDFA条件。您可以在标准文本编辑器或代码编辑器中打开此文件。