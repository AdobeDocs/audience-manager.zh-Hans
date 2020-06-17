---
description: Audience Manager根据这些规范向第三方内容提供商发送批量数据。
seo-description: Adobe Audience Manager(AAM)根据这些规范向第三方内容提供商发送批量数据。
seo-title: Adobe Audience Manager(AAM)中的批量出站数据传输
title: 批量出站数据传输
translation-type: tm+mt
source-git-commit: 1b31f10effa2780b5e4374516dd6c76d92a0123a
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%

---


# 批量出站数据传输

Audience Manager根据这些规范向第三方内容提供商发送批量数据。

* [出站数据文件名： 语法和示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   描述用于命名出站数据文件的必填字段、语法和约定。

* [配置批处理数据传输集成](batch-server-configuration.md)

   介绍配置批处理数据传输集成的方法。

* [日志文件传输的传输控制文件](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   传输控制(.info)文件提供有关文件传输的元数据信息，以便合作伙伴可以验证Audience Manager处理的文件传输是否正确。

* [出站模板宏](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   列表可用于创建出站模板的宏。 这些宏包括文件名宏、标题宏和内容宏。

* [出站宏示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   一些常用宏用于创建出站文件模板的示例。

* [利用您出站文件的 Amazon S3 跨帐户存储段权限](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   对于使用Amazon Simple Data Service(Amazon S3)的存储，客户的出站传输过程要求我们要求您提供Amazon S3访问密钥和密钥，以便将出站数据文件传送到您的存储桶。
