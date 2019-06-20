---
description: 避免将个人资料合并规则与设备图表结合使用，对于没有实时细分群体的细分而言。
seo-description: 避免将个人资料合并规则与设备图表结合使用，对于没有实时细分群体的细分而言。
seo-title: 配置文件合并规则的重要注意事项与设备图表
title: 配置文件合并规则的重要注意事项与设备图表
uuid: 93cd8861-210d-4c52-9cb7-6f2dd7dc7dc7dc7dc7dc7dc7dc7dc7dd7dc7dd7dc7dd7dc7dd7dc7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd7dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Important Considerations for Profile Merge Rules with Device Graphs {#important-considerations-for-profile-merge-rules-with-device-graphs}

Avoid using [!UICONTROL Profile Merge Rules] with a [!UICONTROL Device Graph] for segments which have little to no real-time segment population.

>[!IMPORTANT]
>
>[!UICONTROL Profile Merge Rule] 如果配置错误，导出到批处理目标的区段将明显低于预期。

Segments using a [Profile Merge Rule with a Device Graph](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) are only evaluated against devices seen in real-time on [Audience Manager’s Edge Servers](../../reference/system-components/components-edge.md) after the segment has been created.

Remember, a [!UICONTROL Profile Merge Rule] with a [!UICONTROL Device Graph] has one of the following device options selected, as shown below.

![](assets/pmr-considerations-1.png)

Devices that qualify for a segment in real-time are measured by the [segment’s real-time population](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

较低的实时细分群体意味着很少有资格获得该区段的设备实时查看。For best performance, segments with little to no real-time population should use a [!UICONTROL Profile Merge Rule] set to evaluate the *[!UICONTROL Current Device]*, like in the image below.

![](assets/pmr-considerations-3.png)

Setting the [!UICONTROL Profile Merge Rule] to evaluate the *[!UICONTROL Current Device]* ensures that all devices (not just those seen in real-time) are evaluated for the segment. 所有符合区段资格的设备均由区段总人数定义，如下所示。

![](assets/pmr-considerations-4.png)