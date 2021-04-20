---
description: 取消分段描述取消分段和从分段中删除设备用户档案的进程。 您能否从区段中删除设备用户档案取决于用于创建用户档案合并规则的设备选项。
seo-description: 取消分段描述取消分段和从分段中删除设备用户档案的进程。 您能否从区段中删除设备用户档案取决于用于创建用户档案合并规则的设备选项。
seo-title: 配置文件合并规则和设备取消分段过程
solution: Audience Manager
title: 配置文件合并规则和设备取消分段过程
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# 配置文件合并规则和设备取消分段过程 {#profile-merge-rules-and-device-un-segmentation-processes}

取消分段描述取消分段和从分段中删除设备用户档案的进程。 能否从区段中删除设备用户档案取决于用于创建[!UICONTROL Profile Merge Rule]的设备选项。

## 可用设备选项{#device-options}

作为提醒，在创建或编辑[!UICONTROL Profile Merge Rule]时，[!UICONTROL Profile Merge Rules Setup]部分提供[!UICONTROL Device Options]。

## 当前设备用户档案选项和设备取消分段{#current-device-profile-options}

**[!UICONTROL Device Profile]** 是设备的默认用户档案选 [!UICONTROL Profile Merge Rule]项[!DNL Audience Manager] 可以在您使用选项时从区段中删 [!UICONTROL Profile Merge Rule] 除设备 **[!UICONTROL Device Profile]** 用户档案。在这些情况下，当出现以下情况时，会发生取消分段：

* 设备用户档案已停用120天。 每周的数据清理过程会从您的区段中删除非活动设备用户档案。
* 设备不再有资格获得区段，因为对设备用户档案的更新或更改会取消区段资格。 当区段资格条件发生更改，或者您将[!DNL AND NOT]运算符应用于区段规则，或指定使用小于/等于设置的[最近和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 [即时跨设备抑制](instant-cross-device-suppression.md)文档中介绍了用例。

![仅限设备](assets/device-only.png)

## 无设备选项和设备取消分段{#no-device-option}

[!DNL Audience Manager] 可以在使用+选项时从区段中删 [!UICONTROL Profile Merge Rule] 除跨设 **[!UICONTROL Current Authenticated Profiles]** 备 **[!UICONTROL No Device Profile]** ID。在这些情况下，当跨设备ID不再符合区段资格时，会发生取消分段，因为对跨设备用户档案的更新或更改将取消分段资格。 当区段资格条件发生更改，或者您将[!UICONTROL AND NOT]运算符应用于区段规则，或指定使用小于/等于设置的[最近和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 [即时跨设备抑制](instant-cross-device-suppression.md)文档中介绍了用例。

![](assets/current-no-device.png)

## 设备图表选项和设备取消分段{#device-graph-options-unsegmentation}

[!DNL Audience Manager] 使用设备图表选项时，可以从区段 [!UICONTROL Profile Merge Rule] 中删除多个设备用户档案。当设备从设备图形的合并用户档案不再符合区段条件时，会发生取消分段，因为对此合并用户档案的更新或更改会使设备不再符合区段条件。 当区段资格条件发生更改，或者您将[!UICONTROL AND NOT]运算符应用于区段规则，或指定使用小于/等于设置的[最近和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 [即时跨设备抑制](instant-cross-device-suppression.md)文档中介绍了用例。

>[!NOTE]
>
>**对100个设备进行细分评估和取消资格限制**。
>Audience Manager在使用设备图表的用户档案合并规则评估区段时合并多达100台设备。 Audience Manager通过[认证用户档案](../../reference/visitor-authentication-states.md)（跨设备ID）评估当前设备和最多99个与当前设备链接的设备。 如果发出未分段信号，则当前设备和其他设备将从目标的分段中删除。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [即时跨设备抑制](instant-cross-device-suppression.md)

