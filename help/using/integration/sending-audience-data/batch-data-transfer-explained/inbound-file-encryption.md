---
description: 作为选项，您可以在将数据文件发送到Audience manager时使用PGP加密来加密它们。
seo-description: 作为选项，您可以在将数据文件发送到Audience manager时使用PGP加密来加密它们。
seo-title: 入站数据类型的文件PGP加密
solution: Audience Manager
title: 入站数据类型的文件PGP加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 入站数据类型的文件PGP加密{#file-pgp-encryption-for-inbound-data-types}

作为选项，您可以在将数据文件发送到Audience Manager时 [!DNL PGP] 使用加密技术对它们进行加密。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>我们目前不支持对同一个入站数据文件进行加密和压缩。 您可以选择加密或压 [缩入站](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 文件。

请按照以下步骤加密入站数据文件。

1. 下载 [Audience manager公钥](./assets/adobe_pgp.pub)。
1. 将公钥导入受信任的商店。

   例如，如果您使 [!DNL GPG]用，该命令可能类似于以下内容：

   `gpg --import adobe_pgp.pub`

1. 通过运行以下命令验证密钥是否已正确导入：

   `gpg --list-keys`

   您应当看到一条与以下内容类似的消息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. 使用以下命令加密入站数据：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密的数 `.pgp` 据必须 `.gpg` 使用或作为文件扩展名(例如 `ftp_dpm_100_123456789.sync.pgp` 或 `ftp_dpm_100_123456789.overwrite.gpg`)。

   >[!NOTE]
   >
   >Audience manager仅支持数 [!DNL Advanced Encryption Standard (AES)] 据加密算法。 Audience manager支持任何关键大小。