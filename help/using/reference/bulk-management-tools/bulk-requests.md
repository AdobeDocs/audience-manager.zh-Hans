---
description: 批量请求会返回可在更新、创建、评估和删除工作表中使用不同标题的数据。
seo-description: 批量请求会返回可在更新、创建、评估和删除工作表中使用不同标题的数据。
seo-title: 批量请求
solution: Audience Manager
title: 批量请求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

批量请求会返回可在更新、创建、评估和删除工作表中使用不同标题的数据。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. 此工具仅为方便起见而提供，并且仅作为好意提供。For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [在UI中](../../features/administration/administration-overview.md) 分配的CLUAC组权限在 [!DNL Audience Manager] 此中受支持 [!UICONTROL Bulk Management Tools]。

[!UICONTROL Request] 工作表没有自己的列标题集，您无需将ID复制到任何列。相反，它会根据您在工具栏中单击的操作按钮返回数据。而且，可选报告功能返回像素触发的频率计数和多个固定时间间隔的独特用户计数。

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. 在工作表顶部的工具栏中，单击与您要处理的数据对应的请求按钮。您可以请求：

   * 数据提供者ID
   * 派生信号
   * 目标映射
   * 基于规则的和内置的特征
   * 区段
   * 特征和区段文件夹ID
   [!DNL Audience Manager] API会将批量数据写入 [!UICONTROL Request] 工作表中。

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. 基础日期/时间戳以UNIX UTC时间进行记录。目前，工作表无法以可读格式返回日期/时间戳。

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
