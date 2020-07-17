---
description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-description: 当有多个设备与用户连接时，如果在其中任一设备上产生了特定体验，“即时跨设备抑制”功能会禁止这些设备上的用户。使用这项“即时跨设备抑制”功能，可为您的用户提供一致的跨设备体验。Audience Manager 中的实时取消区段功能可提供这种体验。
seo-title: 即时跨设备抑制
title: 即时跨设备抑制
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 15%

---


# 即时跨设备抑制 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 即当任何这些设备上都出现特定体验时，能够抑制连接到它们的多个设备上的用户。 Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Audience Manager 中的实时取消区段功能可提供这种体验。

## 概述 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 提供两个主要用例： 改善了用户体验和媒体效率。

* **改进的用户体验**: 已购买您的产品或服务的用户将看不到与购买前相同的创意。 相反，您可以显示您知道尚未购买的产品或服务的追加销售或交叉销售消息。
* **媒体效率**: 通过在所有渠道应用全局频率上限，优化活动 [!DNL DSP]支出。 对于属于用户的多个设备，可以实时地调节频率盖。

在用户档案合并规则和设备非分割过程中，对实时非 [分割的技术细节进行了详细描述](merge-rule-unsegment.md)。 阅读上述使用案例的实际实施。

## 转换后不目标 {#do-not-target-once}

确保您的用户已转换(购买产品、获得订阅等) 将看不到与转换前相同的消息。 可以使用逻辑获 [!UICONTROL AND NOT] 得此值，如下所示。

1. 使用两个特征创建区段，并 [!UICONTROL AND NOT] 使用逻辑，如下图所示。 必须使用基于规则的特征来定义要实时触发的取消段的转换事件。 阅读有关如何创建基 [于规则的特征的更多信息](../traits/create-onboarded-rule-based-traits.md)。
2. 将区段映射到任意数量的实时服务器到服务器目标。 阅读有关如何将区段添加到服 [务器到服务器目标的信息](../destinations/add-edit-segments.md)。

只要访客尚未转换，他们就有资格加入该区段。 一旦他们符合转换特征，就不再遵循段规则，并立即从段中删除。

![](assets/and_not_use_case.png)

## 在x印象后不目标 {#do-not-target-after-x}

通过设置最近频率和频率控制，您可以确保不会以相同的创意淹没用户。 在此方案中，创建具有两个特征的区段，如以下步骤所述。

1. 使用两个特征创建区段，并 [!UICONTROL AND] 使用逻辑，如下图所示。 必须使用基于规则的特征来定义要实时触发的取消区段的印象事件。 阅读有关如何创建基 [于规则的特征的更多信息](../traits/create-onboarded-rule-based-traits.md)。
   >[!NOTE]
   >
   >您可以使用 [!UICONTROL Actionable Log Files] 或根 [!UICONTROL Pixel Calls] 据用户印象创建特征。 阅读有关可操作 [的日志文件](../../integration/media-data-integration/actionable-log-files.md) 和像 [素调用的更多信息](../../integration/media-data-integration/impression-data-pixels.md)。
2. 对第二个特征应用频率控制。 如果您愿意，还可以添加最近使用的控件。 阅读有关如 [何应用最近和频率控制的更多信息](../segments/recency-and-frequency.md)。
3. 将区段映射到任意数量的实时服务器到服务器目标。 阅读有关如何将区段添加到服 [务器到服务器目标的信息](../destinations/add-edit-segments.md)。

在此方案中，用户累积了超过三个印象后，将从此区段中删除这些印象，不会再看到此特定创意。

![](assets/impressions_use_case.png)

## 注释的重要方面——处理 {#processing-notes}

切记与处理相关的以下方面：

* 要使实时取消细分功能正常工作，您必须将所需细分映射到实时服务器到服务器目标。
* 对于通过设备图连接到设备 [的设备](profile-link-use-case.md#recommendations)，我们对评估和取消分段强制实施四设备限制。 此限制在设备图 [形选项和设备取消分段中介绍](merge-rule-unsegment.md#device-graph-options-unsegmentation)&#x200B;。
* unsegment命令将包含在批处理文件中，该文件每24小时发送一次至目标，用于通过设备图形连接的多个设备。
* 设备必须实时显示(在Edge上 [](../../reference/system-components/components-edge.md) )，以实时提示细分评估。 对于满足该特 [!UICONTROL time-to-live (TTL)] 征时的特 [!DNL TTL] 征，设备将在24小时内通过批处理文件自动取消分&#x200B;段。 阅读有关如何设置特 [征到期间隔的更多信息](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)。
* 如果您实时 [!UICONTROL DCS API] 使用基于到板规则的特征，则可以使用逻辑触发取消细 [!UICONTROL AND NOT] 分。 阅读有关将 [数据发送到DCS API的更多信息](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)&#x200B;。

## 注意的重要方面——时间 {#timing-notes}

请牢记与时间有关的以下方面：

* 段将存储在Edge [上](../../reference/system-components/components-edge.md) ，与设备用户档案存储在Edge上的同一时间段 [!UICONTROL Edge]，即自上次实时交互以来的14天。 在我们的数据保留常见问题解答中阅读 [有关数据保留的更多信息](../../faq/faq-privacy.md#data-retention-faq)。
* 未分段操作在不同区域之间传播大约需要24 [!DNL DCS] 小时。 进一步了解我们 [!DNL DCS] 的 [地区](../..//reference/system-components/components-data-collection.md) , [这里](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)。
