---
description: 作为一种选项，在将数据文件发送到Audience Manager时，可以使用PGP加密来加密数据文件。
seo-description: 作为一种选项，在将数据文件发送到Audience Manager时，可以使用PGP加密来加密数据文件。
seo-title: 入站数据类型的文件 PGP 加密
solution: Audience Manager
title: 入站数据类型的文件 PGP 加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 11%

---


# 入站数据类型的文件 PGP 加密{#file-pgp-encryption-for-inbound-data-types}

在将数据文件发送到Audience Manager时， [!DNL PGP] 可以使用加密方式对数据文件进行加密。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 加密包括文件压缩。 发送加 [!DNL PGP] 密的入站文件时，请确保不 [使用](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) gzip()压`.gz`缩它们。
>
>[!DNL PGP] 经过压缩的已加密入站 [文件](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) ，在Audience Manager中无效。

请按照以下步骤加密入站数据文件。

1. 下载 [Audience Manager公钥](./assets/adobe_pgp.pub)。
2. 将公钥导入信任的商店。

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

   所有加密数据 `.pgp` 必须 `.gpg` 使用或作为文件扩展名( `ftp_dpm_100_123456789.sync.pgp` 如或 `ftp_dpm_100_123456789.overwrite.gpg`)。

   >[!NOTE]
   >
   >Audience Manager仅支持 [!DNL Advanced Encryption Standard (AES)] 数据加密算法。 Audience Manager支持任何密钥大小。
