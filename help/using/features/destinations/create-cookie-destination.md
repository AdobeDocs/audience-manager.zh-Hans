---
description: Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含其他可存取頁面的平台可讀取的資料。 依照下列指示，使用建立Cookie目的地 [!UICONTROL Destination Builder].
seo-description: A cookie destination returns and writes data to a cookie in the user's browser. The cookie contains data that can be read by other platforms that have access to the page. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].
seo-title: Configure a Cookie Destination
solution: Audience Manager
title: 配置 Cookie 目标
feature: Destination Basics
exl-id: 32b8de66-e12d-48ec-82cf-9b0d335ae834
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 3%

---

# 配置 Cookie 目标 {#create-cookie-destination}

Cookie目的地會傳回資料，並將資料寫入使用者瀏覽器中的Cookie。 Cookie包含其他可存取頁面的平台可讀取的資料。 依照下列指示，使用建立Cookie目的地 [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

若要建立新的Cookie目的地，請前往 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 並完成以下所述的章節。

## 基本信息 {#basic-information}

本節包含啟動Cookie目的地建立程式的欄位和選項。 若要完成本節：

1. 按一下 **[!UICONTROL Basic Information]** 以公開控制項。
2. 命名目标。 避免缩写和特殊字符。
3. *（可选）* 描述目标。 简要描述是定义或提供有关目标的详细信息的有效方法。
4. **[!UICONTROL Category]**&#x200B;在列表中，选择 **[!UICONTROL Custom]** 。
5. 在 **[!UICONTROL Environment]** 清單，選取 **[!UICONTROL Browser]**. 您無法為原生行動環境(例如Android或iOS應用程式)設定Cookie目的地。
6. **[!UICONTROL Type]**&#x200B;在列表中，单击 **[!UICONTROL Cookie]** 。
7. *（可选）***[!UICONTROL Auto-fill Destination Mapping]**&#x200B;选择。选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段 ID 并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**：自动添加区段集成代码并将其发送到目标映射。 集成代码是由客户创建和使用的唯一标识符。 最高可超过255个字符。
8. 按一下 **[!UICONTROL Next]** 前往 [!UICONTROL Configuration] 設定或按一下 **[!UICONTROL Data Export Labels]** 將匯出控制項套用至目的地。

## 資料匯出標籤 {#data-export-labels-cookies}

本節包含套用的選項 [資料匯出控制](../../features/data-export-controls.md) 至Cookie目的地。 如果您不使用資料匯出控制項，請略過此步驟。 若要完成本節：

1. 单击 **[!UICONTROL Data Export Labels]** 以公开控件。
2. 選取與套用至目的地的資料匯出控制對應的標籤(請參閱 [將匯出標籤新增至目的地](/help/using/features/destinations/add-data-export-labels.md) 以取得詳細資訊)。
3. 单击 **[!UICONTROL Save]**.

## 配置 {#configuration}

本節包含可讓您為目的地設定Cookie的欄位和選項。

>[!NOTE]
>
>[!DNL Audience Manager] 對寫入目的地Cookie的資料進行編碼。 例如，空格會編碼為 `%20` 和分號編碼為 `%3B`.

要完成此部分：

1. 单击 **[!UICONTROL Configuration]** 以公开控件
1. 為Cookie命名。 避免使用縮寫和特殊字元。
1. 選擇資料格式選項。 這些選項可讓您為將區段資料傳送至目的地的機碼值組選擇分隔符號和分隔符號。 格式選項包括：
   * **单键值：** 允许您在键值对中设置键。 在下面的 [!UICONTROL Segment Mappings] 部分中选择区段后，您将设置该值。
   * **多键：** 用于设置键值对的键和值。 在下面的 &quot;区段映射&quot; 部分中选择区段后，您将创建键值对。有关这些数据元素的详细信息，请参阅 [ 标准和串行键值对 ](../../features/destinations/key-value-pairs.md) 。
1. 单击 **[!UICONTROL Save]**.

所有其他设置都是可选的。 有关和 **[!UICONTROL Publish data to]** 设置的详细信息 **[!UICONTROL Cookie Domain]** ，请参阅 [ Cookie 目标 ](/help/using/features/destinations/cookie-destination-options.md) 的可选设置。

## 區段對應 {#segments-mapping}

此區段可讓您搜尋區段並將區段新增至您的目的地。 若要完成本節：

1. 按一下 **[!UICONTROL Segment Mappings]** 以公開控制項。
1. 在 **[!UICONTROL Search and Add Segments]** 方塊中，開始輸入區段名稱或按一下 **[!UICONTROL Browse All Segments]** 以瀏覽可用區段的清單。
1. 在找到要使用的区段时单击 **[!UICONTROL Add Selected Segments]** 。 新增區段會開啟 [!UICONTROL Edit Mapping] 視窗。
1. [!UICONTROL Edit Mapping]在对话框中：
   * **[!UICONTROL Mapping]** 可为上述 &quot;配置&quot; 部分中指定的键值设置值。
   * **[!UICONTROL Publish from]** 可讓您設定目的地的開始和結束日期。 如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Save]**.
1. 单击 **[!UICONTROL Done]**.
