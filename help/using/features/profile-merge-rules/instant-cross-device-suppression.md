---
description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-title: 即时跨设备抑制
title: 即时跨设备抑制
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: 配置文件合并
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# 即时跨设备抑制 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 能够在与用户连接的多个设备上出现特定体验时禁止这些设备上的用户。使用[!UICONTROL Instant Cross-Device Suppression]功能为用户提供跨设备的一致体验。 Audience Manager 中的实时取消区段功能可提供这种体验。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供了两个关键用例：改善了用户体验和媒体效率。

* **改进的用户体验**:已购买您的产品或服务的用户将看不到与购买前相同的创意。相反，您可以针对您知道尚未购买的产品或服务显示追加销售或交叉销售消息。
* **媒体效率**:通过在所有网站中应用全球频率上限来优化促销活动 [!DNL DSP]支出。对于属于用户的多个设备，可以实时地操作频率上限。

[配置文件合并规则和设备取消分段流程](merge-rule-unsegment.md)中详细描述了实时取消分段的技术详细信息。 阅读以实际实施上述用例。

## 转换{#do-not-target-once}后，请勿定位

确保已转换（购买产品、获取订阅等）的用户 将看不到与转化前相同的消息传递。 您可以使用[!UICONTROL AND NOT]逻辑获取此值，如下所示。

1. 使用两个特征创建区段，然后使用[!UICONTROL AND NOT]逻辑，如下图所示。 您必须使用基于规则的特征来定义要实时触发的取消分段的转化事件。 阅读有关如何[创建基于规则的特征](../traits/create-onboarded-rule-based-traits.md)的更多信息。
2. 将区段映射到任意数量的实时服务器到服务器目标。 阅读有关如何将区段添加到[服务器到服务器目标](../destinations/add-edit-segments.md)的信息。

只要访客未进行转化，他们就有资格加入该区段。 一旦符合转化特征，访客就不再遵循区段规则，并立即从区段中删除。

![](assets/and_not_use_case.png)

## 在x展示次数{#do-not-target-after-x}后不定位

通过设置回访间隔和频度控件，您可以确保不会向用户大量提供相同的创意内容。 在此方案中，创建一个具有两个特征的区段，如下面的步骤所述。

1. 使用两个特征创建区段，然后使用[!UICONTROL AND]逻辑，如下图所示。 您必须使用基于规则的特征来定义要实时触发的取消分段的展示事件。 阅读有关如何[创建基于规则的特征](../traits/create-onboarded-rule-based-traits.md)的更多信息。
   >[!NOTE]
   >
   >您可以使用[!UICONTROL Actionable Log Files]或[!UICONTROL Pixel Calls]根据用户展示次数创建特征。 阅读有关[可操作日志文件](../../integration/media-data-integration/actionable-log-files.md)和[像素调用](../../integration/media-data-integration/impression-data-pixels.md)的更多信息。
2. 将频度控件应用于第二个特征。 如果需要，也可以添加回访间隔控件。 阅读有关[如何应用回访间隔和频率控件的更多信息](../segments/recency-and-frequency.md)。
3. 将区段映射到任意数量的实时服务器到服务器目标。 阅读有关如何将区段添加到[服务器到服务器目标](../destinations/add-edit-segments.md)的信息。

在此方案中，当您的用户积累了超过三次展示次数后，他们将从此区段中删除，不会再看到此特定创意内容。

![](assets/impressions_use_case.png)

## 注意的重要方面 — 处理{#processing-notes}

请记住与处理相关的以下方面：

* 要使实时取消分段功能正常工作，您必须将所需的区段映射到实时服务器到服务器目标。
* 对于通过[设备图](profile-link-use-case.md#recommendations)连接到设备的设备，我们对评估和取消分段强制实施了四设备限制。 [设备图选项和设备取消分段](merge-rule-unsegment.md#device-graph-options-unsegmentation)中介绍了此限&#x200B;制。
* 取消分段命令将包含在批处理文件中，每24小时向通过设备图连接的多个设备发送一次该批处理文件。
* 设备必须实时显示（位于[Edge](../../reference/system-components/components-edge.md)上），才能实时提示区段评估。 对于满足特征[!DNL TTL]时具有[!UICONTROL time-to-live (TTL)]的特征，将通过批处理文件在24小时内自动取消分段设&#x200B;备。 阅读有关如何[设置特征过期间隔](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)的更多信息。
* 如果您实时使用[!UICONTROL DCS API]到基于规则的板载特征，则可以使用[!UICONTROL AND NOT]逻辑触发取消分段。 有关[将数据发送到DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)的更多信&#x200B;息。

## 注意的重要方面 — 计时{#timing-notes}

请记住与时间有关的以下方面：

* 区段将存储在[Edge](../../reference/system-components/components-edge.md)上，与设备配置文件存储在[!UICONTROL Edge]上的时间段相同，即距上次实时交互14天。 有关数据保留的更多信息，请参阅我们的[数据保留常见问题解答](../../faq/faq-privacy.md#data-retention-faq)。
* 在[!DNL DCS]区域间传播取消分段操作大约需要24小时。 有关[!DNL DCS]区域[的更多信息，请参阅此处](../../reference/system-components/components-data-collection.md)和[此处](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
