---
description: 使用区段生成器暂停或删除活动区段时，描述对分段用户、数据和目标的影响。
seo-description: 使用区段生成器暂停或删除活动区段时，描述对分段用户、数据和目标的影响。
seo-title: 暂停和删除的区段
solution: Audience Manager
title: 暂停和删除的区段
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 暂停和删除的区段 {#paused-and-deleted-segments}

描述在使用暂停或删除活动区段时对分段用户、数据和目标的影响 [!UICONTROL Segment Builder]。

## 访问暂停和删除控件

将鼠标悬停在区段列表中的区段名称上，以 **[!UICONTROL pause]** 显示 **[!UICONTROL delete]** 和图标(在列 [!UICONTROL Actions] 中)。 这些功能影响细分，如下所述。

## 暂停的区段功能

暂停（已取消激活）区段：

* 停止对新的合格用户进行细分。
* 保留用户的分段状态／会员资格（不会从区段中删除用户）。
* 保留在区段列表中，并可以重新激活。
* 不向关联的目标发送数据。
* 返回可用报告中的数据（截至取消激活日期）。

## 已删除的区段功能

已删除的区段：

* 停止对新的合格用户进行细分。
* 从区段会员资格中删除合格用户。
* 从区段列表中删除。
* 无法取消删除。
* 不向关联的目标发送数据。
* 不返回可用报告中的数据。

>[!NOTE]
>
>您还可以使用方法暂停和删除区 [!DNL API] 段。 有关详细信息，请参 [阅REST API](../../api/rest-api-main/rest-api-main.md)。