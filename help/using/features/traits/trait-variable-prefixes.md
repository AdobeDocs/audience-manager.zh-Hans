---
description: 本文描述创建特征规则时必须附加到关键变量的前缀。
seo-description: 本文描述创建特征规则时必须附加到关键变量的前缀。
seo-title: 关键变量的前缀要求
solution: Audience Manager
title: 关键变量的前缀要求
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
feature: Traits
translation-type: tm+mt
source-git-commit: 1c0d40082cd0753a9b4326aae764eb74aefb8be4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 5%

---


# 关键变量的前缀要求 {#prefix-requirements-for-key-variables}

本文描述创建特征规则时必须附加到关键变量的前缀。

<!-- r_tb_variable_prefixes.xml -->

## 关键变量前缀的用途

创建[!UICONTROL Trait Builder]规则时，务必在键变量前添加推荐前缀。 这些前缀标识传入的命名空间类型并帮助避免[!DNL Audience Manager]内的数据冲突。 通常，您可以为变量指定任何名称，但如果关键变量名称与事件调用中的变量名称不匹配，则规则的数据将不会处理。

## 关键变量前缀

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
   <td colname="col2"> <p>作为特定于客户。 这是从您自己的属性发送的关键数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>在<span class="keyword">Audience Manager</span>级别。 此数据在<span class="keyword">Audience Manager</span>生态系统中是一致的。 有关更完整的列表，请参阅<a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> DCS API调用的受支持属性</a>。</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>它包含<a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP头</a>信息。 包括标题参数，如<code> referer</code>、<code> IP</code>、<code> accept-language</code>等。 </p> <p> <p>注意：对于使用9.0以上DIL版本的客户，使用<code> h_referer</code>信号的数据收集在Safari浏览器上不工作。 引入<a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>后，Safari浏览器可以将demdex.net域分类为跟踪器，并将截断数据收集请求上的推荐人，以仅包含来源而不是完整URL。 有关最新的DIL版本，请参阅<a href="../../dil/dil-overview.md#get-implement-dil-code">获取和实施DIL代码</a>。<p>在<a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">信号搜索</a>中未呈现使用此前缀的信号。</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我们的<span class="wintitle">数据收集服务器</span>允许传递私有参数。 基本上，具有<code> p_</code>的开始的任何参数都将用于特征评估，但不会在下游记录或存储。 </p> <p>示例：对于<code> /event?p_age=23</code>和类似<code> YoungPeople = p_age &lt; 25</code>的特征，将实现该特征，但在请求后将删除<code> p_age=23</code>密钥值对，并且不会记录。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本信息概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特征规则](../../features/traits/manage-trait-rules.md#managing-trait-rules)

