---
description: 本文描述了在创建特征规则时必须附加到关键变量的前缀。
seo-description: 本文描述了在创建特征规则时必须附加到关键变量的前缀。
seo-title: 关键变量的前缀要求
solution: Audience Manager
title: 关键变量的前缀要求
uuid: df2ef9c8-606a-45f9-a836-859f856 a7 d4 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Prefix Requirements for Key Variables {#prefix-requirements-for-key-variables}

本文描述了在创建特征规则时必须附加到关键变量的前缀。

<!-- r_tb_variable_prefixes.xml -->

## 关键变量前缀的用途

When you create [!UICONTROL Trait Builder] rules, it is important to preface the key variable with a recommended prefix. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. 通常，您可以为变量提供任何名称，但如果键变量名称与事件调用中的变量名称不匹配，则规则的数据将不会处理。

## 关键变量的前缀

The following table defines the common prefixes used by [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 密钥变量前缀 </th> 
   <th colname="col2" class="entry"> 标识变量 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>与客户特定。这是从您自己的属性发送的关键数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 级别。This data is uniform across the <span class="keyword"> Audience Manager</span> ecosystem. See <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a> for a more complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>That contains <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> information. Includes header parameters such as <code> referer</code>,<code> IP</code>, <code> accept-language</code>, etc. </p> <p> <p>Note: For customers using DIL versions older than 9.0, data collection using the <code> h_referer</code> signal will not work on Safari browsers. With the introduction of <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, Safari browsers may classify the demdex.net domain as a tracker and will truncate the referrer on the data collection request to only contain the origin instead of the full URL. See <a href="../../dil/dil-overview.md#get-implement-dil-code">Getting and Implementing DIL Code</a> for the latest DIL version.. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p><span class="wintitle"> 我们的数据收集服务器</span> 允许传递私有参数。Basically, any parameter that starts with <code> p_</code> will be used for trait evaluation, but it will not be logged downstream, nor stored. </p> <p>Example: given <code> /event?p_age=23</code> and a trait like <code> YoungPeople = p_age &lt; 25</code>, the trait will be realized, but the <code> p_age=23</code> key-value pair will be dropped after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [基本信息概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特征规则](../../features/traits/manage-trait-rules.md#managing-trait-rules)

