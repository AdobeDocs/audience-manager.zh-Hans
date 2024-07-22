---
description: Audience Manager 非常重视数据安全和隐私。我们竭力保障系统安全，为您的宝贵数据保驾护航。
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Data Security in Audience Manager
solution: Audience Manager
title: Audience Manager 中的数据安全
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: Data Governance & Privacy
exl-id: 94b70250-dca3-4c50-b4dd-bc37178a587e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 92%

---

# Audience Manager 中的数据安全 {#data-security}

Audience Manager 非常重视数据安全和隐私。我们竭力保障系统安全，为您的宝贵数据保驾护航。

为保障安全，Audience Manager 采取了很多措施，包括外部和内部审计、活动日志记录、培训，以及旨在帮助保护系统和客户宝贵数据的其他程序。我们坚信，安全的产品有助于建立和维护客户对我们的信任。

在 Audience Manager 中，我们主要考量以下三个类型的安全事宜：

| 安全类型 | 支持对象 |
|---|---|
| **信息安全** | 企业级身份验证、加密和数据存储实践 |
| **数据泄漏/公开** | 深入了解可构成或引发数据泄露的网站活动，并提供可行的解决措施 |
| **流程/策略改进** | 通过采用有助于保护隐私和数据安全的行业最佳做法，为客户提供支持 |

## 系统、培训和访问 {#systems-training-access}

有助于确保系统和数据安全的流程。

**外部安全验证：** Audience Manager 开展年度安全测试和季度安全测试。

* 年度测试：Audience Manager 每年聘请独立的第三方公司开展一次全面渗透测试。该测试旨在识别应用程序存在的安全漏洞。测试内容包括扫描跨站点脚本、SQL 注入、表单参数操纵和其他应用程序级安全漏洞。
* 季度测试：内部团队每季度开展一次安全漏洞排查。测试内容包括进行网络扫描以查找打开的端口和服务漏洞。

**系统安全：**&#x200B;为帮助保护数据安全和隐私，Audience Manager 将：

* 阻止来自未授权 IP 地址的请求。
* 保护防火墙和 VPN 后面的数据以及使用虚拟私有云存储的数据。
* 使用基于触发器的审计日志跟踪客户数据库和控制信息数据库中发生的更改。这些日志将跟踪数据库级别的所有更改，包括从中进行更改的用户 ID 和 IP 地址。

**安全资产**：Audience Manager 专门组建了一个负责监视防火墙和入侵检测设备的网络运营团队。只有核心人员才有权访问我们的安全技术和数据。

**安全培训：**&#x200B;在内部，我们对安全的承诺延伸到产品开发人员。Adobe 为开发人员提供有关如何构建安全应用程序和服务的正式培训。

**安全访问：** Audience Manager 要求用户使用强密码登录到系统。请参阅[密码要求](../../reference/password-requirements.md)。

## 隐私和个人身份信息(PII) {#pii}

有助于保护个人信息安全的流程。欲了解有关隐私保护的更多信息，请参阅 [Adobe 隐私中心](https://www.adobe.com/cn/privacy/advertising-services.html)。

**PII 数据：** Audience Manager 将依照合同规定禁止客户和数据合作伙伴将 PII 信息发送到我们的系统。此外，独特用户 ID (UUID) 不包含 PII 数据，也不会将 PII 数据用于 ID 生成算法。

**IP 地址：** Audience Manager 会收集 IP 地址。在数据处理和日志汇总过程中会使用 IP 地址。在查找地理位置和定位时也需要使用 IP 地址。此外，会在 90 天内对保留的日志文件中的所有 IP 地址进行模糊处理。

## 数据分区 {#data-partitioning}

有助于保护归每个客户所有的数据的流程。

**特征数据分区：**&#x200B;您的数据（[!UICONTROL traits]、ID等） 进行分区。这有助于防止信息在不同客户之间意外泄露。例如，Cookie 中的特征数据将按照客户进行分区并存储在特定于客户的子域中。这样可以防止其他 Audience Manager 客户意外读取或使用这些特征数据。此外，存储在 [!UICONTROL Profile Cache Servers (PCS)] 中的特征数据也是按照客户进行分区的。这样可以防止其他客户在事件调用或其他请求中意外使用您的数据。

**报表中的数据分区：**&#x200B;客户 ID 是所有报表表格中标识键的一部分，报表查询按 ID 进行过滤。这有助于防止您的数据出现在其他 Audience Manager 客户的报表中。

## 入站服务器到服务器(S2S)传输 {#inbound-s2s}

Adobe Audience Manager 主要支持通过以下两种方法将载入的 S2S 数据文件传输到我们的系统：

这两种方法在设计时都考虑到了在客户和合作伙伴的系统与我们的系统之间传输客户和合作伙伴数据时保护数据安全的重要性。

**SFTP：**&#x200B;对于 SFTP 选项，大多数客户都会选择通过使用安全 Shell (SSH) 协议的安全 FTP (SFTP) 协议传送文件。此方法可确保在客户系统与 Adobe 系统之间传输文件时对文件进行加密。我们在 SFTP 服务器上为每位客户都创建一个被保护和监管的文件接收位置，该位置与系统上的用户帐户绑定。只有客户授权的内部系统用户才能访问这个被保护和监管的文件接收位置。其他客户永远无法访问此位置。

通过HTTPS的&#x200B;**[!UICONTROL Amazon Web Services S3]：**&#x200B;对于S3传送选项，我们建议所有客户都将其S3客户端配置为使用HTTPS加密方法进行文件传输（这不是默认设置，因此必须进行明确配置）。 s3cmd 命令行工具以及在每种主要编程语言中均可用的 S3 库都支持此 HTTPS 选项。启用此 HTTPS 选项后，客户数据在传输到我们的系统时会进行加密。我们为每个客户都创建一个单独的 S3 存储段子目录，该子目录只有通过客户的凭据以及我们内部系统用户的凭据才能访问。

要向数据文件添加 PGP 加密，请参阅[适用于入站数据类型的文件 PGP 加密](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)。

## 通过转义保护数据 {#escaping-data}

请注意，为保护传出数据免受跨站点脚本 (XSS) 攻击以及其他攻击，[!DNL Audience Manager] 不会对传出数据进行转义。客户需负责对传入数据进行转义。

## HTTP严格传输安全 {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] 是行业范围的 Web 安全机制，有助于抵御 Cookie 劫持和协议降级攻击。

该策略会向 Web 浏览器下达以下指令：在对给定域发起安全 [!DNL HTTPS] 调用后，应禁止再对该域发起不安全的后续调用 ([!DNL HTTP])。这样可以防止中间人攻击，即攻击者尝试将 [!DNL HTTPS] 调用降级为不安全的 [!DNL HTTP] 调用。

此策略可加强客户端与 Adobe [Edge](../../reference/system-components/components-edge.md) 服务器之间的数据安全性。

### 示例 {#hsts-example}

假设`yourcompany.demdex.com`域通过[!DNL HTTP]向[!DNL DCS]发送流量。 [!DNL HSTS] 会对调用进行升级以改用 [!DNL HTTPS]，而且所有来自 `yourcompany.demdex.com` 的后续 [!DNL DCS] 调用都会使用 [!DNL HTTPS] 而不使用 [!DNL HTTP]。

有关 HSTS 的更多信息，请参阅 [HTTP 严格传输安全 - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)。
