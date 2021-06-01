---
description: 取消分段描述了从区段中取消设备配置文件资格和删除设备配置文件的流程。 能否从区段中删除设备配置文件取决于用于创建配置文件合并规则的设备选项。
seo-description: 取消分段描述了从区段中取消设备配置文件资格和删除设备配置文件的流程。 能否从区段中删除设备配置文件取决于用于创建配置文件合并规则的设备选项。
seo-title: 配置文件合并规则和设备取消分段过程
solution: Audience Manager
title: 配置文件合并规则和设备取消分段过程
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: 配置文件合并
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# 配置文件合并规则和设备取消分段过程 {#profile-merge-rules-and-device-un-segmentation-processes}

取消分段描述了从区段中取消设备配置文件资格和删除设备配置文件的流程。 能否从区段中删除设备配置文件取决于用于创建[!UICONTROL Profile Merge Rule]的设备选项。

## 可用设备选项{#device-options}

当您创建或编辑[!UICONTROL Profile Merge Rule]时， [!UICONTROL Device Options]在[!UICONTROL Profile Merge Rules Setup]部分中可用。

## 当前设备配置文件选项和设备取消分段{#current-device-profile-options}

**[!UICONTROL Device Profile]** 是的默认设备配置文件选 [!UICONTROL Profile Merge Rule]项。[!DNL Audience Manager] 当您使用选项时，可以从区段中删除设 [!UICONTROL Profile Merge Rule] 备配置 **[!UICONTROL Device Profile]** 文件。在这些情况下，会在以下情况下发生取消分段：

* 设备配置文件已处于非活动状态120天。 每周的数据清理过程会从您的区段中删除非活动的设备配置文件。
* 设备不再符合区段的条件，因为设备配置文件的更新或更改会取消该设备的资格。 当区段鉴别标准发生更改，或者将[!DNL AND NOT]运算符应用于区段规则，或指定使用小于/等于设置的[回访间隔和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 [Instant Cross-Device Suppression](instant-cross-device-suppression.md)文档中介绍了用例。

![仅限设备](assets/device-only.png)

## 无设备选项和设备取消分段{#no-device-option}

[!DNL Audience Manager] 当您使用+选项时，可以从区段中删 [!UICONTROL Profile Merge Rule] 除跨设 **[!UICONTROL Current Authenticated Profiles]** 备 **[!UICONTROL No Device Profile]** ID。在这些情况下，如果跨设备ID不再符合区段的条件，则会取消分段，因为跨设备配置文件的更新或更改会取消该区段的资格。 当区段鉴别标准发生更改，或者将[!UICONTROL AND NOT]运算符应用于区段规则，或指定使用小于/等于设置的[回访间隔和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 [Instant Cross-Device Suppression](instant-cross-device-suppression.md)文档中介绍了用例。

![](assets/current-no-device.png)

## 设备图选项和设备取消分段{#device-graph-options-unsegmentation}

[!DNL Audience Manager] 当您使用设备图选项时，可以从区段中删除 [!UICONTROL Profile Merge Rule] 多个设备配置文件。如果设备图中设备的合并配置文件不再符合区段的条件，则会取消分段，因为对此合并配置文件的更新或更改会使其不符合区段的条件。 当区段鉴别标准发生更改，或者将[!UICONTROL AND NOT]运算符应用于区段规则，或指定使用小于/等于设置的[回访间隔和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 [Instant Cross-Device Suppression](instant-cross-device-suppression.md)文档中介绍了用例。

>[!NOTE]
>
>**区段评估和取消资格的100个设备限制**。
>Audience Manager使用使用设备图的配置文件合并规则评估区段时，最多可合并100个设备。 Audience Manager通过[经过验证的配置文件](../../reference/visitor-authentication-states.md)（跨设备ID）评估当前设备和最多99个与当前设备链接的设备。 如果发出取消分段信号，则将从目标的区段中删除当前设备和其他设备。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
* [即时跨设备抑制](instant-cross-device-suppression.md)

