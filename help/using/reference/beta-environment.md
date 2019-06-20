---
description: Beta环境用于测试Audience Manager实施。测试版中所做的更改不会影响生产数据。如果您希望使用Beta环境，请与Audience Manager合作伙伴解决方案代表联系。
keywords: sandbox
seo-description: Beta环境用于测试Audience Manager实施。测试版中所做的更改不会影响生产数据。如果您希望使用Beta环境，请与Audience Manager合作伙伴解决方案代表联系。
seo-title: 测试版环境
solution: Audience Manager
title: 测试版环境
uuid: de4a1a46-cfa4-4f64-8569-48a7650 fd8 cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# 测试版环境 {#beta-environment}

Beta环境用于测试Audience Manager实施。测试版中所做的更改不会影响生产数据。如果您希望使用Beta环境，请与Audience Manager合作伙伴解决方案代表联系。

## 概述

Beta环境是制作环境的精确副本，无需任何实验或未释放的功能。生产环境中的登录凭据在测试环境中有效。

**更新计划**

Beta环境将在高峰期结束时每个月结束。

**出站流量**

测试版环境中未启用出站流量。

<!-- 

Added re: AAM-30826.

 -->

## 端点



| 服务 | URL/主机名 | 如何获取访问权限 |
|--- |--- | --- |
| S3 | 联系Audience Manager合作伙伴解决方案代表或客户关怀 | 请与Audience Manager合作伙伴解决方案代表或客户关怀部门联系，为您的Beta实例设置Amazon S桶。Read about the [advantages of using Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | See [Accessing the DCS in the Beta Environment](../reference/beta-environment.md#access-dcs-beta-environment). |
| 用户界面 | `https://bank-beta.demdex.com` | 您的生产环境凭据对测试版环境有效。 |
| API | `https://api-beta.demdex.com/...` | 您的生产环境凭据对测试版环境有效。We recommend that you create a generic API user, [see details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Accessing the DCS in the Beta Environment {#access-dcs-beta-environment}

1. Make a DCS call, using the curl [command](https://curl.haxx.se/docs/manpage.html). Curl是一种使用受支持的协议之一从服务器或服务器传输数据的工具。

   例如：

   `curl -v https://dcs-beta.demdex.net/event`

1. 通过在DCS响应头中查找“沙箱”，确认测试由测试版DCS提供。

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