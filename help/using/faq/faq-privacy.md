---
description: 有关隐私和数据的常见问题解答。
seo-description: 有关隐私和数据的常见问题解答。
seo-title: 隐私和数据保留常见问题解答
solution: Audience Manager
title: 隐私和数据保留常见问题解答
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: 数据管理和隐私
exl-id: bccf49d7-1a3b-4286-86fb-59e472af4501
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 83%

---

# 隐私和数据保留常见问题解答{#privacy-and-data-retention-faq}

有关隐私和数据的常见问题解答。

<!-- faq_privacy.xml -->

## 隐私常见问题解答 {#privacy-faq}

>[!TIP]
>
>有关更多信息，请访问 [Adobe 隐私中心](https://www.adobe.com/cn/privacy.html)。

**Audience Manager 如何使用 Cookie？Audience Manager 会设置哪些 Cookie？**

请参阅 [Audience Manager Cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)。

**美国的 Audience Manager 客户能否定位欧盟资产的用户？**

能。Audience Manager 与在全球拥有资产和库存的客户合作。虽然欧盟地区实施了严格的隐私法，但 Audience Manager 的一些客户仍使用第一方数据在欧洲地区进行受众定位。因此，Audience Manager 可以支持针对欧盟地区受众的定位，但是您有责任遵守当地隐私法规。

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 数据保留常见问题解答 {#data-retention-faq}

下表列出了各类型数据的保留时长和存储系统。

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据类型、来源或存储 </th> 
   <th colname="col2" class="entry"> 数据保留期 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>后端服务器 </p> </td> 
   <td colname="col2"> <p>120天 </p> <p> Audience Manager 会在 120 天后（从上次在 Audience Manager 平台上看到用户之日算起）从后端服务器删除用户数据。如果<span class="keyword">Audience Manager</span>在此120天的周期中记录到用户活动，我们将再将数据保留120天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge 服务器 </p> </td> 
   <td colname="col2"> <p> 14天 </p> <p>Audience Manager 会在 14 天后（从上次在 Audience Manager 平台上看到用户之日算起）从 Edge 服务器删除用户数据。如果<span class="keyword">Audience Manager</span>在此14天的周期中记录到用户活动，我们将再将数据保留14天。 如果用户在14天周期后再次变为活动状态，则从第一次查看新页面到用户变为可操作状态之间将会有延迟。 超过14天不活动后，需要6-18小时才能将完整配置文件返回到边缘中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>原始日志 </p> </td> 
   <td colname="col2"> <p>60天（在60天不活动后删除） </p> <p>原始日志是 Edge 服务器通过 HTTP 调用接收到的数据，或从发送到 <span class="keyword">Audience Manager</span> 的已载入文件接收到的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>广告服务器日志 </p> </td> 
   <td colname="col2"> <p><b>报表</b> </p> <p>当用于报表时，日志文件最多可保留 30 天。我们不会在后端存储中保留不匹配的日志（即访客的广告服务器 ID 未与 <span class="keyword">Audience Manager</span> ID 进行同步的日志），并且 <span class="keyword">Amazon S3</span> 中存储的匹配日志最多可保留 30 天。 </p> <p><b>可操作的日志文件</b> </p> <p>匹配的日志和不匹配的日志最多都可保留 30 天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM 级别配置文件（已验证的配置文件） </p> </td> 
   <td colname="col2"> <p>非活动的 CRM 级别配置文件（客户 ID）的默认存留期 (TTL) 为 24 个月。但是，您可以使用Audience Manager用户界面缩短或延长不活动的CRM级别配置文件的TTL，TTL的有效期为1个月到5年。 您可以在创建或编辑跨设备数据源时执行此操作。</p> <p>有关更多信息，请参阅<a href="../features/profile-merge-rules/merge-rules-start.md#settings">创建跨设备数据源</a>中的“数据源设置”。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备 ID </p> </td> 
   <td colname="col2"> <p>移动设备 ID（<a href="../reference/ids-in-aam.md">IDFA、GAID</a>）的保留条件遵循前两行“后端服务器”和“Edge 服务器”中所述的终止时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客户数据信息源 (CDF) </p> </td> 
   <td colname="col2"> <p>CDF 文件包含的数据与 <span class="keyword">Audience Manager</span> 事件调用 (/event) 发送到我们服务器的数据相同。保留期为 8 天。有关 CDF 的更多详细信息，请参阅 <a href="../features/cdf-files.md">CDF 简介</a>和 <a href="../faq/faq-cdf.md">CDF 常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已同步 ID 之间的映射 </p> </td> 
   <td colname="col2"> <p>Audience Manager Cookie ID（<a href="../reference/ids-in-aam.md">Audience Manager 独特用户 ID 或 AAM UUID</a>）与第三方 Cookie ID 之间的 <a href="../features/administration/usage-limits.md#id-mapping-limits">ID 映射</a>的有效期限制为 120 天。每当在 Audience Manager 网络中看到 Audience Manager Cookie 时，ID 映射的有效期便会重置。最近一次 ID 映射同步的保留时间将等于相关联的 <a href="../reference/ids-in-aam.md">Audience Manager 独特用户 ID (AAM UUID)</a> 的有效期。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站数据 </p> </td> 
   <td colname="col2"> <p>您通过 FTP 发送到 <span class="keyword">Audience Manager</span> 的入站数据，或直接发送到 <span class="keyword">Amazon S3</span> 目录的数据。请参阅<a href="../faq/faq-inbound-data-ingestion.md">入站客户数据摄取常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出站数据 </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span> 发送到第三方激活合作伙伴的批量数据。保留期为 8 天。有关出站数据的更多详细信息，请参阅<a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">出站数据批量传输</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特征资格数据保留 {#trait-qual}

下表列出了适用于特征资格数据的保留选项。

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 特征操作 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>删除特征 </p> </td> 
   <td colname="col2"> <p>若删除某个特征，则会从之前符合该特征的所有用户配置文件中删除特征资格数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已达到特征限制 </p> </td> 
   <td colname="col2"> <p>我们将每个用户配置文件的特征资格数限制为 100,000。此限制适用于已验证的用户配置文件和设备配置文件。如果用户配置文件达到此限制，我们将按先进先出原则删除最早的特征资格数据。 </p> <p>有关更多详细信息，请参阅我们的<a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">特征资格限制</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>
