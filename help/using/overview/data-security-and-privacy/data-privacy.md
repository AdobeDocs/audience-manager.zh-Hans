---
description: 介绍Audience manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-description: 介绍Audience manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-title: 数据隐私
solution: Audience Manager
title: 数据隐私
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# 数据隐私{#data-privacy}

介绍Audience manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。

## 数据隐私{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## 消费者隐私保护 {#consumer-privacy-protection}

Audience manager认识到消费者与与之互动的在线品牌之间的隐性契约。 双方都从匿名数据元素的透明交换中受益：

* 消费者可获得个性化内容、折扣产品推广信息和简化的用户体验。
* 品牌可获得支持多种在线业务模型的重要收入流。

在我们对这一模式的持续支持中，Audience manager继续致力于为消费者提供透明度和控制，并满足或超越在线行为广告(OBA)自律原则。

## 退出管理 {#opt-out-management}

选择退出文档已扩展并移至我们文档的另一部分。 请参 [阅退出管理](../../overview/data-security-and-privacy/opt-out-management.md)。

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## 收集IP地址和IP地址模糊化 {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

访问客户网站的访客 IP 地址会被传输到 Adobe 数据处理中心 (DPC)，IP 地址可能存储在那里。根据访客的网络配置，IP地址不一定代表访客计算机的IP地址。 例如，IP 地址可能为网络地址转换 (NAT) 防火墙、HTTP 代理或互联网网关的外部 IP 地址。

**** IP模糊化方法：Adobe Audience manager遵循“按设计保护隐私”的原则，允许客户在全球所有地理区域或特定国家／地区的UI中启用IP模糊化。 启用此设置后，当将IP地址引入Audience manager时，IP地址的最后八位字节（最后一部分）将立即被丢弃。 Audience manager在处理之前（包括在任何可选的地理查找或IP地址记录之前），会丢弃IP地址的这一部分。 例如：

* 在记录: `255.255.255.255`
* 之后: `255.255.255.0`

>[!NOTE]
>
>请参 [阅IP地址模糊化](/help/using/features/administration/ip-obfuscation.md) ，了解如何在Audience Manager UI中启用IP地址模糊化。

**** 地理细分：如果启用IP地址模糊处理，则IP地址的其余八位字节仍可用于Audience manager中的地理划分和报告。 如果不启用IP地址模糊处理，Audience manager将使用完整的IP地址。 您可以使用“地理分段”功能，该功能允许您按地理区域识别IP位置，但在使用IP模糊处理时会稍有不准确。 获取城市级别信息很有可能会受到 IP 地址模糊处理的影响。获取区域和国家一级的信息应仅受到轻微影响。 地理细分数据仅粒度级别为市级或邮政编码级别，而不粒度级别为个人级别。 阅读更多关 [于地理定位](/help/using/features/traits/trait-geotarget-keys.md) ，以及如何使用地理变量设置特征。

## 相关概念 {#related-concepts}

* [选择退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [隐私和数据保留常见问题解答](/help/using/faq/faq-privacy.md)