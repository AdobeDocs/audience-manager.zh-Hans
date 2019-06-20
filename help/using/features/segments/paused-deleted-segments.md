---
description: 介绍使用区段生成器暂停或删除活动区段时对分段用户、数据和目标的影响。
seo-description: 介绍使用区段生成器暂停或删除活动区段时对分段用户、数据和目标的影响。
seo-title: 已暂停和已删除的区段
solution: Audience Manager
title: 已暂停和已删除的区段
uuid: 88efe4af-f9 a4-4bce-920a-352bd4 d505 dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## 访问暂停和删除控件

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). 这些功能会影响区段，如下所述。

## 已暂停的区段功能

暂停(已取消激活)区段：

* 停止细分新的合格用户。
* 保留用户的分段状态/会员资格(不会从区段中删除用户)。
* 保留在区段列表中，可重新激活。
* 不会将数据发送到关联的目标。
* 返回可用报告中的数据(直至取消激活日期)。

## 删除的区段功能

删除的区段：

* 停止细分新的合格用户。
* 从细分会员资格中删除合格用户。
* 从区段列表中删除。
* 无法取消删除。
* 不会将数据发送到关联的目标。
* 不会返回可用报告中的数据。

>[!NOTE]
>
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).