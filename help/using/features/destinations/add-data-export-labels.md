---
description: 数据导出标签可与您在数据源上设置的导出控件配合使用。 数据导出标签会阻止您将受限制的特征添加到区段，并阻止您将区段数据发送到目标。 您可以将多个导出标签设置为新的或现有的Cookie或URL目标。
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: 将数据导出控件添加到目标
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# 将数据导出标签添加到目标 {#add-data-export-labels}

[!DNL Data Export Labels]使用您在数据源中设置的[!DNL Export Controls]。 [!DNL Data Export Labels]阻止您将受限制的特征添加到区段，阻止您将区段数据发送到目标。 您可以将多个导出标签设置为新的或现有的[!DNL cookie]或[!DNL URL]目标。

>[!NOTE]
>
>要添加导出标签，您需要具有管理员权限&#x200B;*或*&#x200B;足够的权限才能创建或编辑目标。

<!-- t_export_labels.xml -->

要将导出标签添加到目标，请执行以下操作：

1. 单击&#x200B;**[!UICONTROL Audience Data]**：
   * 对于新目标：单击&#x200B;**[!UICONTROL Create New Destination]**。 请先完成[!UICONTROL Basic Information]部分，然后再选择数据导出标签。 有关信息，请参阅[创建Cookie目标](../../features/destinations/create-cookie-destination.md)或[创建URL目标](../../features/destinations/create-url-destination.md)。
   * 对于现有目标：使用[!DNL Search]框查找您的目标，或者滚动浏览列表并单击目标名称以打开它。
1. 选择[!DNL Data Export Label]。 如果不想设置任何导出限制，请将复选框保留为空。 导出标签包括以下选项：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >除非您在数据源上设置与导出控制](../../features/data-export-controls.md)匹配的[，否则导出限制将不起作用。
1. 单击 **[!UICONTROL Save]**。

>[!MORELIKETHIS]
>
>* [创建数据源](../../features/manage-datasources.md#create-data-source)
