---
description: 本文描述创建特征规则时必须附加到关键变量的前缀。
seo-description: 本文描述创建特征规则时必须附加到关键变量的前缀。
seo-title: 关键变量的前缀要求
solution: Audience Manager
title: 关键变量的前缀要求
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 关键变量的前缀要求 {#prefix-requirements-for-key-variables}

本文描述创建特征规则时必须附加到关键变量的前缀。

<!-- r_tb_variable_prefixes.xml -->

## 关键变量前缀的用途

在创建规 [!UICONTROL Trait Builder] 则时，务必在键变量前加推荐前缀。 这些前缀标识传入的数据类型并帮助避免内部的命名空间冲突 [!DNL Audience Manager]。 通常，您可以为变量指定任何名称，但如果关键变量名称与事件调用中的变量名称不匹配，则规则的数据将不会处理。

## 关键变量的前缀

下表定义了使用的公共前缀 [!UICONTROL Trait Builder]。

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键变量前缀 </th> 
   <th colname="col2" class="entry"> 标识变量 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>作为特定客户。 这是从您自己的属性发送的关键数据。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>在Audience Manager <span class="keyword"> 级别</span> 。 此数据在 <span class="keyword"> Audience manager生态系统中是统一的</span> 。 有关 <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> 更完整的列表，请参阅DCS API调用的受支持属性</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>它包含 <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP头信息</a> 。 包括标题参 <code> 数</code>，如referer<code> 、IP</code>、 <code> accept-language</code>，等等。 </p> <p> <p>注意：对于使用9.0以上DIL版本的客户，使用 <code> h_referer信号的数据收集在Safari浏览器上不工作</code> 。 随着 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0的推出</a>,Safari浏览器可能会将demdex.net域分类为跟踪器，并将在数据收集请求中截断引用来源，以仅包含源而不是完整的URL。 请参 <a href="../../dil/dil-overview.md#get-implement-dil-code">阅获取和实施DIL代码</a> ，了解最新DIL版本。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>我们 <span class="wintitle"> 的数据收集服务器</span> ，允许传递私有参数。 基本上，以 <code> p_</code> 开头的任何参数都将用于特征评估，但不会记录在下游或存储。 </p> <p>示例：如果 <code> /event?p_age=23</code> ，并且某个特征(如 <code> YoungPeople = p_age &lt; 25</code>)，则将实现该特征，但 <code> p_age=23</code> key-value对将在请求后被删除，并且将不被记录。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [基本信息概述](../../features/traits/create-onboarded-rule-based-traits.md)
>* [管理特征规则](../../features/traits/manage-trait-rules.md#managing-trait-rules)

