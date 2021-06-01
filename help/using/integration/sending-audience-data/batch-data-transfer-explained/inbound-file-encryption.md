---
description: 作为一个选项，在将数据文件发送到Audience Manager时，可以使用PGP加密来加密数据文件。
seo-description: 作为一个选项，在将数据文件发送到Audience Manager时，可以使用PGP加密来加密数据文件。
seo-title: 入站数据类型的文件 PGP 加密
solution: Audience Manager
title: 入站数据类型的文件 PGP 加密
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: 入站数据传输
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 12%

---

# 入站数据类型的文件 PGP 加密{#file-pgp-encryption-for-inbound-data-types}

在将数据文件发送到Audience Manager时，可以使用[!DNL PGP]加密来加密它们。

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 加密包括文件压缩。发送[!DNL PGP]加密的入站文件时，请确保不要[使用gzip(`.gz`)压缩](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)这些文件。
>
>[!DNL PGP] 加密的入站文件在Audience Manager [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 中也压缩无效。

请按照以下所述步骤加密入站数据文件。

1. 下载[Audience Manager公钥](./assets/adobe_pgp.pub)。
2. 将公共密钥导入受信任的存储。

   例如，如果使用[!DNL GPG]，则命令可能类似于以下内容：

   `gpg --import adobe_pgp.pub`

3. 通过运行以下命令验证密钥是否已正确导入：

   `gpg --list-keys`

   您应会看到与以下内容类似的消息：

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 使用以下命令加密入站数据：

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   所有加密数据都必须使用`.pgp`或`.gpg`作为文件扩展名(例如，`ftp_dpm_100_123456789.sync.pgp`或`ftp_dpm_100_123456789.overwrite.gpg`)。

   >[!NOTE]
   >
   >Audience Manager仅支持[!DNL Advanced Encryption Standard (AES)]数据加密算法。 Audience Manager支持任何键大小。
