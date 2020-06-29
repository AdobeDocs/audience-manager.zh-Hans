---
description: 取消分段描述了将设备用户档案从区段中取消资格和删除的流程。 您能否从区段中删除设备用户档案取决于用于创建用户档案合并规则的设备选项。
seo-description: 取消分段描述了将设备用户档案从区段中取消资格和删除的流程。 您能否从区段中删除设备用户档案取决于用于创建用户档案合并规则的设备选项。
seo-title: 配置文件合并规则和设备取消分段过程
solution: Audience Manager
title: 配置文件合并规则和设备取消分段过程
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 6%

---


# 配置文件合并规则和设备取消分段过程 {#profile-merge-rules-and-device-un-segmentation-processes}

取消分段描述了将设备用户档案从区段中取消资格和删除的流程。 您能否从区段中删除设备用户档案取决于用于创建设备的设备选项 [!UICONTROL Profile Merge Rule]。

## 可用设备选项 {#device-options}

作为提醒，在 [!UICONTROL Device Options] 创建或编辑 [!UICONTROL Profile Merge Rules Setup] 时，部分中提供 [!UICONTROL Profile Merge Rule]。

## 当前设备用户档案选项和设备取消分段 {#current-device-profile-options}

**[!UICONTROL Device Profile]** 是设备的默认用户档案选 [!UICONTROL Profile Merge Rule]项 [!DNL Audience Manager] 可以在您使用该选项时从区段中删 [!UICONTROL Profile Merge Rule] 除设备 **[!UICONTROL Device Profile]** 用户档案。 在这些情况下，当出现以下情况时，将发生非分段：

* 设备用户档案已停用120天。 每周的数据清理过程会从您的细分中删除非活动设备用户档案。
* 设备不再有资格获取区段，因为对设备用户档案的更新或更改会取消该区段的资格。 当区段资格条件发生更改，或者您将运 [!DNL AND NOT] 算符应用于区段规则，或 [者指定使用小于](../segments/recency-and-frequency.md) /等于设置的最近和频率条件时，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了使用案例](instant-cross-device-suppression.md) 。

![仅限设备](assets/device-only.png)

## 无设备选项和设备取消分段 {#no-device-option}

[!DNL Audience Manager] 使用+选项时，可以从区段中删 [!UICONTROL Profile Merge Rule] 除跨 **[!UICONTROL Current Authenticated Profiles]** 设备 **[!UICONTROL No Device Profile]** ID。 在这些情况下，当跨设备ID不再符合区段资格时，会发生取消分段，因为对跨设备用户档案的更新或更改会取消分段资格。 当区段资格条件发生更改，或者您将运 [!UICONTROL AND NOT] 算符应用于区段规则，或 [者指定使用小于](../segments/recency-and-frequency.md) /等于设置的最近和频率条件时，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了使用案例](instant-cross-device-suppression.md) 。

![](assets/current-no-device.png)

## 设备图形选项和设备未分段 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] 使用设备图形选项时，可以从区段 [!UICONTROL Profile Merge Rule] 中删除多个设备用户档案。 当设备图形中的设备的合并用户档案不再符合区段条件时，会发生取消分段，因为对此合并用户档案的更新或更改会使其不符合区段条件。 当区段资格条件发生更改，或者您将运 [!UICONTROL AND NOT] 算符应用于区段规则，或 [者指定使用小于](../segments/recency-and-frequency.md) /等于设置的最近和频率条件时，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了使用案例](instant-cross-device-suppression.md) 。

>[!NOTE]
>
>**对100台设备进行细分评估和取消资格限制**。
>Audience Manager使用设备图表的用户档案合并规则评估区段时，最多可合并100台设备。 Audience Manager通过经过身份验证的用户档案（跨设备ID）评估当前设备以及最多99 [个与当前设备链](../../reference/visitor-authentication-states.md) 接的设备。 如果发出未分段信号，则当前设备和附加设备将从目标的分段中移除。

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [即时跨设备抑制](instant-cross-device-suppression.md)

