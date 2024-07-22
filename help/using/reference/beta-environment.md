---
description: 测试版环境用于测试您的Audience Manager实施。 在Beta版中所做的更改不会影响生产数据。 如果您有兴趣使用测试版环境，请联系您的Audience Manager合作伙伴解决方案代表。
keywords: 沙盒
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta环境
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Beta环境 {#beta-environment}

测试版环境用于测试您的Audience Manager实施。 在Beta版中所做的更改不会影响生产数据。 如果您有兴趣使用测试版环境，请联系您的Audience Manager合作伙伴解决方案代表。

## 概述

bveta环境中的功能是生产环境的精确副本，没有任何实验性或未发布的功能。 您在生产环境中的登录凭据在测试版环境中有效。

**更新计划**

Beta环境会在每月末的非高峰时段更新。

>[!IMPORTANT]
>
>请注意，您的客户数据（[信号、特征和区段](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en)）未在生产环境和测试版环境之间同步。

## 入站流量

测试版环境仅支持用于验证文件名和内容语法的入站流量。 由于测试版环境中不会进行ID映射，因此客户不会看到任何区段人口。

因此，在Beta版环境中摄取文件时，[!UICONTROL Onboarding Status]页面将始终报告[!UICONTROL No matching AAM ID]。

我们建议所有客户在其生产环境中执行任何入站测试。

## 出站流量

未为测试版环境启用出站流量。

## 端点

| 服务 | URL/主机名 | 如何获取访问权限 |
|--- |--- | --- |
| S3 | 请联系您的Audience Manager合作伙伴解决方案代表或客户关怀 | 请联系您的Audience Manager合作伙伴解决方案代表或客户关怀团队，为您的测试版实例设置Amazon S3存储段。 阅读有关使用Amazon S3](../reference/amazon-s3.md)的[优势的信息。 |
| DCS | `https://dcs-beta.demdex.net/...` | 请参阅[在Beta环境中访问DCS](../reference/beta-environment.md#access-dcs-beta-environment)。 |
| 用户界面 | `https://bank-beta.demdex.com` | 您的生产环境凭据对测试版环境有效。 |
| API | `https://api-beta.demdex.com/...` | 您的生产环境凭据对测试版环境有效。 我们建议您创建通用API用户，[查看详细信息](../api/rest-api-main/aam-api-getting-started.md#requirements)。 |

## 在Beta环境中访问DCS {#access-dcs-beta-environment}

1. 使用curl [命令](https://curl.haxx.se/docs/manpage.html)进行DCS调用。 Curl是一种使用多种支持的协议之一，将数据从服务器传输到服务器的工具。

   例如：

   `curl -v https://dcs-beta.demdex.net/event`

1. 通过在DCS响应标头中查找“sandbox”，验证测试版DCS是否提供了您的请求。

   例如：

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->
