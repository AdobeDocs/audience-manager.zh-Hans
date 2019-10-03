---
description: 介绍Audience manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-description: 介绍Audience manager集成以及遵守与消费者隐私和选择退出程序相关的公认最佳实践。
seo-title: 数据隐私
solution: Audience Manager
title: 数据隐私
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

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

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP模糊化方法：Adobe Audience manager遵循“按设计保护隐私”的原则，允许客户在UI中实现模糊化，无论是在全球所有地理区域还是针对特定国家／地区。 [!DNL IP] 启用此设置后，当将地址引入Audience manager中时，地址的最后八位字节( [!DNL IP] 最后一部分) [!DNL IP] 将立即被丢弃。 Audience manager在处理之前(包括 [!DNL IP] 在任何可选的地理查找或地址记录之前)放弃此部分地 [!DNL IP] 址。 例如：

* 在记录: `255.255.255.255`
* 之后: `255.255.255.0`

>[!NOTE]
>
>请参 [阅IP地址模糊化](/help/using/features/administration/ip-obfuscation.md) ，了解如何在Audience Manager UI [!DNL IP] 中启用地址模糊化。

观看以下视频，了解地址模糊 [!DNL IP] 处理在Audience manager中的工作原理。

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hans)

**** 地理细分：如果启用地 [!DNL IP] 址模糊处理，则地址的其余八位 [!DNL IP] 元仍可用于Audience manager中的地域划分和报告。 如果不启用地址模 [!DNL IP] 糊处理，则Audience manager将使用完整地 [!DNL IP] 址。 您可以使用“地理分段”功能，在任一情况下，该功能都允许您按地理区域来识别位置，但在使用模糊处理时，会稍有不 [!DNL IP][!DNL IP] 确定位置。 Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 获取区域和国家一级的信息应仅受到轻微影响。 地理细分数据仅粒度级别为市级或邮政编码级别，而不粒度级别为个人级别。 阅读更多关 [于地理定位](/help/using/features/traits/trait-geotarget-keys.md) ，以及如何使用地理变量设置特征。

## 相关概念 {#related-concepts}

* [选择退出管理](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [隐私和数据保留常见问题解答](/help/using/faq/faq-privacy.md)