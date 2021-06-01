---
description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-title: 自定义合作伙伴集成
solution: Audience Manager
title: 自定义合作伙伴集成
feature: 第三方集成
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 22%

---

# 自定义合作伙伴集成 {#custom-partner-integrations}

此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。

## Oracle数据云{#oracle-data-cloud}

### 描述

Audience Manager 通过入站数据文件从 Oracle Data Cloud for Audience Marketplace 中提取 Cookie 和移动 ID 数据。下面描述的自定义集成规范仅引用包含移动ID（IDFA和Android设备ID）的入站数据文件。

### 集成详情

从Oracle数据云接收的入站数据文件与[Amazon S3入站数据文件的名称和文件大小要求中描述的标准入站文件名语法不同，而与[入站数据文件内容中描述的标准入站文件内容语法不同：语法、无效字符、变量和示例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

除集客数据文件的标准实施字段外，还需要以下突出显示的元素。 有关所有其他标准字段和文件名元素的说明，请参阅上面链接的两个页面中的“文件名语法”和“文件内容语法”。

### 文件命名

ODC文件名的结构如下：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

`odc`文件名元素将文件标识为从Data Cloud导入的文件，并指示Audience Manager入站文件验证器进行相应处理。

### 文件内容

ODC入站数据文件中的字段必须按以下顺序显示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type`可以是：

* IDFA
* Android设备ID

>[!IMPORTANT]
>
>请勿在同一集客数据文件中发送IDFA和Android设备ID。

## ODC入站文件示例

下载[样例文件](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)。 此文件可使多个IDFA符合特征ID 38838的条件。 您可以在标准文本编辑器或代码编辑器中打开此文件。
