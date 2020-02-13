---
description: 作为选项，您可以在将数据文件发送到Audience manager时使用PGP加密来加密它们。
seo-description: 作为选项，您可以在将数据文件发送到Audience manager时使用PGP加密来加密它们。
seo-title: 入站数据类型的文件PGP加密
solution: Audience Manager
title: 入站数据类型的文件PGP加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: b2e0b560a944f2ad63a48476be647f1355712342

---


# 入站数据类型的文件PGP加密{#file-pgp-encryption-for-inbound-data-types}

在将数据文件发送到Audience manager时， [!DNL PGP] 可以使用加密方式加密数据文件。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 加密包括文件压缩。 发送加 [!DNL PGP] 密的入站文件时，请确保不使用 [gzip](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) ()压缩`.gz`它们。
>
>[!DNL PGP] 在Audience Manager中，也经过压缩 [的加密](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 入站文件无效。

请按照以下步骤加密入站数据文件。

1. 下载 [Audience manager公钥](./assets/adobe_pgp.pub)。
2. 将公钥导入受信任的商店。

   例如，如果您使 [!DNL GPG]用，该命令可能类似于以下内容：

   `gpg --import adobe_pgp.pub`

3. 通过运行以下命令验证密钥是否已正确导入：

   `gpg --list-keys`

   您应当看到一条与以下内容类似的消息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 使用以下命令加密入站数据：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密的数 `.pgp` 据必须 `.gpg` 使用或作为文件扩展名(例如 `ftp_dpm_100_123456789.sync.pgp` 或 `ftp_dpm_100_123456789.overwrite.gpg`)。

   >[!NOTE]
   >
   >Audience manager仅支持数 [!DNL Advanced Encryption Standard (AES)] 据加密算法。 Audience manager支持任何关键大小。
