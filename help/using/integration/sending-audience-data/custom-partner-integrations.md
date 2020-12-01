---
description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-title: 自定义合作伙伴集成
solution: Audience Manager
title: 自定义合作伙伴集成
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 22%

---


# 自定义合作伙伴集成 {#custom-partner-integrations}

此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。

## Oracle数据云{#oracle-data-cloud}

### 描述

Audience Manager 通过入站数据文件从 Oracle Data Cloud for Audience Marketplace 中提取 Cookie 和移动 ID 数据。下面描述的自定义集成规范只涉及包含移动ID（IDFA和Android设备ID）的入站数据文件。

### 集成特点

从Oracle数据云接收的入站数据文件与[AmazonS3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)中描述的标准入站文件名语法和[入站数据文件内容中描述的标准入站文件内容语法不同：语法、无效字符、变量和示例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

除入站数据文件的标准实施字段外，还需要以下突出显示的元素。 有关所有其他标准字段和文件名元素的说明，请参阅以上链接的两页中的文件名语法和文件内容语法。

### 文件命名

ODC文件名的结构如下：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

`odc`文件名元素将文件标识为从Oracle数据云导入，并指示Audience Manager入站文件验证程序进行相应处理。

### 文件内容

ODC入站数据文件中的字段必须按如下顺序显示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type`可以是：

* IDFA
* Android设备ID

>[!IMPORTANT]
>
>请勿在同一入站数据文件中发送IDFA和Android设备ID。

## 入站ODC示例文件

下载[示例文件](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)。 此文件为特征ID 38838限定了多个IDFA。 您可以在标准文本编辑器或代码编辑器中打开此文件。