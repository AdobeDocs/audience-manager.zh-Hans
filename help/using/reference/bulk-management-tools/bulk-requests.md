---
description: 批量请求会返回您可以与“更新”、“创建”、“估计”和“删除”工作表中的不同标题一起使用的数据。
seo-description: 批量请求会返回您可以与“更新”、“创建”、“估计”和“删除”工作表中的不同标题一起使用的数据。
seo-title: 批量请求
solution: Audience Manager
title: 批量请求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# 批量请求{#bulk-requests}

批量请求会返回您可以与“更新”、“创建”、“估计”和“删除”工作表中的不同标题一起使用的数据。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[UI中分配的](../../features/administration/administration-overview.md) RBAC组权 [!DNL Audience Manager] 限在中得到保留 [!UICONTROL Bulk Management Tools]。

工 [!UICONTROL Request] 作表没有其自己的列标题集，您无需将ID复制到任何列。 而是根据您在工具栏中单击的操作按钮返回数据。 此外，可选的报告功能会为像素触发返回频率计数，为多个固定时间间隔返回唯一用户计数。

要发出批量请求，请打开工 [!UICONTROL Bulk Management Tools] 作表并：

1. Click the **[!UICONTROL Request]** tab.
2. 在工作表顶部的工具栏中，单击与要处理的数据对应的请求按钮。 您可以请求：

   * 算法模型
   * 数据源
   * 派生信号
   * 目标映射
   * 算法、基于规则和载入的特征
   * 区段
   * 特征和段文件夹ID
   API [!DNL Audience Manager] 将批量数据写回工作 [!UICONTROL Request] 表。

>[!NOTE]
>
>在结果中，和列 `createTime` 以指 `updateTime` 数表示法返回数据。 基础日期／时间戳以UNIX UTC时间记录。 当前，工作表无法以可读格式返回日期／时间戳。

如果批量更新返回错误或失败，请参阅批 [量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
