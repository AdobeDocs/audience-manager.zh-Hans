---
description: 目标登陆页面列出您的所有URL、cookie和服务器到服务器目标。它提供允许您创建、编辑、搜索和报告目标的功能。登陆页面位于“受众数据”>“目标”中。
seo-description: 目标登陆页面列出您的所有URL、cookie和服务器到服务器目标。它提供允许您创建、编辑、搜索和报告目标的功能。登陆页面位于“受众数据”>“目标”中。
seo-title: 管理目标
solution: Audience Manager
title: 管理目标
uuid: 6b66ff42-0075-49a7-a58 f-7f8 ea2295 fdc
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# 管理目标 {#manage-destinations}

[!UICONTROL Destination] 登陆页面列出您的所有 [!DNL URL]、cookie和服务器到服务器目标。它提供允许您创建、编辑、搜索和报告目标的功能。登录页面 **[!UICONTROL Audience Data > Destinations]**&#x200B;位于中。

## 默认登陆页面 {#default-landing-page}

<!-- destinations-home.xml -->

默认登陆页面会根据类型列出目标。您可以使用四个可用的选项卡过滤目标：

* ****&#x200B;全部：显示所有类型的目标。
* **Adobe Experience Cloud**：显示将数据发送到其他Adobe Experience Cloud解决方案的目标。目前，唯一支持的选项是Adobe Analytics。See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **集成平台**：显示基于用户的和基于设备的目标(也称为服务器到服务器目标)。请注意，基于人员的目标目前仅对选定客户提供测试功能。
* **自定义**：显示cookie和URL目标。


![](assets/destinations-landing.png)

## 可寻址受众登陆页面 {#audiences-landing-page}

要查看服务器到服务器目标的受众数据和匹配率，请选择 **[!UICONTROL Integrated Platforms > Device-Based]**。

有关所显示信息的更多信息，请参阅 [潜在受众界面](/help/using/features/addressable-audiences.md#addressable-audience-interface)。

![](/help/using/features/assets/addressable-audiences-landing.png)

## 配置URL目标 {#configure-url-destination}

[!DNL URL] 目标会向目标页面发出像素调用。按照这些说明创建 [!DNL URL][!UICONTROL Destination Builder]目标。

<!-- create-url-destination.xml -->

要创建 [!DNL URL] 新目标，请转至 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 并完成如下所述的章节。

### 基本信息 {#basic-info}

此部分包含启动URL目标创建过程的字段和选项。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Basic Information]** 以显示控件。
2. 命名目标。避免缩写和特殊字符。
3. *(可选)* 描述目标。简明描述是定义或提供目标的更多信息的有效方法。
4. 在 **[!UICONTROL Category]** 列表中，选择 **[!UICONTROL Custom]**。
5. 在 **[!UICONTROL Environment]** 列表中，选择触发URL目标的环境。
6. 在 **[!UICONTROL Type]** 列表中，单击 **[!UICONTROL URL]**。
7. *(可选)* 选择一个 **[!UICONTROL Auto-fill Destination Mapping]**。选项包括：
   * **[!UICONTROL Segment ID]**：自动添加区段ID并将其发送到目标。
   * **[!UICONTROL Integration Code Value]**：自动添加区段集成代码并将其发送到目标映射。集成代码是客户创建和使用的唯一标识符。长度限制为255个字符，最大。
8. 单击 **[!UICONTROL Next]** 以转到 [!UICONTROL Configuration] 设置，或单击 **[!UICONTROL Data Export Labels]** 以将导出控件应用于目标。

### 数据导出标签 {#data-export-labels-dest}

