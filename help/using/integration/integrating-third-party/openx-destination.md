---
description: 將OpenX設定為目的地，並將Audience Manager區段資料傳送至該平台。
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX 作为 Audience Manager 目标
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---

# OpenX 作为 Audience Manager 目标{#openx-as-an-audience-manager-destination}

設定 [!DNL OpenX] 作為目的地，並將Audience Manager區段資料傳送至該平台。

>[!NOTE]
>
>僅用於現場廣告伺服器目標定位。

## OpenX目的地需求 {#openx-requirements}

程式碼放置標準、支援的鍵值格式、報表，以及傳送至的區段資料型別 [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

設定前請先檢閱下列內容 [!DNL OpenX] 作為Audience Manager目的地：

* **[!UICONTROL DIL]：** [!UICONTROL Data Integration Library] 程式碼應部署在您的網站上。 [!UICONTROL DIL] 協助您免除撰寫特殊程式碼以進行資料收集、整合、讀取Cookie值及復原頁面資料的需求。
* **`get_aamCookie`函式：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。 地標 [此程式碼](../../features/destinations/get-aam-cookie-code.md) 在頁面頂端或內部 `<head>` 程式碼區塊。
* **傳送傳遞記錄至Audience Manager：** 如果您想要區段傳送報表（選用），請為Audience Manager提供包含曝光層級傳送資料的每日記錄。 資料可以是原始格式，但每筆記錄都必須包含Audience Manager `UUID`. Audience Manager可以透過以下方式取得或接收這些內容： [!DNL FTP].

### 索引鍵值資料：格式需求

Audience Manager會以機碼值組的形式傳送資料。 根據下列規格建立索引鍵值配對：

* 前置詞索引鍵 `c.` (例如， `c.color` 或 `c.price`)。
* 以逗號分隔附加至單一索引鍵的序列化值(例如， `c.color = red, green, blue`)。
* 以&amp;符號分隔多個索引鍵值組(例如， `c.color=red & c.price = 100 & c.condition = new`)。
* 金鑰名稱不得包含特殊字元，例如輔音符號和標點符號或其他符號。

### 只有合格的區段才會傳送至OpenX

傳遞至的資料量 [!DNL OpenX] 視特定使用者符合的區段數量而定。 例如，假設您設定100個Audience Manager區段。 如果網站訪客符合其中五個區段的資格，則系統只會將這五個區段傳送至 [!DNL OpenX] （並非全部100個）。

## 建立OpenX目的地 {#openx-destination}

建立Cookie目的地 [!DNL OpenX] 在Audience Manager中。

<!-- aam-openx-destination.xml -->

在Audience Manager中， *目的地* 是任何其他系統(廣告伺服器、 [!DNL DSP]、廣告網路等) 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送流程的工具。 Audience Manager目的地功能位於 *受眾資料>目的地*. 若要開始使用，請按一下 **[!UICONTROL Add New Destination]** 並遵循下列步驟。

### 步驟1：基本資訊

若要完成 [!UICONTROL Basic Information] 區段：

1. 為目的地命名。
1. 選取 **[!UICONTROL "Cookie"]** 從 [!UICONTROL Type] 下拉式清單。
1. 按一下 **[!UICONTROL Next]** 並移至 [!UICONTROL Configuration] 和 [!UICONTROL Segment Mappings] 區段。

### 步驟2：設定資訊

若要完成 [!UICONTROL Configuration] 區段：

1. **Cookie名稱：** 為您的Cookie提供簡短的描述性名稱。
1. **Cookie網域：** 留空可在使用者目前頁面的網域中設定Cookie。 如果您想要指定網域，請在名稱前面加上句號，如下所示， `.mydomain.com`.
1. 在「 」中選擇一個索引鍵選項 [!UICONTROL Data Format] 區段。
1. 如果您的索引鍵使用具有序列化值的資料，請選取 **[!UICONTROL Serialize]** 控制並指定序列分隔符號（分隔序列化值的字元）。
1. 按一下 **[!UICONTROL Save]** 並展開 [!UICONTROL Segment Mappings] 區段。

### 步驟3：區段對應

若要將區段新增至Cookie目的地：

1. **尋找區段：** 此 [!UICONTROL Segment Mappings] 區段提供兩種搜尋工具來協助尋找區段。 若要搜尋區段，請執行下列步驟：
   * 選項1：開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 按一下 **[!UICONTROL Add]** 找到要使用的區段後。
   * 選項2：按一下 **[!UICONTROL Browse All Segments]** 以開啟視窗，讓您依名稱或儲存位置瀏覽區段。 按一下 **[!UICONTROL Add Selected Segments]** 完成時。
1. **新增對應：** 在對映彈出式視窗中，在對映欄位中輸入區段ID，然後按一下 **[!UICONTROL Save]**.
1. 单击 **[!UICONTROL Done]**.

## OpenX設定 {#openx-code-setup}

修改 [!DNL OpenX] 用於處理Audience Manager區段資料的設定。

<!-- aam-openx-code.xml -->

若要設定 [!DNL OpenX]：

* 安裝 [!UICONTROL DIL] 程式碼跨您的網站。
* 建立 [!DNL OpenX] 作為Audience Manager中的Cookie目的地。
* 放置 `get_aamCookie` 函式在頁面頂端，最好是在 `<head>` 程式碼區塊。 此 `get_aamCookie` 程式碼可供使用 [此處](../../features/destinations/get-aam-cookie-code.md).
* 修改您的廣告標籤以呼叫 `get_aamCookie` 函式並包含您在設定時提供的Cookie名稱 [!DNL OpenX] 目的地。 例如，如果您將Cookie `test_cookie`，則廣告標籤應呼叫 `get_aamCookie` 和參考Cookie名稱。
* 您的廣告標籤看起來可能類似於以下範例。

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

記得加入 `xid=` . 它保有實際的不重複使用者ID ([!UICONTROL UUID])在廣告呼叫期間傳入。

完整格式的廣告呼叫看起來可能類似這樣：

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
