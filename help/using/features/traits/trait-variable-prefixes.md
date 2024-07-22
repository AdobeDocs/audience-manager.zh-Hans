---
description: 本文介绍了在创建特征规则时，必须附加到关键变量的前缀。
seo-description: This article describes the prefixes you must attach to key variables when creating trait rules.
seo-title: Prefix Requirements for Key Variables
solution: Audience Manager
title: 关键变量的前缀要求
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
exl-id: 67fe0c74-6831-48cb-90cf-417ebbf7f272
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---

# 关键变量的前缀要求 {#prefix-requirements-for-key-variables}

本文介绍了在创建特征规则时，必须附加到关键变量的前缀。

<!-- r_tb_variable_prefixes.xml -->

## 关键变量前缀的目的

创建[!UICONTROL Trait Builder]规则时，务必要在键变量前面加上建议的前缀。 这些前缀标识传入的数据类型，并帮助避免[!DNL Audience Manager]内的命名空间冲突。 通常，您可以为变量指定任意名称，但如果键变量名称与事件调用中的变量名称不匹配，则不会处理规则的数据。

## 关键变量的前缀

下表定义了[!UICONTROL Trait Builder]使用的常用前缀。

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
   <td colname="col2"> <p>特定于客户。 这是从您自己的资产中发送的关键数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>在<span class="keyword">Audience Manager</span>级别。 此数据在<span class="keyword">Audience Manager</span>生态系统中是统一的。 有关更完整的列表，请参阅<a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API调用支持的属性</a>。</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>它包含<a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP标头</a>信息。 包括标头参数，如<code> referer</code>、<code> IP</code>、<code> accept-language</code>等。 </p> <p> <p>注意：对于使用低于9.0的DIL版本的客户，使用<code> h_referer</code>信号的数据收集在Safari浏览器上不起作用。 随着<a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>的引入，Safari浏览器可能会将demdex.net域分类为跟踪器，并将截断数据收集请求上的反向链接，使其仅包含原始URL而非完整URL。 有关最新DIL版本，请参阅<a href="../../dil/dil-overview.md#get-implement-dil-code">获取和实现DIL代码</a>。<p>使用此前缀的信号未出现在<a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">信号搜索</a>中。</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我们的<span class="wintitle">数据收集服务器</span>允许传递私有参数。 基本上，任何以<code> p_</code>开头的参数都将用于特征评估，但不会将其记录到下游，也不会存储。 </p> <p>示例：如果给定<code> /event?p_age=23</code>和诸如<code> YoungPeople = p_age &lt; 25</code>之类的特征，将实现该特征，但<code> p_age=23</code>键值对将在请求后删除并且不会被记录。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本信息概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特征规则](../../features/traits/manage-trait-rules.md#managing-trait-rules)