此部分包含将 [数据导出控件](../../features/data-export-controls.md) 应用 [!DNL URL] 到目标的选项。如果您不使用数据导出控件，请跳过此步骤。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Data Export Labels]** 以显示控件。
2. 选择与应用于目标的数据导出控件对应的标签(请参阅 [将导出标签添加到目标](../../features/destinations/manage-destinations.md#add-data-export-labels) 以了解详细信息)。
3. 单击 **[!UICONTROL Save]**.

### 配置 {#configure-base-data}

此部分包含允许您设置由字符串传入的基础 [!DNL URL] 和数据分隔符的 [!DNL URL] 选项。此部分为可选部分。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Configuration]** 以显示控件。
1. *(可选)* 选中复选 **[!UICONTROL Serialize]** 框。
这允许您按顺序将区段发送到目标，而不是为每个区段单独发送调用。序列化有助于提高数据传输效率。选中此复选框可显示URL和分隔符字段。有关详细信息，请参阅 [标准和串行密钥对。](../../features/destinations/key-value-pairs.md)
1. 如果您选择 **[!UICONTROL Serialize]**&#x200B;此选项，则还必须配置下面描述的URL和分隔符字段。

| 字段 | 描述 |
|--- |--- |
| 基本 URL | 标准 `HTTP`[!DNL URL] 的基本部分不变。此外，您还需要将 `%ALIAS%`[占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined) 放置到基本URL中。示例: `https://www.myCompany.com/%alias%...` |
| 安全URL | 安全的基本部分 `HTTPS`[!DNL URL] 不会改变。此外，您还需要将 `%ALIAS%`[占位符宏](../../features/destinations/destination-macros.md#destination-macros-defined) 放置到基本URL中。示例: `https://www.myCompany.com/%alias%...` |
| Delimiter（分隔符） | 分隔 [!DNL URL] 字符串变量的符号。这通常是逗号或分号。从目标合作伙伴处获取此信息。 |

### 细分映射 {#segment-mappings}

此部分允许您搜索区段并将其添加到目标位置。要完成本节，请执行以下操作：

1. 单击 **[!UICONTROL Segment Mappings]** 以显示控件。
1. **[!UICONTROL Search and Add Segments]** 在框中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 浏览可用区段列表。
1. 在 **[!UICONTROL Add Selected Segments]** 找到要使用的区段时单击。添加区段将打开 [!UICONTROL Edit Mapping] 窗口。
1. 在 [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**：提供区段使用的键值对。
   * **[!UICONTROL Start Date]** 以及 **[!UICONTROL End Date]**：选择目标的开始日期和结束日期。如果结束日期为空，则目标永不过期。
1. 单击 **[!UICONTROL Done]**.

## 为服务器到服务器目标添加或编辑区段 {#add-edit-segments}

您只能为服务器-server([!DNL S2S])目标添加或编辑区段。无法创建 [!DNL S2S] 目标。[!UICONTROL Destination Builder]请与您的顾问联系以设置 [!DNL S2S] 目标。按照这些说明为 [!DNL S2S] 目标添加或编辑区段。

<!-- destination-s2s-edit.xml -->

要为 [!DNL S2S] 目标添加或编辑区段映射，请执行以下操作：

1. **[!UICONTROL Audience Data > Destinations]**&#x200B;转至。选择 **“集成平台”&gt;“基于设备的设备** ”，找到要处理的 [!DNL S2S] 目标。
2. 在 [!UICONTROL Action] 列中，单击铅笔图标以编辑目标。
   * **[!UICONTROL Search and Add Segments]** 在框中，开始键入区段名称或单击 **[!UICONTROL Browse All Segments]** 浏览可用区段列表。
   * 在 **[!UICONTROL Add Selected Segments]** 找到要使用的区段时单击。添加区段将打开 [!UICONTROL Edit Mapping] 窗口。
   * 在 [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**：为此目标使用的 [键值对](../../features/destinations/key-value-pairs.md) 设置值。
      * **[!UICONTROL Start Date]** 以及 **[!UICONTROL End Date]**：选择目标的开始日期和结束日期。如果结束日期为空，则目标永不过期。
3. 单击 **[!UICONTROL Save]** 并单击 **[!UICONTROL Done]**。

## 将数据导出标签添加到目标位置 {#add-data-export-labels}

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

