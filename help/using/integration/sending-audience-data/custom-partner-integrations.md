---
description: 此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: 自定义合作伙伴集成
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 15%

---

# 自定义合作伙伴集成 {#custom-partner-integrations}

此页面列出了 Audience Manager 与数据合作伙伴之间的自定义集成。

## Oracle Data Cloud {#oracle-data-cloud}

### 描述

Audience Manager 通过入站数据文件从 Oracle Data Cloud for Audience Marketplace 中提取 Cookie 和移动 ID 数据。下述自定义集成规范仅适用于包含移动ID(IDFA和Android设备ID)的入站数据文件。

### 集成详情

从Oracle Data Cloud接收的入站数据文件与[Amazon S3入站数据文件的名称和文件大小要求](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)中所述的标准入站文件名语法不同，也与[入站数据文件内容中所述的标准入站文件内容语法不同：语法、无效字符、变量和示例](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)。

除了入站数据文件的标准实施字段之外，还需要以下高亮显示的元素。 有关所有其他标准字段和文件名元素的说明，请参阅上面链接的两个页面中的“文件名语法”和“文件内容语法”。

### 文件命名

ODC文件名的结构如下：

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

`odc`文件名元素将文件标识为从Oracle Data Cloud导入，并指示Audience Manager入站文件验证器按原样处理文件。

### 文件内容

ODC入站数据文件中的字段必须按如下顺序显示：

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type`可以是：

* IDFA
* Android设备ID

>[!IMPORTANT]
>
>请勿在同一个入站数据文件中发送IDFA和Android设备ID。

## 示例ODC入站文件

下载[示例文件](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)。 此文件使特征ID38838数符合多个IDFA的条件。 您可以在标准文本编辑器或代码编辑器中打开此文件。
