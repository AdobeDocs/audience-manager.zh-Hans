---
description: 批量估计会根据区段规则返回区段大小数据。 按照这些说明进行批量评估请求。
seo-description: 批量估计会根据区段规则返回区段大小数据。 按照这些说明进行批量评估请求。
seo-title: 批量预估
solution: Audience Manager
title: 批量预估
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# 批量预估{#bulk-estimates}

批量估计会根据区段规则返回区段大小数据。 按照这些说明进行批量评估请求。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[在UI中](../../features/administration/administration-overview.md) 分配的RBAC组 [!DNL Audience Manager] 权限将在中得 [!UICONTROL Bulk Management Tools]到。

要进行批量更新，请打开[!UICONTROL Bulk Management Tools]工作表，然后：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡并复制[!UICONTROL Estimate Segment Size]标头。
2. 单击&#x200B;**[!UICONTROL Estimate]**&#x200B;选项卡。
3. 将估计标题粘贴到估计工作表的第一行中。
4. 根据标题标签，将要更改的数据粘贴或键入到相应的列中。
5. 在工作表工具栏中，单击与您要更新的项目匹配的创建按钮。
此操作将打开[!UICONTROL Account Information]对话框。
6. 提供所需的[登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)并单击&#x200B;**[!UICONTROL Submit]**。

此操作会在包含估计区段大小数据的工作表中创建[!UICONTROL Response]列。 在输入数据之前，您的批量预估工作表应类似于以下内容：

![](assets/estimate.png)
如果批量更新返回错误或失败，请参阅批量 [管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
