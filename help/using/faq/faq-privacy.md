---
description: 隐私性和数据方面的常见问题解答。
seo-description: 隐私性和数据方面的常见问题解答。
seo-title: 隐私和数据保留常见问题解答
solution: Audience Manager
title: 隐私和数据保留常见问题解答
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 3a4f23bc853a2324a4c91c6e65b14455293a5b1b

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

隐私性和数据方面的常见问题解答。

<!-- faq_privacy.xml -->

## 隐私常见问题解答 {#privacy-faq}

>[!TIP]
>
>有关更多 [信息，请访问Adobe隐私中心](https://www.adobe.com/privacy.html) 。

**Audience manager如何使用cookies及其设置了哪些cookies?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**美国的Audience manager客户是否可以针对欧盟资产的用户进行定位？**

能。Audience manager可与拥有国际资产和库存的客户协作。 欧盟有严格的隐私法，但Audience manager的客户使用第一方数据在欧洲定位受众。 Audience manager可以支持针对欧盟受众的定位，但您有责任遵守当地隐私法规。

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
   <td colname="col2"> <p>120-days. </p> <p> Audience manager在上次在Audience manager平台上查看用户后120天从我们的后端服务器中删除用户数据。 如果 <span class="keyword"> Audience Manager在120天周期内记录用户活动</span> ，我们将再保留120天的此数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>边缘服务器 </p> </td> 
   <td colname="col2"> <p> 14-days. </p> <p>Audience manager在上次在Audience manager平台上查看用户后14天从边缘服务器删除用户数据。 如果 <span class="keyword"> Audience Manager在14天周期内记录用户活动</span> ，我们将再保留14天的此数据。 If the user becomes active again after the 14-day period, there will be a delay between that first new page view and when the user becomes actionable. 在超过14天不活动后，需要6-18小时才能将完整配置文件重新发布到边缘中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>原始日志 </p> </td> 
   <td colname="col2"> <p>180-days (removed after 180-days of no activity). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>报表</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and  Audience Manager ID) in our backend storage, and matched logs stored in  Amazon S3 are retained for up to 30 days.<span class="keyword"></span><span class="keyword"></span> </p> <p><b>可操作的日志文件</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>The default time-to-live (TTL) interval for inactive CRM-level profiles (Customer IDs) is 24 months. However, you can use the Audience Manager UI to reduce or extend the TTL interval for inactive CRM-level profiles between one month and 5 years. You can accomplish this when creating or editing a Cross-Device data source.</p> <p>For more information, see Data Source Settings in  Create a Cross-Device Data Source .<a href="../features/profile-merge-rules/merge-rules-start.md#settings"></a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs ( IDFA, GAID) follow the cadence described in the first two rows, back-end servers and edge servers.<a href="../reference/ids-in-aam.md"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Customer Data Feeds (CDF) </p> </td> 
   <td colname="col2"> <p>CDF文件包含的数据与 <span class="keyword"> Audience Manager事件调用</span> （/事件）发送到我们的服务器的数据相同。 保留期为8天。 有关CDF的更多详细信息，请参阅 <a href="../features/cdf-files.md"> CDF简介</a> 和 <a href="../faq/faq-cdf.md"> CDF常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>同步ID之间的映射 </p> </td> 
   <td colname="col2"> <p>Audience Manager Cookie ID( <a href="../features/administration/usage-limits.md#id-mapping-limits"> Audience Manager唯一用户ID或AAM UUID</a><a href="../reference/ids-in-aam.md"></a>)与第三方Cookie ID之间的ID映射的寿命限制为120天。 每次在Audience Manager网络中查看Audience Manager Cookie时，ID映射的寿命都会重置。 将在关联的 <a href="../reference/ids-in-aam.md">Audience Manager唯一用户ID(AAM UUID)的有效期内保留最新的ID映射同步</a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站数据 </p> </td> 
   <td colname="col2"> <p>这是您通过FTP发送到 <span class="keyword"> Audience Manager</span> ，或直接发送到 <span class="keyword"> Amazon S3目录的入站数据</span> 。 请参阅入站 <a href="../faq/faq-inbound-data-ingestion.md"> 客户数据摄取常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出站数据 </p> </td> 
   <td colname="col2"> <p>这是Audience manager发送给第三方激 <span class="keyword"> 活合作伙伴的</span> 批量数据。 保留期为8天。 有关出站数据的更多详细信息，请参阅 <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> 出站批量传输</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特征鉴定数据保留 {#trait-qual}

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
   <td colname="col2"> <p>删除特征会从过去符合该特征的所有用户配置文件中删除特征资格数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>达到特征限制 </p> </td> 
   <td colname="col2"> <p>我们对每个用户配置文件限制为100,000个特质资格。 此限制适用于经过身份验证的配置文件和设备配置文件。 如果用户配置文件达到此限制，我们将先入先出地删除最旧的特征资格。 </p> <p>有关更多详细信息，请阅读我们的 <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> 特质资格限制</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

