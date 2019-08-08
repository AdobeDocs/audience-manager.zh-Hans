---
description: 数据导出标签使用您在数据源上设置的导出控件。数据导出标签可防止您向区段添加受限特征，并将区段数据发送到目标。您可以将多个导出标签设置为新的或现有的cookie或URL目标。
seo-description: 数据导出标签使用您在数据源上设置的导出控件。数据导出标签可防止您向区段添加受限特征，并将区段数据发送到目标。您可以将多个导出标签设置为新的或现有的cookie或URL目标。
seo-title: 将数据导出控制添加到目标
solution: Audience Manager
title: 将数据导出控制添加到目标
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---



# 将数据导出标签添加到目标位置 {#add-data-export-labels}

[!DNL Data Export Labels] 使用在数据 [!DNL Export Controls] 源上设置的内容。[!DNL Data Export Labels] 防止您向区段添加受限特征，并将区段数据发送到目标。您可以将多个导出标签设置为新的或现有 [!DNL cookie][!DNL URL] 的或目标的。

>[!NOTE]
>
>要添加导出标签，您需要管理员权限 *或* 足够的权限来创建或编辑目标。

<!-- t_export_labels.xml -->

要向目标中添加导出标签，请执行以下操作：

1. 单击 **[!UICONTROL Audience Data]**:
   * 对于新目标：单击 **[!UICONTROL Create New Destination]**。在选择数据导出标签之前，请完成 [!UICONTROL Basic Information] 此部分。请参阅 [创建Cookie目标](../../features/destinations/manage-destinations.md#create-cookie-destination) 或 [创建URL目标](../../features/destinations/manage-destinations.md#configure-url-destination) 以获取信息。
   * 对于现有目标：使用该 [!DNL Search] 框查找目标或滚动列表，然后单击目标名称以将其打开。
1. 选择 [!DNL Data Export Label]. 如果不希望设置任何导出限制，请将复选框保留为空。导出标签包括以下选项：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >除非在数据源上设置 [了匹配的导出控制](../../features/data-export-controls.md) ，否则导出限制将不起作用。
1. 单击 **[!UICONTROL Save]**.

>[!MORE_ LIKE_ This]
>
>* [创建数据源](../../features/manage-datasources.md#create-data-source)