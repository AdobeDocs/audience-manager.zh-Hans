---
description: Audience Manager根据这些规范向第三方内容提供商发送批量数据。
seo-description: Adobe Audience Manager(AAM)根据这些规范向第三方内容提供商发送批量数据。
seo-title: 在Adobe Audience Manager(AAM)进行批量出站数据传输
title: 批量出站数据传输
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 17%

---


# 批量出站数据传输

Audience Manager根据这些规范向第三方内容提供商发送批量数据。

* [出站数据文件名：语法和示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)

   描述用于命名出站数据文件的必填字段、语法和约定。

* [配置批处理数据传输集成](batch-server-configuration.md)

   介绍配置批处理数据传输集成的方法。

* [用于日志文件传输的传输控制文件](/help/using/integration/receiving-audience-data/batch-outbound-transfers/transfer-control-files.md)

   传输控制(.info)文件提供有关文件传输的元数据信息，以便合作伙伴可以验证Audience Manager处理的文件传输是否正确。

* [出站模板宏](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)

   列表可用于创建出站模板的宏。 这些宏包括文件名宏、标题宏和内容宏。

* [出站宏示例](/help/using/integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

   一些常用宏用于创建出站文件模板的示例。

* [利用出站文件的 Amazon S3 跨帐户存储段权限](/help/using/integration/receiving-audience-data/batch-outbound-transfers/authorize-s3-cross-bucket.md)

   对于使用Amazon简单存储服务(AmazonS3)的客户，“出站传输”过程要求我们要求您提供AmazonS3访问密钥和密钥，以便将出站数据文件传送到您的存储桶。
