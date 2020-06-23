---
description: 在区段生成器中，最近和频率允许您根据在设置的每日间隔内发生或重复的操作对访客进行区段。
seo-description: 在区段生成器中，最近和频率允许您根据在设置的每日间隔内发生或重复的操作对访客进行区段。
seo-title: 回访间隔和频度
solution: Audience Manager
title: 回访间隔和频度
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 3%

---


# 回访间隔和频度 {#recency-and-frequency}

在中 [!UICONTROL Segment Builder]、最近和频率，您可以根据在设置的每日间隔内发生或重复的操作对访客进行细分。

Audience Manager定 [!DNL recency] 义 [!DNL frequency] 如下：

* **[!UICONTROL Recency]:**用户最近查看或符合一个（或多个）用户资格的时间[!UICONTROL traits]。
* **[!UICONTROL Frequency]:**用户查看或限定一个（或多个）用户的速率[!UICONTROL traits]。

[!UICONTROL Recency] 和设 [!UICONTROL Frequency] 置可帮助您根据访客对网站、章节或特定创意的真实（或感知）兴趣级别对其进行细分。 例如，符合最近／频率要求较高细分的用户对网站或产品的兴趣可能大于访问频率较低或访问频率较低的用户。

## 设置的位 [!UICONTROL Recency and Frequency] 置 {#location}

In [!UICONTROL Segment Builder]和 [!UICONTROL Recency] 设置位于 [!UICONTROL Frequency] 面板的 [!UICONTROL Basic View][!UICONTROL Traits] 部分。 单击时钟图标以显示这些控件。

![](assets/recency_frequency.png)

## 限制和规则 {#limitations-rules}

当您希望将最近期和频率应用于区段中的特征时，请查看并了解这些限制和规则。

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 限制或规则 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>最小值</b> </p> </td> 
   <td colname="col2"> <p>最近的值必须大于0。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>特征类型</b> </p> </td> 
   <td colname="col2"> <p>您只能将最近使用的控制应用于基于规则和文件夹的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方特征</b> </p> </td> 
   <td colname="col2"> <p>不能为包含第三方特征的个人第三方特征或特征组设置最近规则。 近期和频率仅适用于您自己的特征。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 限制或规则 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>第三方特征</b> </p> </td> 
   <td colname="col2"> <p>不能为包含第三方特征的个人第三方特征或特征组设置频率规则。 近期和频率仅适用于您自己的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特征类型</b> </p> </td> 
   <td colname="col2"> <p>您只能将频率控制应用于基于规则和文件夹的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>最近要求</b> </p> </td> 
   <td colname="col2"> <p>您可以配置频率要求，而 <i>不配置</i> 最近频率要求。 只需设置一个频率值，并将“最近”字段留空。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>配置文件合并规则</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最近示例 {#recency-examples}

下面是两个说明最近如何工作的示例，具体取决于您在UI中的选择：

### 使用小于或等于运算符(&lt;=)

![小于或等于](assets/less-than-equal-to.png)

在此示例中，您选择&lt;=运算符，如屏幕截图所示。 如果用户在过去 [!UICONTROL segment] 五天内至少有三次符合这 [!UICONTROL traits] 三种情况中任何一种的条件，则这将使用户有资格获得。 以下时间轴显 [!UICONTROL segment] 示创建时的资 [!UICONTROL segment] 格，即10月1日和10天后。

![最近五天](assets/last-5-days.png)

### 使用大于或等于运算符(=>)

![大于等于](assets/greater-than-equal-to.png)

在此示例中，您选择=>运算符，如屏幕截图所示。 如果用户在Audience Manager平 [!UICONTROL segment] 台上首次获得资格和五天前中断 [!UICONTROL traits] 时间之间，每次至少有三次资格，这样您的用户就有资格享受这三者中的任何一次。 以下时间轴显 [!UICONTROL segment] 示创建时的资 [!UICONTROL segment] 格，即10月1日和10天后。

![早期资格](assets/earlier-qualification.png)


## 频率上限示例 {#frequency-capping}

频率上限表达式包括其实现数量低于所 [!UICONTROL trait] 需值的所有用户。 以下是一些正确和错误的示例：

* 错误-表达式包 `frequency([1000T]) <= 5` 括已实现ID为“ [!UICONTROL trait] 1000”（最多五次）的所有用户，但也包括尚未实现该标识的用户 [!UICONTROL trait]。 因此，Audience Manager不会出于性能原因验证此表达式，因为它会使太多用户符合此条件 [!UICONTROL segment]。

* 对——如果要包含已识别ID为“1000” [!UICONTROL trait] （最多五次）的所有用户，请向表达式添加其他条件，以确保用户至少具备一 [!UICONTROL trait] 次资格：  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右——当您需要的最近／频率要求小于特定次数或天数时，请使用运算符将 [!UICONTROL trait] 该要求连接到另 `AND` 一个。 使用第一个项目符号点中的示例，当与另一个项目符号连接时，此表达式 [!UICONTROL trait] 将变为有效，如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 右——对于广告限频用例，您可以创建 [!UICONTROL segment] 类似于以下规则： `(frequency([1000T] <= 2D) >= 5)`. 此表达式包括过去2天 [!UICONTROL trait] 中已识别ID为“1000”的所有用户，至少五次。 通过将此设置发送 [!UICONTROL segment] 到广告服务器并在广告服 `NOT` 务器中设置 [!UICONTROL segment] 一个设置来设置频率上限。 该方法在仍用于频率 [!DNL Audience Manager] 上限的相同目的的同时获得更好的性能。

>[!MORELIKETHIS]
>
>* [区段生成器控件： 特征部分](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [区段表达式编辑器中使用的代码语法](../../features/segments/segment-code-syntax.md)

