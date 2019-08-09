---
description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-title: 即时跨设备抑制
title: 即时跨设备抑制
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857 d821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# 即时跨设备抑制 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 这是在任何设备上发生特定体验时，可以禁止跨多个设备连接到这些设备的用户。Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Audience Manager 中的实时取消区段功能可提供这种体验。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供两个主要用例：提升用户体验和媒体效率。

* **改进的用户体验**：已购买产品或服务的用户在购买之前不会看到相同创意。相反，您可以向了解他们未购买的产品或服务追加销售或交叉销售消息。
* **媒体效率**：通过在所有s上应用全局频率上限优化营销活动支出 [!DNL DSP]。频率上限可实时针对属于用户的多个设备进行定位。

[个人资料合并规则和设备取消分段流程中的篇幅描述了实时取消细分的技术细节](../../features/profile-merge-rules/merge-rule-unsegment.md)。阅读上述使用案例的实际实施。

## 转换后不设目标 {#do-not-target-once}

确保您的用户已转换(购买产品、获取订阅等)将看不到与转换之前相同的消息。您可以使用 [!UICONTROL AND NOT] 逻辑来获得这一点，如下所示。

1. 使用两个特征创建一个区段，然后使用 [!UICONTROL AND NOT] 逻辑，如下图所示。您必须使用基于规则的特征来定义要实时触发的取消区段转化事件。阅读有关 [如何创建基于规则的特征](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)的更多信息。
1. 将区段映射到任意数量的实时服务器目标目标。阅读关于如何向 [服务器到服务器目标添加区段的信息](../../features/destinations/add-edit-segments.md)。

只要未转换，访客就有资格享受该区段。一旦客户资格符合转换特征，他们就会停止遵循区段规则，并立即从区段中删除。

![](assets/and_not_use_case.png)

## 不要在x印象之后定位 {#do-not-target-after-x}

通过设置新近度和频率控制，您可以确保不会通过相同的创意来发掘用户。在此方案中，如下面的步骤所述，创建具有两个特征的区段。

1. 使用两个特征创建一个区段，然后使用 [!UICONTROL AND] 逻辑，如下图所示。您必须使用基于规则的特征来定义要实时触发的取消区段的印象事件。阅读有关 [如何创建基于规则的特征](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)的更多信息。
   >[!NOTE]
   >
   >您可以根据用户印象使用 [!UICONTROL Actionable Log Files] 或 [!UICONTROL Pixel Calls] 创建特征。阅读有关 [可操作日志文件](../../integration/media-data-integration/actionable-log-files.md) 和 [像素调用](../../integration/media-data-integration/impression-data-pixels.md)的更多信息。
1. 将频率控件应用于第二个特征。如果您愿意，还可以添加新近度控件。阅读有关如何 [应用新近度和频率控制](../../features/segments/recency-and-frequency.md)的更多信息。
1. 将区段映射到任意数量的实时服务器目标目标。阅读关于如何向 [服务器到服务器目标添加区段的信息](../../features/destinations/add-edit-segments.md)。

在这种情况下，一旦用户累计了三次以上的展示次数，他们将从此区段中删除，并且不再看到此特定创意。

![](assets/impressions_use_case.png)

## 注意事项-处理 {#processing-notes}

请记住与处理相关的这些方面：

* 为了实现实时取消细分功能，您必须将所需的区段映射到实时服务器到服务器目标。
* 对于 [设备图](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)连接到设备的设备，我们实施了对评估和取消分段的四设备限制。[设备图表选项和设备取消分段中描述了此限制](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation)。
* 取消区段命令将包含在批处理文件中，每24小时发送到目标，对于设备图表连接的多个设备。
* 设备必须实时查看( [边缘](../../reference/system-components/components-edge.md))以提示细分评估。对于具有 [!UICONTROL time-to-live (TTL)] 值的特征，即使满足特征 [!DNL TTL] ，设备 *也不* 会自动取消分段，直到设备实时显示。阅读有关 [如何设置特征到期间隔](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)的更多信息。
* 如果您实时 [!UICONTROL DCS API] 使用基于规则的基于规则的特征，则可以使用 [!UICONTROL AND NOT] 逻辑触发取消区段。阅读有关向DCS API [发送数据的更多信息](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)。

## 注意事项-计时 {#timing-notes}

请记住与时间相关的这些方面：

* 区段将存储 [在Edge的同一](../../reference/system-components/components-edge.md) 时间段内(即设备配置文件存储在 [!UICONTROL Edge]上次实时交互后的14天内)。阅读 [我们的数据保留常见问题解答](../../faq/faq-privacy.md#data-retention-faq)，了解有关数据保留的更多信息。
* 取消区段操作大约需要24小时才能跨 [!UICONTROL DCS] 区域传播。在此处和此处了解有关我们 [!UICONTROL DCS] 的地区 [的](../../reference/system-components/components-data-collection.md) 更多 [信息](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。