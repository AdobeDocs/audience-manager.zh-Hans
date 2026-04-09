---
description: 批量估计会根据区段规则返回区段大小数据。 按照这些说明发出批量估算请求。
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: 批量预估
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
TQID: https://experienceleague.adobe.com/FDD4gSg00I8p4sRqxE9sEpO5dSkGEXpH3hUD6h5CAtI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# 批量预估{#bulk-estimates}

批量估计会根据区段规则返回区段大小数据。 按照这些说明发出批量估算请求。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[接受在](../../features/administration/administration-overview.md) UI中分配的[!DNL Audience Manager]RBAC组权限[!UICONTROL Bulk Management Tools]。

要进行批量更新，请打开[!UICONTROL Bulk Management Tools]工作表并：

1. 单击&#x200B;**[!UICONTROL Headers]**&#x200B;选项卡并复制[!UICONTROL Estimate Segment Size]标题。
2. 单击&#x200B;**[!UICONTROL Estimate]**&#x200B;选项卡。
3. 将估算标题粘贴到估算工作表的首行。
4. 根据标题标签，将要更改的数据粘贴或键入到相应的列中。
5. 在工作表工具栏中，单击与您正在更新的项目相匹配的“创建”按钮。
此操作打开[!UICONTROL Account Information]对话框。
6. 提供所需的[登录信息](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)，然后单击&#x200B;**[!UICONTROL Submit]**。

此操作在工作表中创建包含预计区段大小数据的[!UICONTROL Response]列。 在输入数据之前，批量估算工作表应当类似于以下内容：

![](assets/estimate.png)
如果批量更新返回错误或失败，请参阅[批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
