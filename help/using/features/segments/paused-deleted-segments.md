---
description: 描述当您使用区段生成器暂停或删除活动区段时对分段用户、数据和目标的影响。
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: 暂停和删除的区段
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
TQID: https://experienceleague.adobe.com/aLnmaOxB3fkGdwq4XjKz8SFKizwHI7Ll5rBUb-o34BM
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 0%

---

# 暂停和删除的区段 {#paused-and-deleted-segments}

描述当您使用[!UICONTROL Segment Builder]暂停或删除活动区段时对分段用户、数据和目标的影响。

## 访问暂停和删除控件

将鼠标悬停在区段列表中的区段名称上以显示&#x200B;**[!UICONTROL pause]**&#x200B;和&#x200B;**[!UICONTROL delete]**&#x200B;图标（在[!UICONTROL Actions]列中）。 这些功能会影响区段，如下所述。

## 暂停的区段功能

已暂停（已停用）的区段：

* 停止对符合条件的新用户进行分段。
* 保留用户的分段状态/成员资格（不会从区段中删除用户）。
* 保留在区段列表中，可以重新激活。
* 不会将数据发送到关联的目标。
* 返回可用报表中的数据（截至停用日期）。

## 已删除区段功能

已删除的区段：

* 停止对符合条件的新用户进行分段。
* 从区段成员资格中删除符合条件的用户。
* 从区段列表中删除。
* 无法取消删除。
* 不会将数据发送到关联的目标。
* 在可用报表中不返回数据。

>[!NOTE]
>
>您还可以使用[!DNL API]方法暂停和删除区段。 有关详细信息，请参阅[REST API](../../api/rest-api-main/rest-api-main.md)。
