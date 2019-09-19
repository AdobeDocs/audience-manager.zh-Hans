---
description: “数据导出标签”与您在数据源上设置的“导出控件”配合使用。 数据导出标签阻止您将受限特征添加到区段，并阻止将区段数据发送到目标。 您可以将多个导出标签设置为新的或现有的cookie或URL目标。
seo-description: “数据导出标签”与您在数据源上设置的“导出控件”配合使用。 数据导出标签阻止您将受限特征添加到区段，并阻止将区段数据发送到目标。 您可以将多个导出标签设置为新的或现有的cookie或URL目标。
seo-title: 将数据导出控件添加到目标
solution: Audience Manager
title: 将数据导出控件添加到目标
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---



# 将数据导出标签添加到目标 {#add-data-export-labels}

[!DNL Data Export Labels] 使用您在 [!DNL Export Controls] 数据源上设置的内容。 [!DNL Data Export Labels] 阻止您向区段添加受限特征，以及将区段数据发送到目标。 您可以将多个导出标签设置为新的或现有的或 [!DNL cookie] 目标 [!DNL URL] 位置。

>[!NOTE]
>
>要添加导出标签，您需要管理员权限 *或足够的权限* ，才能创建或编辑目标。

<!-- t_export_labels.xml -->

要向目标添加导出标签，请执行以下操作：

1. 单击 **[!UICONTROL Audience Data]**:
   * 对于新目标：单击 **[!UICONTROL Create New Destination]**。 在选择数 [!UICONTROL Basic Information] 据导出标签之前，请完成该部分。 有关 [信息，请参阅创建Cookie](../../features/destinations/create-cookie-destination.md)[目标或创建URL目标](../../features/destinations/create-url-destination.md) 。
   * 对于现有目标：使用该 [!DNL Search] 框可查找目标，或在列表中滚动并单击目标名称以打开它。
1. 选择 [!DNL Data Export Label]. 如果不想设置任何导出限制，请将复选框留空。 导出标签包括以下选项：
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >除非对数据源设置了匹配的导 [出控制](../../features/data-export-controls.md) ，否则导出限制无效。
1. 单击 **[!UICONTROL Save]**.

>[!MORE_LIKE_THIS]
>
>* [创建数据源](../../features/manage-datasources.md#create-data-source)