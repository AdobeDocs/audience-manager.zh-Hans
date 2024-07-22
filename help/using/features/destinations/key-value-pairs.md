---
description: A [!DNL key-value pair] 由 [!DNL related elements]组成。 键，它是定义数据集（例如，性别、颜色、价格）的常量，值，它是属于该集的变量（例如，男性/女性、绿色、100）。 Destination Builder发送格式化为键值对的数据。
solution: Audience Manager
title: 标准和串行 [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# 标准和序列键值对 {#standard-and-serial-key-value-pairs}

键值对由相关元素组成：键值，它是定义数据集的常量（例如：性别、颜色、价格）；值，它是属于数据集的变量（例如，男性/女性、绿色、100）。 [!UICONTROL Destination Builder]发送格式化为键值对的数据。

## 基本键值对 {#basic-key-value-pairs}

如果采用完整形式，则键值对的基本集可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## 标准和序列键值对 {#standard-serial-key-value-pairs}

目标接受&#x200B;*`standard`*&#x200B;或&#x200B;*`serialized`*&#x200B;格式的键值数据。

* **标准键值对：**&#x200B;将目标数据格式化为单独的键值对。 每个键都明确地声明，即使再次用来定义不同的值时也是如此。
* **序列化的键值对：**&#x200B;将多个值压缩为一个键值对。 在序列化的键值对中，使用特殊指示符分隔键值集中的值。

标准键值和序列化键值均可包含单个或多个值。 下表提供了标准和序列键值格式的示例。

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 格式化 </th>
   <th colname="col2" class="entry"> 单键值对 </th>
   <th colname="col3" class="entry"> 多个键值对 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>标准</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>已序列化</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## 分隔符和分隔符 {#delimiters-separators}

将键和值之间或键内的值分隔的字符称为&#x200B;*`delimiters`*&#x200B;和&#x200B;*`separators`*。 当以序列格式将区段发送到目标时，这一点变得尤其重要。 序列化允许您使用单个键传入多个值并组合键值对。 分隔符和分隔符的定义如下：

* **键值分隔符：**&#x200B;用于分隔键值对中的键和值。
* **键值分隔符：**&#x200B;用于分隔键值对的集合。
* **序列分隔符：**&#x200B;用于分隔序列化键值对集合中的多个值。

## 示例 {#examples}

使用[!UICONTROL Destination Builder]，您可以通过多种不同的方式设置键值数据的格式。 让我们看一下每种类型的一些示例。

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 键值对示例 </th> 
   <th colname="col2" class="entry"> 示例 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>标准单键</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>键值对的简单集合。 此示例包含以下元素： </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">密钥： X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">值： 1， 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">分隔符： = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">键值分隔符： &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多个键值对</b> （非序列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>一组通过单独的键值集传递值的多个键值对。 此示例包含以下元素： </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">键：X、Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">值： 1、2、3、4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">分隔符： = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">键值分隔符： &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>串行单键</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>使用单个键传入多个值的键值集。 由于此键有多个值，因此它称为序列化的键值对。 此示例包含以下元素： </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">密钥： X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">值： 1、2、3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">分隔符： = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">序列分隔符：分号 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多个键值对</b> （序列） </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>一组在单独键上传递多个值的多个键值对。 此示例包含以下元素： </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">键：X、Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">值： 1、2、3、4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">分隔符： = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">分隔符： &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">序列分隔符：分号 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 目标序列化 {#destination-serialized}

序列化目标将多个特征组合为一个字符串，并将该信息发送到目标。

<!-- c_dest_serialized.xml -->

序列化数据传输有助于提高效率，因为多个特征会按顺序触发，而不是并行触发。 这样可在响应其他请求之前，为目标服务器提供足够的时间来接收、处理和返回数据。

### 支持的目标

在[!DNL Audience Manager]中，您可以序列化数据并将其发送到几乎任何您想要使用的目标。 但是，在使用此功能之前，您需要知道目标[!DNL URL]以及放置一些必需或可选宏的位置。 从目标合作伙伴获取有关宏放置的信息。 有关详细信息，请参阅[定义的目标宏](../../features/destinations/destination-macros.md#destination-macros-defined)。
