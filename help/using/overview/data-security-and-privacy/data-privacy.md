---
description: 介绍Audience Manager集成和遵守一般接受的与消费者隐私和选择退出过程相关的最佳实践。
seo-description: 介绍Audience Manager集成和遵守一般接受的与消费者隐私和选择退出过程相关的最佳实践。
seo-title: 数据隐私
solution: Audience Manager
title: 数据隐私
uuid: 865e7b4e-value1-4fa4-8035-1595fc77 cd96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# 数据隐私{#data-privacy}

介绍Audience Manager集成和遵守一般接受的与消费者隐私和选择退出过程相关的最佳实践。

## 数据隐私{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager可识别消费者与其互动品牌之间的隐式协议。双方都受益于匿名数据元素的透明交换：

* 消费者可获得个性化内容、折扣产品优惠以及简化的用户体验。
* 品牌会获得重要的收入流，支持多个在线业务模型。

在我们继续支持这一模型的情况下，Audience Manager仍致力于为消费者提供透明度和控制权，并超越在线行为广告(OBA)自律原则。

## Opt-Out Management {#opt-out-management}

选择退出文档已延期并将其移至文档的单独部分。See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

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

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

访问客户网站的访客 IP 地址会被传输到 Adobe 数据处理中心 (DPC)，IP 地址可能存储在那里。根据访客的网络配置，IP地址未必代表访客计算机的IP地址。例如，IP 地址可能为网络地址转换 (NAT) 防火墙、HTTP 代理或互联网网关的外部 IP 地址。

**IP模糊处理方法：** 遵循“隐私依据设计”的原则，Adobe Audience Manager允许客户从用户界面(全球所有地理区域或针对特定国家/地区)启用IP模糊处理。启用此设置后，将在将IP地址收录到Audience Manager时立即放弃IP地址的最后一个字节(最后一部分)。Audience Manager会在处理之前放弃IP地址的此部分(包括在任何可选地理位置查找或记录IP地址之前)。例如：

* 在记录: `255.255.255.255`
* 之后: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**地理分段：** 如果您启用IP地址模糊处理，则IP地址的剩余八个字节仍可用于Audience Manager中的地理分段和报告。如果您不启用IP地址模糊处理，Audience Manager将使用完整的IP地址。您可以使用地理分段功能，以便在任一情况下按地理区域确定IP位置，但在使用IP模糊化时稍有降低。获取城市级别信息很有可能会受到 IP 地址模糊处理的影响。获取地区和国家级信息只会受到轻微影响。地理分段数据仅粒度为城市级别或邮政编码级别，不适用于个人级别。Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## 相关概念 {#related-concepts}

* [选择退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [隐私和数据保留常见问题解答](/help/using/faq/faq-privacy.md)