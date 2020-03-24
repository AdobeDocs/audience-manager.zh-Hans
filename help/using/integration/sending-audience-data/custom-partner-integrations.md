---
description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-title: 自定义合作伙伴集成
solution: Audience Manager
title: 自定义合作伙伴集成
translation-type: tm+mt
source-git-commit: c069c901df6d8737f611d27ce7dffd4072e50adf

---


# 自定义合作伙伴集成 {#custom-partner-integrations}

此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。

## Oracle Data Cloud {#oracle-data-cloud}

### 描述

Audience Manager 通过入站数据文件从 Oracle Data Cloud for Audience Marketplace 中提取 Cookie 和移动 ID 数据。下面描述的自定义集成规范只涉及包含移动ID（IDFA和Android设备ID）的入站数据文件。

### 集成特定信息

从Oracle Data Cloud接收的入站数据文件与Amazon S3 Name and File Size Requirements for Inbound Data Files [(入站数据文件的](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) Amazon S3名称和文件大小要求)中描述的标准入站文件名语法不同，与Inbound Data File Contents（入站数据文件内容）中描述的标准入站文件内容语法 [不同：语法、无效字符、变量和示例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

除了入站数据文件的标准实施字段外，以下突出显示的元素也是必需的。 有关所有其他标准字段和文件名元素的说明，请参阅上述链接的两个页面中的文件名语法和文件内容语法。

### 文件命名

ODC文件名的结构如下：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

文 `odc` 件名元素将文件标识为从Oracle Data Cloud导入，并指示Audience Manager入站文件验证程序处理该文件。

### 文件内容

ODC入站数据文件中的字段必须按如下顺序显示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

可 `ID type` 以是：

* IDFA
* Android设备ID

>[!IMPORTANT]
>
>请勿在同一入站数据文件中发送IDFA和Android设备ID。

## 示例ODC入站文件

下载 [示例文件](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)。 此文件为特征ID 38838限定了多个IDFA。 您可以在标准文本编辑器或代码编辑器中打开此文件。