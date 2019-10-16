---
description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-title: 即时跨设备抑制
title: 即时跨设备抑制
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 即时跨设备抑制 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 是当任何这些设备上都出现特定体验时，能够禁止连接到他们的多个设备上的用户。 Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Audience Manager 中的实时取消区段功能可提供这种体验。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供两个关键使用案例：改善了用户体验和媒体效率。

* **改进的用户体验**:已购买您的产品或服务的用户将看不到与购买前相同的创意。 相反，您可以显示您知道尚未购买的产品或服务的追加销售或交叉销售消息。
* **媒体效率**:通过对所有渠道应用全局频率上限，优化您的营销 [!DNL DSP]活动支出。对于属于用户的多个设备，可以实时地对频率上限进行操作。

在Profile Merge Rules和Device Un-Segmentation Process中，对实时取消分段的技术细节进 [行了详细的描述](merge-rule-unsegment.md)。 阅读上述使用案例的实际实施。

## 转换后不定位 {#do-not-target-once}

确保您的用户已转换（购买了产品、获得了订阅等）将看不到与转换前相同的消息。 您可以使用逻辑获 [!UICONTROL AND NOT] 取此值，如下所示。

1. 使用两个特征创建区段，然后使 [!UICONTROL AND NOT] 用逻辑，如下图所示。 必须使用基于规则的特征来定义要实时触发的取消段的转换事件。 阅读有关如何创建基 [于规则的特征的更多信息](../traits/create-onboarded-rule-based-traits.md)。
2. 将区段映射到任意数量的实时服务器到服务器目标。 阅读有关如何将区段添加到服 [务器到服务器目标的信息](../destinations/add-edit-segments.md)。

只要访客尚未转化，他们就有资格加入该区段。 一旦他们符合转化特征，他们就不再遵循区段规则并立即从区段中删除。

![](assets/and_not_use_case.png)

## Do Not Target After x展示次数 {#do-not-target-after-x}

通过设置最近和频率控件，您可以确保不会以相同的创意淹没用户。 在此方案中，请创建具有两个特征的区段，如下面的步骤所述。

1. 使用两个特征创建区段，然后使 [!UICONTROL AND] 用逻辑，如下图所示。 必须使用基于规则的特征来定义要实时触发的取消区段的印象事件。 阅读有关如何创建基 [于规则的特征的更多信息](../traits/create-onboarded-rule-based-traits.md)。
   >[!NOTE]
   >
   >您可以使用 [!UICONTROL Actionable Log Files] 或根 [!UICONTROL Pixel Calls] 据用户印象创建特征。 阅读有关可操作 [的日志文件](../../integration/media-data-integration/actionable-log-files.md) 和像 [素调用的更多信息](../../integration/media-data-integration/impression-data-pixels.md)。
2. 将频率控制应用于第二个特征。 如果您愿意，还可以添加近期控制。 阅读有关如 [何应用最近和频率控制的更多信息](../segments/recency-and-frequency.md)。
3. 将区段映射到任意数量的实时服务器到服务器目标。 阅读有关如何将区段添加到服 [务器到服务器目标的信息](../destinations/add-edit-segments.md)。

在此方案中，一旦用户累积了超过三个印象，他们将从此区段中删除，并且不会再看到此特定创意。

![](assets/impressions_use_case.png)

## 注释的重要方面——处理 {#processing-notes}

请记住与处理相关的以下方面：

* 要使实时取消细分功能正常工作，您必须将所需细分映射到实时服务器到服务器目标。
* 对于通过设备图连接到设备的 [设备](profile-link-use-case.md#recommendations)，我们对评估和取消分段强制实施四设备限制。 此限制在设备图形选 [项和设备取消分段中介绍](merge-rule-unsegment.md#device-graph-options-unsegmentation)&#x200B;。
* unsegment命令将包含在批处理文件中，该批处理文件每24小时发送一次至目标，用于通过设备图连接的多个设备。
* 设备必须实时显示(在 [Edge上](../../reference/system-components/components-edge.md) )，以实时提示细分评估。 对于满足特征时 [!UICONTROL time-to-live (TTL)] 的特征，设 [!DNL TTL] 备将在24小时内通过批处理文件自动取消分段&#x200B;。阅读有关如何设置特 [征到期间隔的更多信息](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。
* 如果您实时使 [!UICONTROL DCS API] 用基于板载规则的特征，则可以使用逻辑触发取消细 [!UICONTROL AND NOT] 分。 阅读有关将数 [据发送到DCS API的更多信息](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)&#x200B;。

## 注意的重要方面——时间 {#timing-notes}

请记住与时间相关的这些方面：

* 段将存储在 [Edge](../../reference/system-components/components-edge.md)[!UICONTROL Edge]，存储的时间段与设备配置文件存储在上的时间段相同，即自上次实时交互以来的14天。 阅读我们的数据保留常见问题解答，了解 [有关数据保留的更多信息](../../faq/faq-privacy.md#data-retention-faq)。
* 非细分操作跨区域传播大约需要24小 [!UICONTROL DCS] 时。 请在此处和此处阅读关 [!UICONTROL DCS] 于 [我们](../..//reference/system-components/components-data-collection.md) 的 [地区](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
