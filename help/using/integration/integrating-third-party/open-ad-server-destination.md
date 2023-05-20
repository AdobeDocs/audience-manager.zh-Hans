---
description: 將Open Ad Server設定為目的地，並將Audience Manager資料傳送至該平台。
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS 作为 Audience Manager 目标
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 4%

---

# OAS 作为 Audience Manager 目标 {#oas-as-an-audience-manager-destination}

設定 [!DNL Open Ad Server] 作為目的地，並將Audience Manager資料傳送至該平台。

## OAS目的地需求 {#oas-requirements}

程式碼放置標準、支援的鍵值格式、報表，以及傳送至的區段資料型別 [!DNL OAS].

<!-- aam-oas-requirements.xml -->

此目的地型別需要下列專案：

* **[!UICONTROL DIL]：** [!UICONTROL Data Integration Library] 程式碼應部署在您的詳細目錄上。 [!UICONTROL DIL] 協助您免除撰寫特殊程式碼以進行資料收集、整合、讀取Cookie值及復原頁面資料的需求。
* **`get_aamCookie`函式：** 擷取Audience Manager使用者ID和Cookie資料的程式碼。 地標 [此程式碼](../../features/destinations/get-aam-cookie-code.md) 在頁面頂端或內部 `<head>` 程式碼區塊。
* **将提交日志发送到 Audience Manager：** 如果您希望区段投放报表（可选），请在每日日志中提供包含印象级别投放数据的 Audience Manager。 数据可以位于原始格式中，但每个记录必须包含 Audience Manager [!UICONTROL UUID] 。 Audience Manager 可以通过 [!DNL FTP] 获取或接收这些信息。

### Cookie格式和索引鍵值資料

Audience Manager可以傳送區段資料至瀏覽器Cookie，如下所示：

* 單一索引鍵(`x=1&x=2`)；
* 多個索引鍵(`x=1&x=2&y=3&y=4`)；
* 序列化值（ `x=1,2,3` ）;
* 用于分隔各个键值对的标准值分隔符。

### 仅向 OAS 发送合格的区段

传入 [!DNL OAS] 的数据量取决于特定用户有多少个区段。 例如，假设您设置了 100 Audience Manager 区段。 如果网站访客符合其中的五个，则仅将这五个区段发送到 OAS （不是全部100）。

>[!MORELIKETHIS]
>
>* [get_aamCookie 代码](../../features/destinations/get-aam-cookie-code.md)
>* [键值对说明](../../reference/key-value-pairs-explained.md)


## 建立OAS目的地 {#oas-dest-setup}

建立Cookie型目的地 [!DNL OAS] 在Audience Manager中。

<!-- aam-oas-destination-setup.xml -->

在Audience Manager中， *目的地* 是任何其他系統(廣告伺服器、 [!DNL DSP]、廣告網路等) 任何其他系统（广告服务器、DSP、广告网络等）。[!UICONTROL Destination Builder] 提供可讓您建立和管理這些資料傳送流程的工具。 Audience Manager目的地功能位於 *受眾資料>目的地*. 若要開始使用，請按一下 **[!UICONTROL Add New Destination]** 並遵循下列步驟。

### 步驟1：基本資訊

若要完成 [!UICONTROL Basic Information] 區段：

1. 為目的地命名。
1. 選取 **[!UICONTROL "Cookie"]** 從 [!UICONTROL Type] 下拉式清單。
1. 单击 **[!UICONTROL Save]** 并移动到 &quot;&quot; 和 [!UICONTROL Segment Mappings] &quot;&quot; [!UICONTROL Configuration] 部分。

### 步骤2：配置信息

若要完成 [!UICONTROL Configuration] 區段：

1. **Cookie名稱：** 為您的Cookie提供簡短的描述性名稱。
1. **Cookie網域：** 留空可在使用者目前頁面的網域中設定Cookie。 如果您想要指定網域，請在名稱前面加上句號，如下所示， `.mydomain.com`.
1. 在部分中 [!UICONTROL Data Format] 选择一个键选项。
1. 如果您的键使用序列化值的数据，请选择 **[!UICONTROL Serialize]** 控件并指定序列分隔符（分隔序列化值的字符）。
1. 单击 **[!UICONTROL Save]** 并展开该 [!UICONTROL Segment Mappings] 区域。

### 步骤3：区段映射

向 Cookie 目标添加区段：

1. **查找区段：** 此 [!UICONTROL Segment Mappings] 部分提供了两个用于帮助查找区段的搜索工具。 若要搜尋區段，請執行下列步驟：
   * 選項1：開始在搜尋欄位中輸入區段名稱。 欄位會根據文字自動更新。 按一下 **[!UICONTROL Add]** 找到要使用的區段後。
   * 選項2：按一下 **[!UICONTROL Browse All Segments]** 以開啟視窗，讓您依名稱或儲存位置瀏覽區段。 按一下 **[!UICONTROL Add Selected Segments]** 完成時。
1. **添加映射：** 在映射 pop 中，在 &quot;映射&quot; 字段中输入区段 ID，然后单击 **[!UICONTROL Save]** 。
1. 单击 **[!UICONTROL Done]**.

## OAS設定 {#oas-code-setup}

修改 [!DNL OAS] 用於處理Audience Manager區段資料的設定。

<!-- aam-oas-code.xml -->

若要設定 [!DNL OAS]

* 安裝 [!UICONTROL DIL] 程式碼跨您的網站。
* 將OAS建立為Audience Manager中的Cookie目的地。
* `get_aamCookie`将函数放在页面的顶部，理想情况下是 `<head>` 在 codeblock 中。`get_aamCookie`代码可在此处 ](../../features/destinations/get-aam-cookie-code.md) 使用 [ 。
* 修改广告标记，以调用 `get_aamCookie` 函数并包含您在设置 [!DNL OAS] 目标时提供的 Cookie 名称。 例如，如果您命名了 Cookie `test_cookie` ，则广告标记应调用 `get_aamCookie` 并引用 Cookie 名称。
* 您的广告标记可能与下面的示例类似。

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

请记住包含 `u=` 变量。 它包含广告调用中传递的实际唯一用户 ID （ [!UICONTROL UUID] ）。
