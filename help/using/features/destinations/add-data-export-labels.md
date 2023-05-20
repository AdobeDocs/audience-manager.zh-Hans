---
description: 「資料匯出標籤」可與您在資料來源上設定的「匯出控制」搭配使用。 「資料匯出標籤」可防止您將受限制的特徵新增至區段，以及防止將區段資料傳送至目的地。 您可以將多個匯出標籤設定為新的或現有的Cookie或URL目的地。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: 将数据导出控件添加到目标
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 6%

---

# 將資料匯出標籤新增至目的地 {#add-data-export-labels}

[!DNL Data Export Labels] 使用 [!DNL Export Controls] 您在資料來源上設定。 [!DNL Data Export Labels] 無法新增受限制的特徵至區段，也無法傳送區段資料至目的地。 您可以將多個匯出標籤設定為新的或現有的 [!DNL cookie] 或 [!DNL URL] 目的地。

>[!NOTE]
>
>若要新增匯出標籤，您需要管理員許可權 *或* 有足夠的許可權可建立或編輯目的地。

<!-- t_export_labels.xml -->

若要將匯出標籤新增至目的地：

1. 单击 **[!UICONTROL Audience Data]**:
   * 針對新目的地：按一下 **[!UICONTROL Create New Destination]**. 完成 [!UICONTROL Basic Information] 區段，然後再選取資料匯出標籤。 另請參閱 [建立Cookie目的地](../../features/destinations/create-cookie-destination.md) 或 [建立URL目的地](../../features/destinations/create-url-destination.md) 以取得相關資訊。
   * 針對現有目的地：使用 [!DNL Search] 方塊以尋找您的目的地，或捲動清單並按一下目的地名稱以開啟。
1. 选择 [!DNL Data Export Label]. 如果您不想設定任何匯出限制，請將核取方塊保留空白。 匯出標籤包含以下選項：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >除非您設定 [符合匯出控制](../../features/data-export-controls.md) 在資料來源上。
1. 单击 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [创建数据源](../../features/manage-datasources.md#create-data-source)

