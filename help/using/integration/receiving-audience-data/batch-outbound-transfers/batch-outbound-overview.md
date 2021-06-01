---
description: Audience Manager会根据这些规范向第三方内容提供商发送批量数据。
seo-description: Adobe Audience Manager(AAM)会根据这些规范向第三方内容提供商发送批量数据。
seo-title: 在Adobe Audience Manager中批量传输出站数据(AAM)
title: 批量出站数据传输
feature: 出站数据传输
exl-id: 1fdcc971-3a71-4033-8501-ef3d1f1f0f47
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 17%

---

# 批量出站数据传输

Audience Manager会根据这些规范向第三方内容提供商发送批量数据。

* [出站数据文件名：语法和示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   描述用于命名出站数据文件的必填字段、语法和惯例。

* [配置批量数据传输集成](batch-server-configuration.md)

   介绍配置批量数据传输集成的方法。

* [用于日志文件传输的传输控制文件](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   传输控制(.info)文件提供有关文件传输的元数据信息，以便合作伙伴能够验证Audience Manager是否正确处理了文件传输。

* [出站模板宏](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   列出可用于创建出站模板的宏。 这些宏包括文件名宏、标题宏和内容宏。

* [出站宏示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   有关如何使用某些常用宏创建出站文件模板的示例。

* [利用出站文件的 Amazon S3 跨帐户存储段权限](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   对于使用Amazon Simple Storage Service(Amazon S3)的客户，“出站数据传输”流程要求我们请求您的Amazon S3访问密钥和密钥，以便将出站数据文件交付到存储段。
