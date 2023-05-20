---
description: 衍生訊號會根據網站訪客已見到的特徵，讓他們符合其他特徵的資格。 換言之，即使使用者以前從未見過新特徵，也可從目前展示的特徵衍生出其他特徵資格。
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: 派生的信号
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---

# 派生的信号 {#derived-signals}

A [!UICONTROL derived signal] 根據網站訪客已看到的特徵，讓他們符合其他特徵的資格。 換言之，即使使用者以前從未見過新特徵，也可從目前展示的特徵衍生出其他特徵資格。

<!-- c_tb_derived_signal.xml -->

## 衍生訊號的用途

在 [!DNL Audience Manager]，您可以在事件呼叫其他指定訊號或特徵期間傳入的訊號（或特徵規則）之間建立關係。 例如，假設事件呼叫傳入由機碼值組成的訊號 [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`)。 [!DNL Audience Manager] 會將該訊號連線至使用 [!UICONTROL derived signals] 工具。 雖然關聯的訊號可以是您指定的任何機碼值，但是當連結至已設定為的現有訊號時，這些訊號最有用 [!UICONTROL Trait Builder] 規則。 例如，在下圖中，當使用者動作觸發訊號時 [!DNL "product = new car"] 該使用者也可符合目標索引鍵和值訊號所定義的特徵。

![](assets/derived_signal_example.png)

## 衍生訊號的位置

建立和管理 [!UICONTROL derived signals] 在 **[!UICONTROL Tools > Derived Signals]** 從側欄導覽取得。

## 建立衍生訊號 {#create}

<!-- t_tb_create_derived.xml -->

若要建立 [!UICONTROL derived signal]：

1. 選取 **[!UICONTROL Derived Signals]** 從 [!UICONTROL Tools] 功能表。
1. 提供：
   * *（可選）* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 单击 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>「 」的字元限制 [!UICONTROL Source Key]， [!UICONTROL Source Value]， [!UICONTROL Target Key]、和 [!UICONTROL Target Value] 欄位為228個字元。

## 編輯衍生訊號 {#edit}

<!-- t_tb_edit_derived.xml -->

若要編輯 [!UICONTROL derived signal]：

1. 暫留在訊號上，然後按一下 **[!UICONTROL Edit]**.
2. 進行必要的程式碼、索引鍵或值變更，然後按一下 **[!UICONTROL Save]**.

## 刪除衍生訊號 {#delete}

<!-- t_tb_delete_derived.xml -->

若要刪除 [!UICONTROL derived signal]，將游標停留在訊號上，然後按一下 **[!UICONTROL Delete]**.
