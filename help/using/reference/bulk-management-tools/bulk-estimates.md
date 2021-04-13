---
description: 批量估计基于区段规则返回区段大小数据。 按照以下说明进行批量评估请求。
seo-description: 批量估计基于区段规则返回区段大小数据。 按照以下说明进行批量评估请求。
seo-title: 批量预估
solution: Audience Manager
title: 批量预估
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# 批量预估{#bulk-estimates}

批量估计基于区段规则返回区段大小数据。 按照以下说明进行批量评估请求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[在UI中](../../features/administration/administration-overview.md) 分配的RBAC组 [!DNL Audience Manager] 权限在中得以执行 [!UICONTROL Bulk Management Tools]。

要进行批量更新，请打开[!UICONTROL Bulk Management Tools]工作表并：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡并复制[!UICONTROL Estimate Segment Size]标题。
2. 单击&#x200B;**[!UICONTROL Estimate]**&#x200B;选项卡。
3. 将估计题头粘贴到估计工作表的第一行中。
4. 根据标题标签，粘贴或键入要更改的数据到相应的列。
5. 在工作表工具栏中，单击与要更新的项目匹配的创建按钮。
此操作将打开[!UICONTROL Account Information]对话框。
6. 提供所需的[登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)并单击&#x200B;**[!UICONTROL Submit]**。

此操作会在工作表中创建一个[!UICONTROL Response]列，其中包含估计的区段大小数据。 在输入数据之前，批量估计工作表应类似于以下内容：

![](assets/estimate.png)
如果批量更新返回错误或失败，请参阅批 [量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
