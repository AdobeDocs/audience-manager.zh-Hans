---
description: Audience manager非常重视数据安全和隐私问题。 我们努力保护我们的系统的安全并保护您的宝贵数据。
seo-description: Audience manager非常重视数据安全和隐私问题。 我们努力保护我们的系统的安全并保护您的宝贵数据。
seo-title: 数据安全
solution: Audience Manager
title: 数据安全
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 91444ad943fcd020c83e522922d67ef400bf8824

---


# 数据安全 {#data-security}

Audience manager非常重视数据安全和隐私问题。 我们努力保护我们的系统的安全并保护您的宝贵数据。

Audience manager的安全实践包括外部和内部审计、活动记录、培训以及旨在帮助保护我们的系统和您的宝贵数据的其他程序。 我们相信，安全的产品有助于建立和维护客户对我们的信任。

在Audience Manager中，我们考虑了以下三个主要类别的安全性：

| 安全类型 | 支持 |
|---|---|
| **信息安全** | 企业级身份验证、加密和数据存储实践 |
| **数据泄漏／透明度** | 深入、可操作地了解构成或导致数据泄露的现场活动 |
| **流程／策略增强** | 客户，通过与隐私和数据安全方面的行业最佳实践合作 |

## 系统、培训和访问 {#systems-training-access}

有助于保护系统和数据安全的流程。

**** 外部安全性验证： Audience manager每年和每季度测试安全性。

* 每年：Audience manager每年进行一次由独立第三方公司进行的全面渗透测试。 该测试旨在识别应用程序中的安全漏洞。 这些测试包括扫描跨站点脚本、SQL注入、表单参数处理和其他应用程序级漏洞。
* 季度：每季度一次，内部团队会检查安全漏洞。 这些测试包括网络扫描打开的端口和服务漏洞。

**** 系统安全： 为帮助保护数据安全和私有，Audience Manager:

* Blocks requests from unauthorized IP addresses.
* Protects data behind firewalls, VPNs, and with Virtual Private Cloud storage.
* Tracks changes in the customer and control-information databases with trigger-based audit logging. These logs track all changes at the database level, including the user ID and IP address from which changes are made.

**Security Assets:**  Audience Manager has a dedicated network operations team that monitors firewalls and intrusion-detection devices. Only key personnel have access to our security technology and data.

**** 安全培训： 在内部，我们对安全性的承诺延伸到负责我们产品的开发人员。 Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. IP地址用于数据处理和日志聚合过程。 地理／位置查找和定位也需要它们。 此外，保留的日志文件中的所有IP地址在90天内都会被模糊处理。

## 数据分区 {#data-partitioning}

有助于保护个别客户拥有的数据的流程。

**** 特征数据分区： 您的数据（特征、ID等）由客户端划分。 这有助于防止不同客户端之间的意外信息泄露。 例如，Cookie中的特征数据由客户划分并存储在特定于客户的子域中。 其他Audience manager客户端不能读取或意外使用它。 此外，存储在该特征数据中的特征数 [!UICONTROL Profile Cache Servers (PCS)] 据也由客户进行分区。 这样可以防止其他客户在事件调用或其他请求中意外使用您的数据。

**** 报告中的数据分区： 客户端ID是所有报表表中标识键的一部分，报表查询按ID进行过滤。 这有助于防止您的数据显示在其他Audience manager客户的报告中。

## 入站服务器到服务器(S2S)传输 {#inbound-s2s}

Adobe Audience manager支持两种将已载入的S2S数据文件传输到我们系统的主要方法：

这两种方法的设计都考虑到了客户和合作伙伴数据的安全性，同时数据在他们的系统和系统之间传输。

**** SFTP:对于SFTP选项，大多数客户选择通过使用安全外壳(SSH)协议的安全FTP(SFTP)协议传送文件。 此方法可确保在客户系统与Adobe系统之间传输时对文件进行加密。 对于每位客户，我们在SFTP服务器上创建一个被监禁的下拉框位置，该位置与该系统上的用户帐户绑定。 只有客户的有凭据且拥有特权的内部系统用户才能访问此被监禁的下拉框位置。 这座牢房永远无法供其他客户使用。

**** 通过HTTPS的Amazon Web Services S3:对于S3交付选项，我们建议所有客户配置其S3客户端，以使用HTTPS加密方法进行文件传输（这不是默认设置，因此必须显式配置它）。 s3cmd命令行工具以及每种主要编程语言中可用的S3库都支持HTTPS选项。 启用此HTTPS选项后，客户在飞到我们的系统时的数据将加密。 For each customer, we create a separate S3 bucket sub-directory that can be accessed only by that customer's credentials and those of our internal system users.

要向数据文件添加PGP加密，请参阅 [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。

## 通过逃逸保护数据 {#escaping-data}

请注意， [!DNL Audience Manager] 不会转义传出数据，以保护其免受可能的跨站点脚本(XSS)等攻击。 客户端有责任逃避传入的数据。

## HTTP Strict-Transport-Security (#hsts)

[!DNL HTTP Strict-Transport-Security (HSTS)] is a web security policy mechanism that helps protect against cookie hijacking and protocol downgrade attacks by not permitting  traffic and transparently upgrading all  traffic to .[!DNL HTTP][!DNL HTTP][!DNL HTTPS]

This policy improves data security between clients and Adobe Edge servers.

### 示例 {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
