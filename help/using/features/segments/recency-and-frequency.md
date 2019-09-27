---
description: 在“区段生成器”中，最近和频率允许您根据在设定的每日间隔内发生或重复的操作对访客进行区段划分。
seo-description: 在“区段生成器”中，最近和频率允许您根据在设定的每日间隔内发生或重复的操作对访客进行区段划分。
seo-title: 近况和频率
solution: Audience Manager
title: 近况和频率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c7e8b67ccad4479487b471668462937c5be6be34

---


# Recency and Frequency {#recency-and-frequency}

在 [!UICONTROL Segment Builder]最近和频率中，您可以根据在设定的每日间隔内发生或重复的操作对访客进行细分。

Audience manager定义 [!DNL recency] 如 [!DNL frequency] 下：

* **[!UICONTROL Recency]** :用户最近查看或符合一个（或多个）特征的资格。
* **[!UICONTROL Frequency]** :用户查看或限定一个（或多个）特征的速率。

[!UICONTROL Recency] 并且 [!UICONTROL Frequency] 这些设置可帮助您根据访客对网站、区域或特定创意的真实（或感知）兴趣级别对访客进行细分。 例如，符合最近／频率要求较高的细分的用户对网站或产品的兴趣可能高于访问频率较低或访问频率较低的用户。

## 最近和频率设置的位置 {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings位于面板 [!UICONTROL Basic View] 的部分 [!UICONTROL Traits] 中。 单击时钟图标以显示这些控件。

![](assets/recency_frequency.png)

## 限制和规则 {#limitations-rules}

当您希望将近期情况和频率应用于区段中的特征时，请查看并了解这些限制和规则。

### 近期情况

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
   <td colname="col2"> <p>最近的时间必须大于0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>You cannot set recency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 频度

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>You cannot set frequency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>近期要求</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements without configuring recency requirements. <i></i>只需设置一个频率值，并将最近使用的字段留空即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Profile Merge Rules</b> </p> </td> 
   <td colname="col2"> <p>See  Trait Frequency, External Device Graphs, and Profile Merge Rules.<a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"></a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Recency Examples {#recency-examples}

Here are two examples of how recency works, depending on your selection in the UI:

### Using a less than or equal to operator (&lt;=)

![Less-than-equal-to](assets/less-than-equal-to.png)

In this example, you select the &lt;= operator, as shown in the screenshot. 如果用户在过去5天内至少有3次符合这3个特征中任意一个的特征，则这将使您有资格获得区段。 以下时间线显示创建区段时的区段资格（10月1日和10天后）。

![最近5天](assets/last-5-days.png)

### 使用大于或等于运算符(=&gt;)

![大于等于](assets/greater-than-equal-to.png)

在此示例中，您选择=&gt;运算符，如屏幕截图所示。 如果用户在Audience manager平台上首次获得资格，并且在五天前中断时间之间，至少有三次符合以下三个特征之一的资格，则这将使用户有资格进入区段。 以下时间线显示创建区段时的区段资格（10月1日和10天后）。

![早期资格](assets/earlier-qualification.png)


## 频率上限示例 {#frequency-capping}

频率上限表达式包括其特征实现数量低于所需值的所有用户。 以下是几个示例：

* 该表达 `frequency([1000T]) <= 5` 式包括已实现ID为“1000”且最多五次的特征的所有用户，包括尚未实现该特征的用户。
* 当您需要的最近／频率要求小于特定次数或天数时，请使用运算符将该特征连接到另一个特 `AND` 征。 使用上面的示例，当与其他特征连接时，此表达式将变为有效，如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 对于广告限频使用案例，您可以创建类似于以下内容的细分规则： `(frequency([1000T] <= 2D) >= 5)`. 此表达式包括在过去2天内至少5次使用ID“1000”实现该特征的所有用户。 通过将此区段发送到广告服务器并在广告服务器中的 `NOT` 区段上设置一组，来设置频率限制。 该方法在仍用于频率 [!DNL Audience Manager] 上限的相同用途的同时获得了更好的性能。

>[!MORE_LIKE_THIS]
>
>* [区段生成器控件：特征部分](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [段表达式编辑器中使用的代码语法](../../features/segments/segment-code-syntax.md)

