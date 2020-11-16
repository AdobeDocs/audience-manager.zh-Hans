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

创建规则 [!UICONTROL Trait Builder] 时，务必在键变量前面添加建议的前缀。 这些前缀标识传入的命名空间类型并帮助避免内部数据冲突 [!DNL Audience Manager]。 通常，您可以为变量指定任何名称，但如果关键变量名称与事件调用中的变量名称不匹配，则规则的数据将不会处理。

## 关键变量前缀

下表定义了使用的公用前缀 [!UICONTROL Trait Builder]。

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
   <td colname="col2"> <p>在Audience Manager <span class="keyword"> 级别</span> 。 这些数据在Audience Manager生态系统中 <span class="keyword"> 是一致的</span> 。 请参 <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> 阅DCS API调用的受支持属性</a> ，以获得更完整的列表。</p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>它包含 <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP头信息</a> 。 包括标题参 <code> referer</code>数<code> IP</code>, <code> accept-language</code>如、 </p> <p> <p>注意：对于使用9.0以上DIL版本的客户，使用该信号的数据 <code> h_referer</code> 收集在Safari浏览器上无效。 引入ITP 2 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> .0后</a>,Safari浏览器可以将demdex.net域分类为跟踪器，并将截断数据收集请求上的推荐人，以仅包含来源而不是完整URL。 请参 <a href="../../dil/dil-overview.md#get-implement-dil-code">阅获取和实施DIL</a> ，以获取最新DIL版本。<p>信号搜索中不会出现使用此前缀 <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">的信号</a>。</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我们 <span class="wintitle"> 的数据收集服务器</span> ，允许传递私有参数。 基本上，具有开始的任 <code> p_</code> 何参数都将用于特征评估，但不会记录在下游或存储。 </p> <p>示例：给 <code> /event?p_age=23</code> 定的特征和类 <code> YoungPeople = p_age &lt; 25</code>似的特征将实现该特征，但 <code> p_age=23</code> 在请求后将删除key-value对，并且不会记录。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [基本信息概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特征规则](../../features/traits/manage-trait-rules.md#managing-trait-rules)

