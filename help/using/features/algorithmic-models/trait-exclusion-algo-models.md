---
description: 「特徵排除」在模型工作流程中提供額外的控制項，可讓您根據您的領域專業知識及法規要求，在模型上新增必要的護欄。 使用「排除」選項，選取從一或多個資料來源建立模型時要忽略的特徵。
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: 演演算法模型特徵排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 1%

---

# 相似人群拓展建模：特征排除 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在您的模型化工作流程中提供其他控制項，讓您根據您的領域專業知識與法規要求，在模型上新增必要的護欄。 使用 [!UICONTROL Exclusions] 選項來選取從一或多個資料來源建立模型時要忽略哪些特徵。

## 用例 {#use-cases}

以下是可協助解決的一些使用案例 [!UICONTROL Trait Exclusion]：

* [!UICONTROL Trait Exclusion] 可讓您排除某些全包特徵，例如網站訪客特徵，這樣就不會偏向模型，導致結果持平。
* 您可以從資料來源中移除您不瞭解或不信任的特徵，以更能瞭解具影響力的特徵。
* 您可以排除某些特徵（例如人口統計特徵），以協助履行您可能承擔的任何法規遵循義務。

>[!IMPORTANT]
>
>第三個使用案例的重要注意事項。 如果第三方資料提供者將新的人口統計特徵新增至資料摘要 *建立模型之後*，則模型會自動擷取特徵。 建立模型後，您無法從建模中排除特徵。 另請參閱 [重要方面和限制](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). 使用此功能時請務必小心，並與資料提供者合作，確保您會獲悉摘要結構有任何變更。

![](assets/lam_exclude_traits.png)

## 如何使用特徵排除 {#how-to-use}

使用 [建立模型](../../features/algorithmic-models/create-model.md#build-model) 建立新演演算法模型的工作流程。

1. 此 [!UICONTROL Exclusions] 選取範圍會呈現灰色，直到您選取一或多個資料來源進行模型化為止。
2. 選取一或多個資料來源進行模型化之後，按下 **[!UICONTROL Browse All Traits]**.
3. 在 **[!UICONTROL Select Traits to Exclude]** 視窗中，您可以看到與您先前選取的資料來源相關聯的所有特徵。 選取您要排除的特徵。
4. 您可以依特徵型別、特徵母體型別來篩選特徵([裝置ID](../../reference/ids-in-aam.md) 和 [跨裝置ID](../../reference/ids-in-aam.md))，或者您可以瀏覽特徵資料夾。 請注意，特徵資料夾只會顯示與您所選資料來源相關聯的特徵。
5. 按下 **[!UICONTROL Exclude Selected Traits]**.

![特徵排除](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>您可以排除整個資料夾，方法是排除資料夾特徵，而非逐一排除資料夾中的特徵。 例如，在具有20個特徵的資料夾中，您只需要排除資料夾特徵，而不必逐一排除所有特徵。

如果您偏好教學課程影片，請觀看我們的特徵排除影片示範：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

此外，請觀看以下影片，詳細瞭解跨裝置量度的運作方式。

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## 重要方面和限制 {#important-aspects-and-limitations}

請注意以下相關的方面和限制 [!UICONTROL Trait Exclusion]：

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>模型摘要檢視中排除的特徵 </p> </td>
   <td colname="col2"> <p>排除的特徵 <i>不顯示</i> 在「模型摘要」檢視中。 您只能在 <b><span class="uicontrol"> 編輯模型</span></b> 工作流程。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>角色型存取控制(RBAC) </p> </td>
   <td colname="col2"> <p>請注意，下列對使用的公司的限制 <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>： </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">如果您無權檢視特徵，請 <i>無法</i> 選取要從模型中排除的特徵。 </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">如果您無權檢視特徵，請 <i>無法</i> 檢視排除的特徵清單中的特徵。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>儲存模型後修改排除的特徵 </p> </td>
   <td colname="col2"> <p>建立並儲存模型後，就無法修改已排除的特徵。 如果您想要調整結果，可以複製模型並變更排除的特徵。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可排除的特徵數量上限 </p> </td>
   <td colname="col2"> <p>您可從模型中排除的特徵數量上限為500。 使用資料夾特徵來最大化您的排除專案。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基線特徵 </p> </td>
   <td colname="col2"> <p>基線特徵預設為排除，因此不會顯示在 <b><span class="uicontrol"> 排除專案</span></b> 清單，在建立模型時。 </p> </td>
  </tr>
 </tbody>
</table>

請觀看以下影片，瞭解如何以及為何要從排除特定特徵 [!UICONTROL Look-Alike Model].

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 相關連結

* [關於演演算法特徵](/help/using/features/algorithmic-models/understanding-models.md)
* [特徵排除 — 教學課程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
