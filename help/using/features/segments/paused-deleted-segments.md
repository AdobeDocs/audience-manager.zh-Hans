---
description: 描述使用区段生成器暂停或删除活动区段时对分段用户、数据和目标的影响。
seo-description: 描述使用区段生成器暂停或删除活动区段时对分段用户、数据和目标的影响。
seo-title: 已暂停和已删除的区段
solution: Audience Manager
title: 已暂停和已删除的区段
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 5%

---


# 已暂停和已删除的区段 {#paused-and-deleted-segments}

描述使用[!UICONTROL Segment Builder]暂停或删除活动区段时对分段用户、数据和目标的影响。

## 访问暂停和删除控件

将鼠标悬停在区段列表中的区段名称上，可显示&#x200B;**[!UICONTROL pause]**&#x200B;和&#x200B;**[!UICONTROL delete]**&#x200B;图标（位于[!UICONTROL Actions]列中）。 这些功能影响细分，如下所述。

## 暂停的段功能

已暂停（已取消激活）区段：

* 停止对新的合格用户进行细分。
* 保留用户的分段状态／成员资格（不会从区段中删除用户）。
* 保留在区段列表中，并可重新激活。
* 不向关联的目标发送数据。
* 返回可用报告中的数据（截止到取消激活日期）。

## 已删除的区段功能

已删除的区段：

* 停止对新的合格用户进行细分。
* 从细分会员资格中删除合格用户。
* 从区段列表中删除。
* 无法取消删除。
* 不向关联的目标发送数据。
* 不返回可用报告中的数据。

>[!NOTE]
>
>您还可以使用[!DNL API]方法暂停和删除区段。 有关详细信息，请参阅[REST API](../../api/rest-api-main/rest-api-main.md)。