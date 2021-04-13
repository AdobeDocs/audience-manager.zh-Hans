---
description: 测试版环境用于测试Audience Manager实施。 测试版中所做的更改不会影响生产数据。 如果您对使用测试版环境感兴趣，请与Audience Manager合作伙伴解决方案代表联系。
keywords: 沙箱
seo-description: 测试版环境用于测试Audience Manager实施。 测试版中所做的更改不会影响生产数据。 如果您对使用测试版环境感兴趣，请与Audience Manager合作伙伴解决方案代表联系。
seo-title: 测试版环境
solution: Audience Manager
title: 测试版环境
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: 参考
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 4%

---

# 测试版环境 {#beta-environment}

测试版环境用于测试Audience Manager实施。 测试版中所做的更改不会影响生产数据。 如果您对使用测试版环境感兴趣，请与Audience Manager合作伙伴解决方案代表联系。

## 概述

测试版环境是生产环境的精确副本，没有任何试验性或未发布的功能。 您来自生产环境的登录凭据在测试版环境中有效。

**更新计划**

测试版环境在每月末的非高峰时段进行更新。

**出站流量**

测试环境未启用出站流量。

<!-- 

Added re: AAM-30826.

 -->

## 端点



| 服务 | URL/主机名 | 如何获得访问 |
|--- |--- | --- |
| S3 | 联系您的Audience Manager合作伙伴解决方案代表或客户关怀 | 联系您的Audience Manager合作伙伴解决方案代表或客户关怀部门，为测试实例设置Amazon S3存储桶。 了解使用Amazon S3](../reference/amazon-s3.md)的[优势。 |
| DCS | `https://dcs-beta.demdex.net/...` | 请参阅[访问测试版环境](../reference/beta-environment.md#access-dcs-beta-environment)中的DCS。 |
| 用户界面 | `https://bank-beta.demdex.com` | 您的生产环境凭据对测试版环境有效。 |
| API | `https://api-beta.demdex.com/...` | 您的生产环境凭据对测试版环境有效。 我们建议您创建一个通用API用户，[请参阅详细信息](../api/rest-api-main/aam-api-getting-started.md#requirements)。 |

## 访问测试版环境{#access-dcs-beta-environment}中的DCS

1. 使用curl [command](https://curl.haxx.se/docs/manpage.html)进行DCS调用。 Curl是使用多种支持的协议之一从服务器传输数据或将数据传输到服务器的工具。

   例如：

   `curl -v https://dcs-beta.demdex.net/event`

1. 通过在DCS响应标头中查找“沙箱”，验证测试版DCS是否提供了您的请求。

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
