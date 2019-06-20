---
description: 作为一个选项，您可以在将数据文件发送到Audience Manager时使用PGP加密加密数据文件。
seo-description: 作为一个选项，您可以在将数据文件发送到Audience Manager时使用PGP加密加密数据文件。
seo-title: 入站数据类型的文件PGP加密
solution: Audience Manager
title: 入站数据类型的文件PGP加密
uuid: 89catch1-0259-48fc-865b-d525 ec7822 f7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>我们当前不支持在同一个入站数据文件上进行加密和压缩。You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

请按照以下步骤加密入站数据文件。

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
1. 将公钥导入受信任的商店。

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. 通过运行以下命令，验证已正确导入密钥：

   `gpg --list-keys`

   您应当看到一条类似于以下内容的消息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. 使用以下命令加密入站数据：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager支持任何密钥大小。