---
description: 隐私性和数据方面的常见问题解答。
seo-description: 隐私性和数据方面的常见问题解答。
seo-title: 隐私和数据保留常见问题解答
solution: Audience Manager
title: 隐私和数据保留常见问题解答
uuid: ef558fca-35ff-44f1-8527-f8 f9 f2 c7 e9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

隐私性和数据方面的常见问题解答。

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**Audience Manager如何使用cookies以及它设置哪些cookies？**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**美国的Audience Manager客户是否可以瞄准欧盟资产的用户？**

能。Audience Manager可与具有国际属性和库存的客户合作。欧盟有严格的隐私法，但Audience Manager的客户是在欧洲使用第一方数据的客户。Audience Manager可支持面向欧盟受众的定位，但您有责任遵守当地隐私规定。

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 数据保留常见问题解答 {#data-retention-faq}

下表列出了不同数据类型和存储系统的保留时间。

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据类型、源或存储 </th> 
   <th colname="col2" class="entry"> 数据保留期限 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>后端服务器 </p> </td> 
   <td colname="col2"> <p>120天。 </p> <p> Audience Manager在上次查看Audience Manager平台上的用户之后12天内从我们的后端服务器删除用户数据。<span class="keyword"> 如果Audience Manager</span> 在此12天周期内记录用户活动，我们会将此数据另保存120天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>边缘服务器 </p> </td> 
   <td colname="col2"> <p> 14天。 </p> <p>Audience Manager在上次看到Audience Manager平台上的用户后14天内从我们的边缘服务器删除用户数据。<span class="keyword"> 如果Audience Manager</span> 在此14天周期内记录用户活动，我们会将此数据保存为14天。如果用户在14天后再次变为活动状态，则第一次新页面查看与用户可操作时将有延迟。在不活动超过14天的时间内，需要6-18小时才能将完整的档案送回边缘中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw日志 </p> </td> 
   <td colname="col2"> <p>180天(无活动180天后删除)。 </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server日志 </p> </td> 
   <td colname="col2"> <p><b>报表</b> </p> <p>在最长30天内将日志文件保留为报告目的。We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>可操作的日志文件</b> </p> <p>匹配的和无与伦比的日志将保留30天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM级别配置文件(实名配置文件) </p> </td> 
   <td colname="col2"> <p>未激活CRM级别配置文件(客户ID)的默认到实时(TTL)时间间隔为24个月。但是，您可以使用Audience Manager UI缩短或延长一个月和年之间未激活CRM级别配置文件的TTL间隔。您可以在创建或编辑跨设备数据源时完成此操作。</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备ID </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客户数据馈送(CMS) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. 保留期为天。For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>同步ID之间的映射 </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站数据 </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出站数据 </p> </td> 
   <td colname="col2"> <p>This is the batch data that <span class="keyword"> Audience Manager</span> sends to third party activation partners. 保留期为天。For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

下表列出了特征资格的保留选项。

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
   <td colname="col2"> <p>删除特征将删除所有符合过去特征的用户配置文件中的特征资格数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已达到特征限制 </p> </td> 
   <td colname="col2"> <p>我们限制每个用户个人资料的100，000特征资格。此限制适用于经过身份验证的配置文件和设备配置文件。如果用户配置文件达到此限制，我们将在首次推出时删除最早的特征资格资格资格。 </p> <p>For more details, read our <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

