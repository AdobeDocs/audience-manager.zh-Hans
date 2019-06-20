---
description: 键值对由相关元素A组成，该键是一个常量，它定义数据集(例如，性别、颜色、价格)和值，这是属于集合的变量(如男性/女性、绿色、100)。目标生成器发送格式设置为关键值对的数据。
seo-description: 键值对由相关元素A组成，该键是一个常量，它定义数据集(例如，性别、颜色、价格)和值，这是属于集合的变量(如男性/女性、绿色、100)。目标生成器发送格式设置为关键值对的数据。
seo-title: 标准和串行键值对
solution: Audience Manager
title: 标准和串行键值对
uuid: 43789419-5b3f-4e62-b2 e0-2722320bdd41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

键值对由相关元素组成：一个键，它是定义数据集(例如性别、颜色、价格)和值的常数，它是属于该集合的变量(如男性/女性、绿色、100)。[!UICONTROL Destination Builder] 发送作为关键值对的数据。

## Basic Key-Value Pairs {#basic-key-value-pairs}

完全组成，一组基本的键值对可能如下所示：

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **标准键值对：** 将目标数据格式设置为单独的键值对。每个键都显式表示，即使再次使用也可以定义不同的值。
* **序列化密钥值对：** 将多个值压缩为一个键值对。在序列化密钥值对中，特殊指示符会分离键值集中的值。

标准键和序列化键值都可以包含单个或多个值。下表提供标准和串行键值格式的示例。

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 格式化 </th>
   <th colname="col2" class="entry"> 单个键值对 </th>
   <th colname="col3" class="entry"> 多个关键值对 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>标准</b> </p> </td>
   <td colname="col2"> <p> <code> x=1&amp; x=2 </code> </p> </td>
   <td colname="col3"> <p> <code> x=1&amp; x=2&amp; y=3&amp; y=4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>序列化</b> </p> </td> 
   <td colname="col2"> <p> <code> x=1；2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x=1；2&amp; y=3；个 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. 当您以串行格式将区段发送到目标时，这些变得尤为重要。序列化允许您通过一个键传递多个值并组合键值对。分隔符和分隔符定义如下：

* **密钥值分隔符：** 在键值对中分离键和值。
* **密钥值分隔符：** 分离关键值对集。
* **串行分隔符：** 在序列化密钥值对集中分隔多个值。

## 示例 {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. 让我们来看一下每种类型的示例。

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 密钥值对示例 </th> 
   <th colname="col2" class="entry"> 示例 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>标准单键键</b> </p> </td> 
   <td colname="col2"> <p> <code> X=&amp; X=2 </code> </p> </td> 
   <td colname="col3"> <p>一组简单的键值对。该示例包含以下元素： </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">密钥：X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">值：1，2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">分隔符：== </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">密钥值分隔符：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多个键值对</b> (非串行) </p> </td> 
   <td colname="col2"> <p> <code> X=&amp; X=2&amp; Y=3&amp; Y=4 </code> </p> </td> 
   <td colname="col3"> <p>用单独的键值集传递值的多个键值对。该示例包含以下元素： </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">密钥：X，Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">值：1，2，3，4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">分隔符：== </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">密钥值分隔符：&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>串行单一键</b> </p> </td> 
   <td colname="col2"> <p> <code> X=1；2；3 </code> </p> </td> 
   <td colname="col3"> <p>通过单键传递以多个值传递的键值设置。由于此键有多个值，因此它被称为序列化键值对。该示例包含以下元素： </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">密钥：X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">值：1，2，3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">分隔符：== </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">串行分隔符：半冒号 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>多个键值对</b> (串行) </p> </td> 
   <td colname="col2"> <p> <code> X=1；2&amp; Y=3；个 </code> </p> </td> 
   <td colname="col3"> <p>在单独的键上传递多个值的多个键值对的集合。该示例包含以下元素： </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">密钥：X，Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">值：1，2，3，4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">分隔符：== </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Delimiter（分隔符）: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">串行分隔符：半冒号 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

序列化目标将多个特征合并为一个字符串，并将该信息发送到目标。

<!-- c_dest_serialized.xml -->

序列化数据传输有助于提高效率，因为按顺序触发多个特征，而不是并行。这为目标服务器提供了足够的时间来接收、处理和返回数据，然后响应其他请求。

### 支持的目标

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. 从目标合作伙伴处获取有关宏位置的信息。See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.