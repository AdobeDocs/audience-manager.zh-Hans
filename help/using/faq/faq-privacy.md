---
description: 隐私性和数据方面的常见问题解答。
seo-description: 隐私性和数据方面的常见问题解答。
seo-title: 隐私和数据保留常见问题解答
solution: Audience Manager
title: 隐私和数据保留常见问题解答
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

隐私性和数据方面的常见问题解答。

<!-- faq_privacy.xml -->

## 隐私常见问题解答 {#privacy-faq}

>[!TIP]
>
>有关更 [多信息，请访](https://www.adobe.com/privacy.html) 问Adobe隐私中心。

**受众经理如何使用cookies，以及它设置了哪些cookies?**

See [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html).

**美国的受众经理客户能否目标欧盟资产上的用户？**

能。受众经理与拥有国际资产和库存的客户合作。 欧盟有严格的隐私法，但受众经理有客户使用第一方数据在欧洲进行受众定位。 受众经理可以支持针对欧盟受众的定位，但您有责任遵守当地隐私法规。

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## 数据保留常见问题解答 {#data-retention-faq}

下表列表了不同数据类型和存储系统的保留时间。

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
   <td colname="col2"> <p>120天。 </p> <p> 受众管理器在上次在受众管理器平台上看到用户120天后，从我们的后端服务器删除用户数据。 如 <span class="keyword"> 果受众管理</span> 器在120天的周期内记录用户活动，我们将再保留120天的数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>边缘服务器 </p> </td> 
   <td colname="col2"> <p> 14天。 </p> <p>受众管理器在上次在受众管理器平台上看到用户14天后，从我们的边缘服务器删除用户数据。 如 <span class="keyword"> 果受众管理</span> 器在此14天周期内记录用户活动，我们将再保留此数据14天。 如果用户在14天后再次变为活动状态，则第一个新页面视图与用户可操作时间之间会有延迟。 在超过14天不活动后，需要6-18小时才能将完整用户档案返回边缘中心。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>原始日志 </p> </td> 
   <td colname="col2"> <p>180天(在180天未活动后删除)。 </p> <p>原始日志是边缘服务器通过HTTP调用或从已载入的文件(发送到受众管理器)接收 <span class="keyword"> 的数据</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>广告服务器日志 </p> </td> 
   <td colname="col2"> <p><b>报表</b> </p> <p>日志文件的保留时间最长为30天，用于报告目的。 我们不会在我们的后端存储中保留不匹配的日志(即访客的广告服务器ID与 <span class="keyword"> 受众管理器ID之间没有ID同步的日志)，并且Amazon S3中存储的</span> 匹配日志最多保留30天 <span class="keyword"></span> 。 </p> <p><b>可操作的日志文件</b> </p> <p>匹配和不匹配的日志最多保留30天。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM级用户档案(经过身份验证的用户档案) </p> </td> 
   <td colname="col2"> <p>非活动的CRM级别用户档案（客户ID）的默认生存时间(TTL)间隔为24个月。 但是，您可以使用受众管理器UI将非活动的CRM级别用户档案的TTL间隔缩短或延长一个月至5年。 创建或编辑跨设备数据源时，可以完成此操作。</p> <p>有关详细信息，请参阅创建跨设 <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 备数据源中的数据源设置 </a>。</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>移动设备ID </p> </td> 
   <td colname="col2"> <p>移动设备ID(<a href="../reference/ids-in-aam.md"> IDFA、GAID</a>)的保留条件遵循前两行、后端服务器和边缘服务器中描述的顺序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>客户数据馈送(CDF) </p> </td> 
   <td colname="col2"> <p>CDF文件包含受众管理器 <span class="keyword"> 事件调用</span> (/事件)发送到我们服务器的相同数据。 保留期为8天。 有关CDF的更多详细信息，请参 <a href="../features/cdf-files.md"> 阅CDF介绍</a> 和 <a href="../faq/faq-cdf.md"> CDF常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>同步ID之间的映射 </p> </td> 
   <td colname="col2"> <p>受众管理器 <a href="../features/administration/usage-limits.md#id-mapping-limits"> Cookie</a> ID(受众管理器<a href="../reference/ids-in-aam.md">唯一用户ID或AAM UUID</a>)和第三方Cookie ID之间的ID映射的寿命限制为120天。 每次在受众管理器网络中看到受众管理器Cookie时，ID映射的寿命都会重置。 将在关联的受众管理器唯一用户ID(AAM UUID)的 <a href="../reference/ids-in-aam.md">有效期内保留最新的ID映射同步</a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>入站数据 </p> </td> 
   <td colname="col2"> <p>这是您通过FTP发送到 <span class="keyword"> 受众管理器</span> ，或直接发送到 <span class="keyword"> Amazon S3目录的入站数据</span> 。 请参阅入站 <a href="../faq/faq-inbound-data-ingestion.md"> 客户数据摄取常见问题解答</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>出站数据 </p> </td> 
   <td colname="col2"> <p>这是受众管理器发 <span class="keyword"> 送给第三方</span> 激活合作伙伴的批处理数据。 保留期为8天。 有关出站数据的详细信息，请参阅 <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> 出站批传</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 特征鉴定数据保留 {#trait-qual}

下表列表了特征资格的保留选项。

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
   <td colname="col2"> <p>删除特征会从过去符合该特征的所有用户用户档案中删除特征资格数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已达到特征限制 </p> </td> 
   <td colname="col2"> <p>我们对每个用户用户档案限制100,000个特质资格。 此限制适用于已验证的用户档案和设备用户档案。 如果用户用户档案达到此限制，我们将删除最早的特征资格，先入先出。 </p> <p>有关详细信息，请阅读我们的 <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> 特质资格限制</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

