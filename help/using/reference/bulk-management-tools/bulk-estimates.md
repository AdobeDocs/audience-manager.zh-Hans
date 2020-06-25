---
description: 批量估计根据细分规则返回细分大小数据。 按照以下说明进行批量评估请求。
seo-description: 批量估计根据细分规则返回细分大小数据。 按照以下说明进行批量评估请求。
seo-title: 批量预估
solution: Audience Manager
title: 批量预估
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# 批量预估{#bulk-estimates}

批量估计根据细分规则返回细分大小数据。 按照以下说明进行批量评估请求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[UI中分配的](../../features/administration/administration-overview.md) RBAC组权 [!DNL Audience Manager] 限在中得到保留 [!UICONTROL Bulk Management Tools]。

要进行批量更新，请打开工 [!UICONTROL Bulk Management Tools] 作表并：

1. 单击选 **[!UICONTROL Headers]** 项卡并复制 [!UICONTROL Estimate Segment Size] 标题。
2. Click the **[!UICONTROL Estimate]** tab.
3. 将估计题头粘贴到估计工作表的第一行中。
4. 根据标题标签，粘贴或键入要更改的数据到相应的列。
5. 在工作表工具栏中，单击与要更新的项目匹配的创建按钮。
此操作将打开 [!UICONTROL Account Information] 对话框。
6. 提供所需的 [登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然后单击 **[!UICONTROL Submit]**。

此操作将在工 [!UICONTROL Response] 作表中创建包含估计段大小数据的列。 在输入数据之前，批量估计工作表应类似于以下内容：

![](assets/estimate.png)
如果批量更新返回错误或失败，请参阅批 [量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。

