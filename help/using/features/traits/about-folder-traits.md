---
description: 資料夾特徵可讓您自動將相同資料夾和所有子資料夾中的特徵彙總到可定位的區段中。
keywords: 區段大小估算器；sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: 資料夾特徵關於
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# 文件夹特征：关于 {#folder-traits-about}

[!UICONTROL Folder traits] 可讓您將相同資料夾和所有子資料夾中的特徵自動彙總到可定位的區段中。

## 使用資料夾特徵的好處 {#benefits}

A [!UICONTROL folder trait] 包含父資料夾及其相關子資料夾中的所有特徵。 這可讓您在不同資料夾層級自動劃分及鎖定使用者。 例如，假設您的資料夾結構如下：

`*` 電子產品（母公司）

    `*` 筆記型電腦（兒童）

        `*` 品牌（孫子）

[!UICONTROL Folder traits] 在自動建立的資料夾中限定這些資料夾中的所有使用者 [!DNL Electronics] [!UICONTROL Folder Trait] （根據上層資料夾的名稱）。 而且，當您向下移動檔案結構時，此程式會自我重複。 在此案例中，資料夾特徵會擷取自動建立之筆記型電腦中Laptops和Brands資料夾中的所有使用者 [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] 區段運算式中可選取。 選取 [!UICONTROL folder trait] 等同於使用「 」選取該資料夾及其子資料夾中的所有特徵 [!UICONTROL OR] 分組。

![](assets/folder-traits-compare-border.jpg)

## 資料夾特徵實現 — 造訪間隔和頻率 {#folder-traits-realization}

資料夾特徵的頻率計數是其資料夾及其子資料夾中特徵的實現總和。 下圖顯示特徵A、B和C，它們位於Automobile資料夾中。 假設每個特徵皆有下列實現專案：

* 特徵A：5個
* 特徵B： 1
* 特徵C：1

在此案例中， [!DNL Automobile Folder Trait] 有7項實現專案。

![](assets/folder_traits_rollup_border.png)

## 資料夾特徵報告 {#folder-traits-reporting}

[!UICONTROL Folder traits] 從下方資料夾結構中的特徵中擷取所有使用者。 如果您將特徵從某個資料夾移至另一個資料夾，則變更會傳播至 [資料收集伺服器](../../reference/system-components/components-data-collection.md) 就像特徵規則變更一樣。 下一個報表執行中的報表會更新，以反映報表日期範圍(1、7、14、30、60、90)中的這項變更。 過去幾天的舊報告數字不會變更。

## 角色型存取控制(RBAC)許可權 {#role-based-access-controls}

針對使用 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])，則您的使用者需具備適當的 [!UICONTROL RBAC] 許可權可以變更與關聯的資料來源 [!UICONTROL folder trait]. 使用者必須屬於具有下列其中一項的群組：

* `READ` 和 `WRITE` 特徵資料來源的群組許可權。
* `VIEW_ALL_TRAITS` 和 `EDIT_ALL_TRAITS` 特徵資料來源的萬用字元許可權。

瞭解如何指派 [!UICONTROL RBAC] 中的許可權 [管理檔案](../../features/administration/administration-overview.md#create-group).

## 限制和其他考量事項 {#limits}

| 项目 | 描述 |
|---|---|
| 特徵型別 | [!UICONTROL Onboarded traits] 和 [!UICONTROL algorithmic traits] 最多可貢獻1個實現目標 [!UICONTROL folder trait]的頻率。 |
| 在資料夾之間移動特徵 | 將特徵從某個資料夾移至另一個資料夾，會使該特徵失去第一個資料夾特徵的資格，並失去第二個資料夾特徵的資格 [!UICONTROL folder trait]. 這表示如果您從資料夾中刪除或移動特徵，該特徵母體中的使用者將會使用資料夾特徵作為區段運算式而從區段中取消分段。 <br> 將Adobe Analytics區段或報表套裝對應至您的Experience Cloud組織時，Audience Manager會自動建立對應的新唯讀區段和特徵。 您無法從Audience Manager編輯或變更這些特徵的儲存位置。 不過，您在對應之Adobe Analytics區段或報表套裝上執行的任何變更都會反映在Audience Manager中。 |
| 系統變數 | [!UICONTROL Folder traits] 無法在事件呼叫中使用 `d_sid` 引數。 |
| 报表 | [!UICONTROL Folder traits] 是自動計算的特徵，不會出現在 **[!UICONTROL Overlap Reports]**. |
