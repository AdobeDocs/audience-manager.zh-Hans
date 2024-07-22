---
description: 取消分段描述取消设备配置文件的资格并从区段中删除设备配置文件的流程。 能否从区段中删除设备配置文件取决于用于创建配置文件合并规则的设备选项。
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: 配置文件合并规则和设备取消分段过程
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# 配置文件合并规则和设备取消分段过程 {#profile-merge-rules-and-device-un-segmentation-processes}

取消分段描述取消设备配置文件的资格并从区段中删除设备配置文件的流程。 能否从区段中删除设备配置文件取决于用于创建[!UICONTROL Profile Merge Rule]的设备选项。

## 可用的设备选项 {#device-options}

提醒一下，当您创建或编辑[!UICONTROL Profile Merge Rule]时，[!UICONTROL Device Options]在[!UICONTROL Profile Merge Rules Setup]分区中可用。

## 当前设备配置文件选项和设备取消分段 {#current-device-profile-options}

**[!UICONTROL Device Profile]**&#x200B;是[!UICONTROL Profile Merge Rule]的默认设备配置文件选项。 当您的[!UICONTROL Profile Merge Rule]使用&#x200B;**[!UICONTROL Device Profile]**&#x200B;选项时，[!DNL Audience Manager]可以从区段中删除设备配置文件。 在这些条件下，取消分段会在以下情况下发生：

* 设备配置文件已停用120天。 每周数据清理过程会从区段中删除不活动的设备配置文件。
* 设备不再符合区段的条件，因为设备配置文件的更新或更改会取消该设备的资格。 当区段资格标准发生更改，或者将[!DNL AND NOT]运算符应用于区段规则，或者指定使用小于/等于设置的[回访间隔和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 在[即时跨设备抑制](instant-cross-device-suppression.md)文档中介绍了用例。

![仅设备](assets/device-only.png)

## 无设备选项和设备取消分段 {#no-device-option}

当您的[!UICONTROL Profile Merge Rule]使用&#x200B;**[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**&#x200B;选项时，[!DNL Audience Manager]可以从区段中删除跨设备ID。 在这些情况下，当跨设备ID不再符合区段的资格时，就会取消分段，因为更新或更改跨设备配置文件会取消该区段的资格。 当区段资格标准发生更改，或者将[!UICONTROL AND NOT]运算符应用于区段规则，或者指定使用小于/等于设置的[回访间隔和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 在[即时跨设备抑制](instant-cross-device-suppression.md)文档中介绍了用例。

![](assets/current-no-device.png)

## 设备图选项和设备取消分段 {#device-graph-options-unsegmentation}

当您的[!UICONTROL Profile Merge Rule]使用设备图选项时，[!DNL Audience Manager]可以从区段中删除多个设备配置文件。 当设备图中的设备合并配置文件不再符合区段资格时，会发生取消分段，因为更新或更改此合并配置文件会取消该设备在区段中的资格。 当区段资格标准发生更改，或者将[!UICONTROL AND NOT]运算符应用于区段规则，或者指定使用小于/等于设置的[回访间隔和频率](../segments/recency-and-frequency.md)条件时，会发生这种情况。 在[即时跨设备抑制](instant-cross-device-suppression.md)文档中介绍了用例。

>[!NOTE]
>
>区段评估和取消资格的设备限制为&#x200B;**100个**。
>在使用设备图的配置文件合并规则评估区段时，Audience Manager可合并最多100台设备。 Audience Manager通过[验证的配置文件](../../reference/visitor-authentication-states.md)（跨设备ID）评估当前设备和链接到当前设备的最多99台设备。 如果发出取消分段信号，则将从目标中的分段中删除当前设备和附加设备。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [即时跨设备抑制](instant-cross-device-suppression.md)
