---
description: 批量估计会根据细分规则返回细分大小数据。按照这些说明进行批量估计请求。
seo-description: 批量估计会根据细分规则返回细分大小数据。按照这些说明进行批量估计请求。
seo-title: 批量估计
solution: Audience Manager
title: 批量估计
uuid: 63b2f06a-8ba0-47a2-bd0 b-8039b2 d4 c95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

批量估计会根据细分规则返回细分大小数据。按照这些说明进行批量估计请求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
1. Click the **[!UICONTROL Estimate]** tab.
1. 将评估标题粘贴到评估工作表的第一行。
1. 根据标题标签，粘贴或键入要更改为相应列的数据。
1. 在工作表工具栏中，单击与要更新的项目匹配的创建按钮。
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. 在输入数据之前，您的批量估计工作表应当类似于以下内容：

![](assets/estimate.png)如果批量更新返回错误或失败，请参阅 [批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。

