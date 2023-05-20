---
description: 在区段生成器中，最近交易和频度允许您根据每日设置的时间间隔来区段访客。
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: 回访间隔和频度
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 2%

---

# 回访间隔和频度 {#recency-and-frequency}

在中 [!UICONTROL Segment Builder] ，最近交易和频度可让您根据每日设置的时间间隔来区段访客。

Audience Manager 定义 [!DNL recency] ， [!DNL frequency] 如下所示：

* **[!UICONTROL Recency]：** 最近用户查看或限定一个（或多个） [!UICONTROL traits] 的方式。
* **[!UICONTROL Frequency]：** 一种（或多） [!UICONTROL traits] 用户查看或限定的速度。

[!UICONTROL Recency] 和 [!UICONTROL Frequency] 设置可帮助您根据网站、区域或特定创意中的真实（或感知）级别的兴趣来区段访客。 例如，符合最近交易/频度要求的区段的用户可能比访问少或少的用户更感兴趣的网站或产品。

## [!UICONTROL Recency and Frequency]设置位置 {#location}

在中 [!UICONTROL Segment Builder] ， [!UICONTROL Frequency] [!UICONTROL Recency] 设置位于面板的区域 [!UICONTROL Traits] 中 [!UICONTROL Basic View] 。按一下時鐘圖示以公開這些控制項。

![](assets/recency_frequency.png)

## 限制和規則 {#limitations-rules}

當您想要將造訪間隔和頻率套用至區段中的特徵時，請檢閱並瞭解這些限制和規則。

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 限制或規則 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>最小值</b> </p> </td> 
   <td colname="col2"> <p>造訪間隔必須大於0。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>特徵型別</b> </p> </td> 
   <td colname="col2"> <p>您只能將造訪間隔控制項套用至規則型和資料夾特徵。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>第三方特徵</b> </p> </td> 
   <td colname="col2"> <p>您無法針對個別第三方特徵或包含第三方特徵的特徵群組設定造訪間隔規則。 造訪間隔和頻率僅適用於您自己的特徵。 </p> </td> 
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
   <td colname="col2"> <p>您无法在包含第三方特征的单个第三方特征或特征组上设置频度规则。 回访间隔和频度仅适用于您自己的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>特征类型</b> </p> </td> 
   <td colname="col2"> <p>您只能将频度控件应用于基于规则和文件夹特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>回访间隔要求</b> </p> </td> 
   <td colname="col2"> <p>您可以在不配置最近交易要求的情况下 </i> 配置频度要求 <i> 。只需设置频度值，并将最近交易字段保留为空。 </i></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>配置文件合并规则</b> </p> </td> 
   <td colname="col2"> <p>请参阅 <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 特征频率、外部设备图和配置文件合并规则 </a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 造訪間隔範例 {#recency-examples}

以下是「造訪間隔」運作方式的兩個範例，視您在UI中的選取專案而定：

### 使用小於或等於運運算元(&lt;=)

![小於等於](assets/less-than-equal-to.png)

在此範例中，您選取&lt;=運運算元，如熒幕擷圖所示。 這會將您的使用者授予 [!UICONTROL segment] 如果他們符合其中任何一項 [!UICONTROL traits] 過去五天內至少三次。 以下時間軸顯示 [!UICONTROL segment] 當時的資格 [!UICONTROL segment] 10月1日及10天後建立。

![最近–5天](assets/last-5-days.png)

### 使用大於或等於運運算元(=>)

![大於等於](assets/greater-than-equal-to.png)

在此範例中，您選取=>運運算元，如熒幕擷圖所示。 這會將您的使用者授予 [!UICONTROL segment] 如果他們符合其中任何一項 [!UICONTROL traits] 從Audience Manager平台上的首次資格取得到五天前的截止時間，至少要間隔三次。 以下時間軸顯示 [!UICONTROL segment] 當時的資格 [!UICONTROL segment] 10月1日及10天後建立。

![早期限定](assets/earlier-qualification.png)


## 频率上限示例 {#frequency-capping}

Frequency-上限表达式包含其 realizations 数目 [!UICONTROL trait] 低于所需值的所有用户。 以下是一些错误的正确示例：

* 错误-表达式 `frequency([1000T]) <= 5` 包括已实现 [!UICONTROL trait] ID 为 &quot;1000&quot; 的所有用户，最多可包含5次，但还包括尚未实现的 [!UICONTROL trait] 用户。 因此，Audience Manager不會基於效能原因驗證此運算式，因為它將讓太多使用者符合 [!UICONTROL segment].

* 如果您想要包括已 [!UICONTROL trait] 使用 ID &quot;1000&quot; 的所有用户，最多为5次，请在表达式中添加其他条件，以确保用户至少符合 [!UICONTROL trait] 一次：  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 正確 — 當您需要時近/頻率要求小於特定次數或天數時，請加入該要求 [!UICONTROL trait] 至另一個具有 `AND` 運運算元。 使用第一個專案符號中的範例，此運算式在與其他專案符號連結時就會變成有效 [!UICONTROL trait] 如下所示： `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 正確 — 針對廣告頻率限定使用案例，您可以建立 [!UICONTROL segment] 類似以下的規則： `(frequency([1000T] <= 2D) >= 5)`. 此運算式包含所有已實現 [!UICONTROL trait] ID為「1000」且在過去2天內至少五次。 透過傳送此設定頻率上限 [!UICONTROL segment] 至廣告伺服器，並附上 `NOT` 設定於 [!UICONTROL segment] 在廣告伺服器中。 此方法可提升以下專案的效能： [!DNL Audience Manager] 同時仍提供相同的頻率上限用途。

>[!MORELIKETHIS]
>
>* [區段產生器控制項：特徵區段](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [区段表达式编辑器中使用的代码语法](../../features/segments/segment-code-syntax.md)

