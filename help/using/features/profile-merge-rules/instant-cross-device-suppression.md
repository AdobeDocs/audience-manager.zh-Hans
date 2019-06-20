---
description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-title: 即时跨设备抑制
title: 即时跨设备抑制
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857 d821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 即时跨设备抑制 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 这是在任何设备上发生特定体验时，可以禁止跨多个设备连接到这些设备的用户。Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Audience Manager 中的实时取消区段功能可提供这种体验。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供两个主要用例：提升用户体验和媒体效率。

* **改进的用户体验**：已购买产品或服务的用户在购买之前不会看到相同创意。相反，您可以向了解他们未购买的产品或服务追加销售或交叉销售消息。
* **媒体效率**：通过在所有s上应用全局频率上限优化营销活动支出 [!DNL DSP]。频率上限可实时针对属于用户的多个设备进行定位。

[个人资料合并规则和设备取消分段流程中的篇幅描述了实时取消细分的技术细节](../../features/profile-merge-rules/merge-rule-unsegment.md)。阅读上述使用案例的实际实施。

## Do Not Target Once Converted {#do-not-target-once}

确保您的用户已转换(购买产品、获取订阅等)将看不到与转换之前相同的消息。You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. 您必须使用基于规则的特征来定义要实时触发的取消区段转化事件。Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. 将区段映射到任意数量的实时服务器目标目标。Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

只要未转换，访客就有资格享受该区段。一旦客户资格符合转换特征，他们就会停止遵循区段规则，并立即从区段中删除。

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

通过设置新近度和频率控制，您可以确保不会通过相同的创意来发掘用户。在此方案中，如下面的步骤所述，创建具有两个特征的区段。

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. 您必须使用基于规则的特征来定义要实时触发的取消区段的印象事件。Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
1. 将频率控件应用于第二个特征。如果您愿意，还可以添加新近度控件。Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. 将区段映射到任意数量的实时服务器目标目标。Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

在这种情况下，一旦用户累计了三次以上的展示次数，他们将从此区段中删除，并且不再看到此特定创意。

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

请记住与处理相关的这些方面：

* 为了实现实时取消细分功能，您必须将所需的区段映射到实时服务器到服务器目标。
* For devices connected to a device by a [device graph](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. [设备图表选项和设备取消分段中描述了此限制](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation)。
* 取消区段命令将包含在批处理文件中，每24小时发送到目标，对于设备图表连接的多个设备。
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. For traits that have a [!UICONTROL time-to-live (TTL)] value, even if a trait [!DNL TTL] is met, the device will *not* automatically be unsegmented until the device is next seen in real-time.​ Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).​

## Important Aspects to Note - Timing {#timing-notes}

请记住与时间相关的这些方面：

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).