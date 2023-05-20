---
description: 本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: 特征和区段生成器中的布尔表达式
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# 特征和区段生成器中的布尔表达式{#boolean-expressions-in-trait-and-segment-builder}

本文說明Audience Manager特徵和區段工具如何使用布林運算式AND、OR和NOT。

<!-- 

c_tb_boolean.xml

 -->

**布林運算式**

布林邏輯是代數的分支，會使用一些基本運算式（或運運算元）來判斷陳述式是true或false。 最常見的運運算元包括 [!UICONTROL AND]， [!UICONTROL OR]、和 [!UICONTROL NOT]. 這些運算式的組合，可協助您打造特別適合您資料需求的重點特徵或區段資格規則。 下圖顯示基本布林值運算式的運作方式。

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>此 [!UICONTROL NOT] 運運算元使用隱含的「and」條件，有時寫成 [!UICONTROL AND NOT].

**如何在特徵和區段產生器中使用布林運算式**

您可以使用布林運算式建立特徵和區段資格規則。 下表說明透過建立資格條件的一般最佳實務 [!UICONTROL AND]， [!UICONTROL OR]、和 [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 表达式 </th> 
   <th colname="col2" class="entry"> 使用它來建立 </th> 
   <th colname="col3" class="entry"> 符合資格 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 且</span></b> </p> </td> 
   <td colname="col2"> <p>狹隘、集中的對象資格要求。 </p> </td> 
   <td colname="col3"> <p>使用者 <i>必須</i> 屬於所有指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 或者</span></b> </p> </td> 
   <td colname="col2"> <p>廣泛、重點較低的對象資格需求。 </p> </td> 
   <td colname="col3"> <p>使用者 <i>可以</i> 屬於任何指定的特徵或區段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>狹隘、集中的對象資格要求。 </p> <p>當有多個條件導致定義對象資格要求困難或無效時，這個選項相當實用。 有時，根據排除而不是包含的需求進行驗證會比較容易。 </p> </td> 
   <td colname="col3"> <p>使用者 <i>不得</i> 屬於排除的特徵或區段。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]使用案例範例**

此 [!UICONTROL AND] 運運算元在輕鬆列舉特徵成員資格要求時很有用。 例如，假設您需要建立「昂貴相機購物者」的受眾。 使用畫素模型時，您必須建立並放置相機的畫素，以及頁面上的數值價格值。 相較之下，透過特徵，您可以套用布林運運算元來處理這兩個條件（相機） [!UICONTROL AND] 價格)。 如此一來，便能以較少的HTTP呼叫，有效率地收集資料，進而協助保留網站上的使用者體驗。

**[!UICONTROL OR]使用案例範例**

此 [!UICONTROL OR] 當您想要建立具有廣泛對象資格要求的訊號時，運運算元就很實用。 如果您有數個特徵或區段資格要求，則 [!UICONTROL OR] 運運算元將在您的網站訪客展示時評估為true *任何* 這些特性中的一個。 [!UICONTROL OR] 當您想要快速建立廣泛的合格網站訪客對象時，這個選項可能最有用。

**[!UICONTROL AND NOT]使用案例範例**

此 [!UICONTROL AND NOT] 運運算元在定義對象時較容易使用 *排除* 而非 *包含*. 例如，假設您正在舉辦銷售活動，且想要將訪客細分為只檢視全價專案的客戶。 與其為所有符合條件的完整或特價專案建立訊號清單，不如讓訪客更容易符合條件，如果訪客符合條件， *not* 已檢視售價專案。 這在管理上很有效率，因為相較於全價優惠，您通常擁有更少的售價專案。 使用布林值 [!UICONTROL NOT]，訪客 *不得* 展示銷售訊號，以符合全價對象會籍資格。 對比之下， [!UICONTROL AND NOT] 與 [!UICONTROL AND] 使用案例，顯示如何透過包含來判斷對象成員資格（即訪客根據2個明確指出的訊號取得資格）。

>[!MORELIKETHIS]
>
>* [在TraitBuilder中使用比較運運算元](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder運算式中的作業順序](../features/traits/trait-operator-precedence.md)

