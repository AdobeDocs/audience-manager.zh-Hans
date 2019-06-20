---
description: Audience Manager非常重视数据安全和隐私。我们努力确保系统安全，保护您的宝贵数据。
seo-description: Audience Manager非常重视数据安全和隐私。我们努力确保系统安全，保护您的宝贵数据。
seo-title: 数据安全性
solution: Audience Manager
title: 数据安全性
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

Audience Manager非常重视数据安全和隐私。我们努力确保系统安全，保护您的宝贵数据。

Audience Manager的安全实践包括外部和内部审计、活动记录、培训和其他旨在帮助保护我们的系统和宝贵数据的程序。我们相信安全的产品有助于建立和维护信任客户的地点。

在Audience Manager中，我们考虑三个主要类别的安全性：

| 安全类型 | 提供对支持 |
|---|---|
| **信息安全性** | 企业级身份验证、加密和数据存储实践 |
| **数据泄露/透明度** | 深入了解构成或促进数据泄漏的现场活动 |
| **流程/策略增强** | 客户通过使用业界最佳隐私和数据安全实践 |

## Systems, Training, and Access {#systems-training-access}

有助于保持系统和数据安全的流程。

**外部安全验证：** Audience Manager按年和每季度测试安全性。

* 每年：Audience Manager一年完成一次由独立第三方公司完成的完全渗透测试。该测试旨在识别应用程序中的安全漏洞。测试包括扫描跨站点脚本、SQL集成、表单参数操作和其他应用程序级漏洞。
* 季度：每个季度一次，内部团队就会检查安全漏洞。这些测试包括用于打开端口和服务漏洞的网络扫描。

**Systems Security：** 为使数据保持安全和私密，Audience Manager：

* 阻止未经授权的IP地址的请求。
* 保护防火墙、VPN和虚拟专用云存储背后的数据。
* 使用基于触发器的审计日志记录跟踪客户和控制信息数据库中的更改。这些日志跟踪数据库级别的所有更改，包括进行更改的用户ID和IP地址。

**安全资产：** Audience Manager有一个专门的网络运营团队，用于监视防火墙和入侵检测设备。只有关键人员才能访问我们的安全技术和数据。

**安全培训：** 在内部，我们对安全的承诺延伸到使用我们产品的开发人员。Adobe为开发人员提供如何构建安全应用程序和服务的正式培训。

**安全访问：** Audience Manager需要强口令才能登录到系统。See [password requirements](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

有助于保护个人信息安全的流程。For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**PII数据：** Audience Manager实质上禁止客户和数据合作伙伴将PII信息发送到我们的系统。此外，唯一用户ID(UUID)不包含或使用PII数据作为ID生成算法的一部分。

**IP地址：** Audience Manager会收集IP地址。IP地址用于数据处理和日志聚集过程。地理位置/位置查找和定位也需要它们。此外，保留日志文件内的所有IP地址在90天内都会模糊化。

## Data Partitioning {#data-partitioning}

有助于保护各个客户拥有的数据的流程。

**特征数据分区：** 您的数据(特征、ID等)由客户端划分。这有助于防止在不同客户端之间意外暴露信息。例如，cookie中的特征数据由客户划分，并存储在特定于客户端的子域中。其他Audience Manager客户端不能意外读取或使用它。Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. 这可防止其他客户端在事件调用或其他请求中意外使用您的数据。

**报表中的数据分区：** 客户端ID是所有报告表和报告查询中标识键的一部分，按ID筛选查询。这有助于防止数据出现在其他Audience Manager客户的报告中。

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager支持将S2S随附数据文件传输到我们的系统的两种主要方法：

这两种方法都是考虑客户和合作伙伴数据的安全性，同时数据在系统和系统之间处于飞行阶段。

**SFTP：** 对于SFTP选项，大多数客户选择通过安全FTP(SFTP)协议交付文件，该协议使用Secure Shell(SSH)协议。此方法确保文件在客户系统与Adobe系统之间飞行时经过加密。对于每个客户，我们在我们的SFTP服务器上创建一个已通过jmail的拖放框位置，该位置绑定到该系统上的某个用户帐户。只有客户的信用授权和特权内部系统用户才能访问此已通过japed的拖放框。其他客户无法访问此监狱。

**Amazon Web Services S通过HTTPS：** 对于S传送选项，我们建议所有客户将其S客户端配置为使用HTTPS加密方法进行文件传输(这不是默认值，因此必须显式配置)。s3cmd命令行工具以及每个主要编程语言中提供的S库都支持HTTPS选项。启用此HTTPS选项后，客户的数据在进入我们的系统时经过加密。对于每个客户，我们创建一个单独的S罐子目录，仅可由该客户凭据和我们内部系统用户的凭据访问。

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. 客户负责逃脱接收的数据。
