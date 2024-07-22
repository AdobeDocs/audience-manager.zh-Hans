---
description: 作为一个选项，您可以在将数据文件发送到Audience Manager时对其进行加密，这使用PGP加密。
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: 入站数据类型的文件PGP加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# 入站数据类型的文件PGP加密{#file-pgp-encryption-for-inbound-data-types}

在将数据文件发送到Audience Manager时，您可以使用[!DNL PGP]加密来加密数据文件。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP]加密包含文件压缩。 发送[!DNL PGP]加密入站文件时，请确保不使用gzip (`.gz`)压缩[它们](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)。
>
>[!DNL PGP]加密的入站文件（也是[压缩的](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)）在Audience Manager中无效。

按照下面列出的步骤加密入站数据文件。

1. 下载[Audience Manager公钥](./assets/adobe_pgp.pub)。
2. 将公钥导入到可信存储中。

   例如，如果您使用[!DNL GPG]，则命令可能类似于以下内容：

   `gpg --import adobe_pgp.pub`

3. 通过运行以下命令验证是否已正确导入密钥：

   `gpg --list-keys`

   您应会看到一条与以下内容类似的消息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 使用以下命令加密入站数据：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密数据必须使用`.pgp`或`.gpg`作为文件扩展名（例如`ftp_dpm_100_123456789.sync.pgp`或`ftp_dpm_100_123456789.overwrite.gpg`）。

   >[!NOTE]
   >
   >Audience Manager仅支持[!DNL Advanced Encryption Standard (AES)]数据加密算法。 Audience Manager支持任何键大小。
