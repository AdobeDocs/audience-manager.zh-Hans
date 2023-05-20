---
description: 目的地產生器可讓您建立Cookie型或DNL URL目的地。 您無法使用Destination Builder建立伺服器對伺服器(S2S)目的地，但您可以管理其區段對應。 請聯絡您的顧問以設定S2S目的地。 目的地產生器位在「對象資料>目的地」中。
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: 目标生成器
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 4%

---

# 目标生成器 {#destination-builder}

[!UICONTROL Destination Builder] 可讓您建立Cookie架構或 [!DNL URL] 目的地。 您無法建立伺服器對伺服器([!DNL S2S])個目的地搭配： [!UICONTROL Destination Builder]，但您可以管理其區段對應。 請聯絡您的顧問以設定 [!DNL S2S] 目的地。 [!UICONTROL Destination Builder] 位於 **[!UICONTROL Audience Data > Destinations]**.

## 目的地產生器設定 {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 包含下列區段和設定：

| [!UICONTROL Destination Builder] 区域 | 用途 |
|--- |--- |
| 基本信息 | 用來命名目的地、描述目的地及選取目的地型別([!DNL URL] 或 [!DNL cookie])和平台(全部， [!DNL Android]、瀏覽器，或 [!DNL iOS])。 |
| 配置 | 包含下列專案的控制項： <br/><ul><li>傳遞索引鍵值資料至 [!DNL URL] 目的地。 您可以個別或序列化索引鍵值配對的形式傳送資料。 如需詳細資訊，請參閱 [目的地序列化](../../features/destinations/key-value-pairs.md#destination-serialized) 和 [標準和序列索引鍵值配對](../../features/destinations/key-value-pairs.md). </li><li>Cookie目的地的元素，例如Cookie名稱、網域、大小、過期時間間隔、資料格式等。</li></ul> |
| 區段對應 | 允许您: <br/><ul><li>搜尋、新增及管理與所有目的地型別相關聯的區段。 </li><li>設定個別區段的傳遞優先順序(適用於 [!DNL cookie] — 僅限以區段為基礎)。</li></ul> |

## 資料傳送方法 {#data-delivery-methods}

透過傳遞資訊至目的地來傳送資訊 [!DNL URL] 字串，透過寫入瀏覽器 [!DNL cookie]或透過離線伺服器對伺服器資料傳輸。

* [!DNL URL] 和以Cookie為基礎的目的地，會在使用者對頁面採取動作時，同步傳輸資料。
* 伺服器對伺服器的資料傳輸為非同步處理，可在使用者離開頁面很久後發生。 您選取的傳送型別取決於您的業務需求，以及特定資料合作夥伴想要或可以如何接收資料。

另請參閱 [如何選擇目的地型別](../../features/destinations/destinations.md) 以取得詳細資訊。
