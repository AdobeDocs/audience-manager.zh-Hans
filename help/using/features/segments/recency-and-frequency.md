---
description: 在区段生成器中，最近的时间和频率允许您根据发生的操作或重复的每日间隔对访客进行细分。
seo-description: 在区段生成器中，最近的时间和频率允许您根据发生的操作或重复的每日间隔对访客进行细分。
seo-title: 新近度和频率
solution: Audience Manager
title: 新近度和频率
uuid: faadd18a-bf27-4b73-995e-9809f52 f5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]：** 用户查看或符合一个(或更多)特征的天数。
* **[!UICONTROL Frequency]：** 用户查看或符合一个(或更多)特征的速率。

[!UICONTROL Recency][!UICONTROL Frequency] 和设置帮助您根据站点、部分或特定创意中的真实(或感知的)级别对访客进行细分。例如，符合高响度/频率要求的用户可能比访问频率更低或经常更少访问的用户更感兴趣。

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. 单击时钟图标以显示这些控件。

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

当您希望将新近和频率应用于细分中的特征时，请查看并了解这些限制和规则。

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
   <td colname="col2"> <p>最近缩进必须大于0。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方特征</b> </p> </td> 
   <td colname="col2"> <p>您无法为包含第三方特征的单个第三方特征或特征组设置新近度规则。新近度和频率仅适用于您自己的特征。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 频度

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
   <td colname="col2"> <p>您不能对包含第三方特征的个别第三方特征或特征组设置频率规则。新近度和频率仅适用于您自己的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>新近度要求</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. 只需设置一个频率值并将缩进字段保留为空即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>个人资料合并规则</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> Trait Frequency, External Device Graphs, and Profile Merge Rules</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

频率上限表达式包括其特征真实性低于所需值的所有用户。以下是一些示例：

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. 此表达式包括已在过去天内使用ID“1000”识别特征的所有用户。Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_ LIKE_ This]
>
>* [区段生成器控制：特征部分](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [区段表达式编辑器中使用的代码语法](../../features/segments/segment-code-syntax.md)

