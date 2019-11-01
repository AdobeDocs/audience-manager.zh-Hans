---
description: 取消分段描述了将设备配置文件从区段中取消资格和删除的过程。 您能否从区段中删除设备配置文件取决于用于创建配置文件合并规则的设备选项。
seo-description: 取消分段描述了将设备配置文件从区段中取消资格和删除的过程。 您能否从区段中删除设备配置文件取决于用于创建配置文件合并规则的设备选项。
seo-title: 配置文件合并规则和设备取消分段过程
solution: Audience Manager
title: 配置文件合并规则和设备取消分段过程
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 配置文件合并规则和设备取消分段过程 {#profile-merge-rules-and-device-un-segmentation-processes}

取消分段描述了将设备配置文件从区段中取消资格和删除的过程。 您能否从区段中删除设备配置文件取决于用于创建设备的设备选项 [!UICONTROL Profile Merge Rule]。

## 可用的设备选项 {#device-options}

作为提醒，在创 [!UICONTROL Device Options] 建或编辑 [!UICONTROL Profile Merge Rules Setup] 时，部分中会显示这些 [!UICONTROL Profile Merge Rule]。

## 当前设备配置文件选项和设备取消分段 {#current-device-profile-options}

**[!UICONTROL Device Profile]** 是设备的默认配置文件选 [!UICONTROL Profile Merge Rule]项 [!DNL Audience Manager] 可以在您使用该选项时从区段中删除设 [!UICONTROL Profile Merge Rule] 备配置 **[!UICONTROL Device Profile]** 文件。 在这些情况下，当出现以下情况时，将发生取消分段：

* 设备配置文件已停用120天。 每周的数据清理过程可从您的区段中删除非活动的设备配置文件。
* 设备不再有资格获得区段，因为设备配置文件的更新或更改会取消区段资格。 当区段资格条件发生更改，或者您对区段规则应用运算符，或者指定使用小于／等于设置的 [!DNL AND NOT] 最近和频率条件时 [](../segments/recency-and-frequency.md) ，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了用例](instant-cross-device-suppression.md) 。

![仅限设备](assets/device-only.png)

## 无设备选项和设备取消分段 {#no-device-option}

[!DNL Audience Manager] 在您使用+选项时，可以从区段中删 [!UICONTROL Profile Merge Rule] 除跨设 **[!UICONTROL Current Authenticated Profiles]** 备ID **[!UICONTROL No Device Profile]** 。 在这些情况下，当跨设备ID不再符合区段资格时，会发生取消分段，因为对跨设备配置文件的更新或更改将取消分段资格。 当区段资格条件发生更改，或者您对区段规则应用运算符，或者指定使用小于／等于设置的 [!UICONTROL AND NOT] 最近和频率条件时 [](../segments/recency-and-frequency.md) ，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了用例](instant-cross-device-suppression.md) 。

![](assets/current-no-device.png)

## 设备图选项和设备取消分段 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] 使用设备图形选项时，可从区段中删除 [!UICONTROL Profile Merge Rule] 多个设备配置文件。 当设备图形中设备的合并配置文件不再符合区段的条件时，会发生取消分段，因为对此合并配置文件的更新或更改会使其不符合区段的条件。 当区段资格条件发生更改，或者您对区段规则应用运算符，或者指定使用小于／等于设置的 [!UICONTROL AND NOT] 最近和频率条件时 [](../segments/recency-and-frequency.md) ，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了用例](instant-cross-device-suppression.md) 。

>[!NOTE]
>
>**100个设备限制，用于评估和取消资格**。
>在使用设备图的配置文件合并规则评估区段时，Audience manager可合并多达100台设备。 Audience manager通过经过身份验证的配置文件 [（跨设备ID）评估当前设备以及最多99个与当前设备链](../../reference/visitor-authentication-states.md) 接的设备。 如果发出未分段信号，则当前设备和附加设备将从目标的分段中移除。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [即时跨设备抑制](instant-cross-device-suppression.md)

