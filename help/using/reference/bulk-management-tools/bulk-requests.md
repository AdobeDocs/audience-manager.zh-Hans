---
description: 批量请求会返回可用于更新、创建、估计和删除工作表中的不同标题的数据。
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: 批量请求
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 批量请求{#bulk-requests}

批量请求会返回可用于更新、创建、估计和删除工作表中的不同标题的数据。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]接受在[!DNL Audience Manager] UI中分配的[RBAC组权限](../../features/administration/administration-overview.md)。

[!UICONTROL Request]工作表没有自己的列标题集，您无需将ID复制到任何列。 相反，它会根据您在工具栏中单击的操作按钮返回数据。 此外，可选的报表功能会返回像素触发的频率计数以及多个固定时间间隔内的独特用户计数。

要发出批量请求，请打开[!UICONTROL Bulk Management Tools]工作表并：

1. 单击&#x200B;**[!UICONTROL Request]**&#x200B;选项卡。
2. 在工作表顶部的工具栏中，单击与您要使用的数据对应的请求按钮。 您可以请求：

   * 算法模型
   * 数据源
   * 派生的信号
   * 目标映射
   * 算法、基于规则和载入的特征
   * 区段
   * 特征和区段文件夹ID

   [!DNL Audience Manager] API将批量数据写回[!UICONTROL Request]工作表。

>[!NOTE]
>
>在您的结果中，`createTime`和`updateTime`列以指数表示法返回数据。 基础日期/时间戳以UNIX UTC时间记录。 目前，工作表无法以可读格式返回日期/时间戳。

如果批量更新返回错误或失败，请参阅[批量管理工具疑难解答](../../reference/bulk-management-tools/bulk-troubleshooting.md)。
