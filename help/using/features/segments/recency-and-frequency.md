---
description: 在“区段生成器”中，最近和频率允许您根据在设定的每日间隔内发生或重复的操作对访客进行区段划分。
seo-description: 在“区段生成器”中，最近和频率允许您根据在设定的每日间隔内发生或重复的操作对访客进行区段划分。
seo-title: 近况和频率
solution: Audience Manager
title: 近况和频率
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

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
   <td colname="col1"> <p> <b>特征类型</b> </p> </td> 
   <td colname="col2"> <p>您只能将最近使用的控制应用于基于规则和文件夹的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方特征</b> </p> </td> 
   <td colname="col2"> <p>不能为包含第三方特征的个人第三方特征或特征组设置近期规则。 最近和频率仅适用于您自己的特征。 </p> </td> 
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
   <td colname="col2"> <p>不能为包含第三方特征的个人第三方特征或特征组设置频率规则。 最近和频率仅适用于您自己的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特征类型</b> </p> </td> 
   <td colname="col2"> <p>您只能将频率控制应用于基于规则的特征和文件夹特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>近期要求</b> </p> </td> 
   <td colname="col2"> <p>您可以配置频率要求， <i>而无需配</i> 置最近的要求。 只需设置一个频率值，并将最近使用的字段留空即可。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>个人资料合并规则</b> </p> </td> 
   <td colname="col2"> <p>请参 <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 阅特征频率、外部设备图形和配置文件合并规则</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 近期示例 {#recency-examples}

以下是最近如何工作的两个示例，具体取决于您在UI中的选择：

### 使用小于或等于运算符(&lt;=)

![不等于](assets/less-than-equal-to.png)

在此示例中，您选择&lt;=运算符，如屏幕截图所示。 如果用户在过去5天内至少有3次符合这3个特征中任意一个的特征，则这将使您有资格获得区段。 以下时间线显示创建区段时的区段资格（10月1日和10天后）。

![最近5天](assets/last-5-days.png)

### 使用大于或等于运算符(=&gt;)

![大于等于](assets/greater-than-equal-to.png)

在此示例中，您选择=&gt;运算符，如屏幕截图所示。 如果用户在Audience manager平台上首次获得资格，并且在五天前中断时间之间，至少有三次符合以下三个特征之一的资格，则这将使用户有资格进入区段。 以下时间线显示创建区段时的区段资格（10月1日和10天后）。

![早期资格](assets/earlier-qualification.png)


## 频率上限示例 {#frequency-capping}

频率上限表达式包括其特征实现数量低于所需值的所有用户。 以下是一些正确和错误的示例：

* 错误——表达式 `frequency([1000T]) <= 5` 包括已实现ID为“1000”且最多五次的特征的所有用户，但还包括尚未实现该特征的用户。 因此，Audience manager不会出于性能原因验证此表达式，因为它会使太多用户符合此区段的条件。

* 对——如果要包含已实现ID为“1000”且最多为5次的特征的所有用户，请向表达式添加另一个条件，以确保用户至少符合该特征一次：  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 右——当您需要的最近／频率要求小于特定次数或天数时，使用运算符将该特征连接到另一个特 `AND` 征。 使用第一个项目符号点中的示例，此表达式在与另一个特征连接时变为有效，如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 对——对于广告限频用例，您可以创建与以下内容类似的细分规则： `(frequency([1000T] <= 2D) >= 5)`. 此表达式包括在过去2天内至少5次使用ID“1000”实现该特征的所有用户。 通过将此区段发送到广告服务器并在广告服务器中的 `NOT` 区段上设置一组，来设置频率限制。 该方法在仍用于频率 [!DNL Audience Manager] 上限的相同用途的同时获得了更好的性能。

>[!MORELIKETHIS]
>
>* [区段生成器控件：特征部分](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [段表达式编辑器中使用的代码语法](../../features/segments/segment-code-syntax.md)

