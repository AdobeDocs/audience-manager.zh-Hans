---
description: 批量估计基于段规则返回段大小数据。 按照以下说明进行批量评估请求。
seo-description: 批量估计基于段规则返回段大小数据。 按照以下说明进行批量评估请求。
seo-title: 批量估计
solution: Audience Manager
title: 批量估计
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 批量估计{#bulk-estimates}

批量估计基于段规则返回段大小数据。 按照以下说明进行批量评估请求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支持 *。*[!DNL Audience Manager]此工具仅出于方便和礼貌而提供。 对于批量更改，我们建议您改用 [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) 。 [在UI中分配的](../../features/administration/administration-overview.md) RBAC组权限 [!DNL Audience Manager] 在UI中被接受 [!UICONTROL Bulk Management Tools]。

要进行批量更新，请打开工作 [!UICONTROL Bulk Management Tools] 表并：

1. 单击选 **[!UICONTROL Headers]** 项卡并复制标 [!UICONTROL Estimate Segment Size] 题。
1. Click the **[!UICONTROL Estimate]** tab.
1. 将估计题头粘贴到估计工作表的第一行中。
1. 根据标题标签，粘贴或键入要更改的数据到相应的列。
1. 在工作表工具栏中，单击与要更新的项目匹配的创建按钮。
此操作将打开对 [!UICONTROL Account Information] 话框。

1. 提供所需的 [登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ，然后单击 **[!UICONTROL Submit]**。

此操作将在工作 [!UICONTROL Response] 表中创建一列，其中包含估计的区段大小数据。 在输入数据之前，批量估计工作表应类似于以下内容：

![](assets/estimate.png)如果批量更新返回错误或失败，请参阅批量 [管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。

