---
description: 数据导出标签与您在数据源上设置的导出控件配合使用。 数据导出标签阻止您向区段添加受限特征以及向目标发送区段数据。 您可以将多个导出标签设置到新的或现有的cookie或URL目标。
seo-description: 数据导出标签与您在数据源上设置的导出控件配合使用。 数据导出标签阻止您向区段添加受限特征以及向目标发送区段数据。 您可以将多个导出标签设置到新的或现有的cookie或URL目标。
seo-title: 将数据导出控件添加到目标
solution: Audience Manager
title: 将数据导出控件添加到目标
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---



# 将数据导出标签添加到目标{#add-data-export-labels}

[!DNL Data Export Labels] 使用您在 [!DNL Export Controls] 数据源上设置的。[!DNL Data Export Labels] 阻止您向区段添加受限特征，以及向目标发送区段数据。可以将多个导出标签设置为新的或现有的[!DNL cookie]或[!DNL URL]目标。

>[!NOTE]
>
>要添加导出标签，您需要管理员权限&#x200B;*或*&#x200B;足够的权限才能创建或编辑目标。

<!-- t_export_labels.xml -->

要将导出标签添加到目标：

1. 单击 **[!UICONTROL Audience Data]**:
   * 对于新目标：单击&#x200B;**[!UICONTROL Create New Destination]**。 在选择数据导出标签之前，请完成[!UICONTROL Basic Information]部分。 有关信息，请参阅[创建Cookie目标](../../features/destinations/create-cookie-destination.md)或[创建URL目标](../../features/destinations/create-url-destination.md)。
   * 对于现有目标：使用[!DNL Search]框查找目标，或滚动浏览列表并单击目标名称以打开它。
1. 选择 [!DNL Data Export Label]. 如果不想设置任何导出限制，请将复选框留空。 导出标签包含以下选项：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >除非对数据源设置[匹配的导出控件](../../features/data-export-controls.md)，否则导出限制将无效。
1. 单击 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [创建数据源](../../features/manage-datasources.md#create-data-source)