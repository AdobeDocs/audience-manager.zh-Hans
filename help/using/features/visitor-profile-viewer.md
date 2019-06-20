---
description: 使用访客配置文件查看器显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。对于每个特征，您可以查看其SID、名称、有关如何实现访客特征的详细信息(第一方或第三方)、实现日期和真实性。对于每个区段，您可以查看其SID、名称和区段成员关系日期。您还可以查看其他Audience Manager配置文件ID(UUID)的访客配置文件。访客配置文件查看器有助于进行疑难解答。
keywords: 位置；位置参数
seo-description: 使用访客配置文件查看器显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。对于每个特征，您可以查看其SID、名称、有关如何实现访客特征的详细信息(第一方或第三方)、实现日期和真实性。对于每个区段，您可以查看其SID、名称和区段成员关系日期。您还可以查看其他Audience Manager配置文件ID(UUID)的访客配置文件。访客配置文件查看器有助于进行疑难解答。
seo-title: 访客个人资料查看器
solution: Audience Manager
title: 访客个人资料查看器
uuid: 77ffe134-e08 f-41de-8fc4-15494847b1 d0
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Visitor Profile Viewer {#visitor-profile-viewer}

Use the [!UICONTROL Visitor Profile Viewer] to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its [!UICONTROL SID], name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its [!UICONTROL SID], name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID ([!UICONTROL UUID]). [!UICONTROL Visitor Profile Viewer] 这有助于解决问题。

>[!NOTE]
>
>* Access requires [!UICONTROL Administrator] permissions.
>* 有关已实现区段和具有载入特征的信息出现在用户界面中的信息有24小时延迟。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Click **[!UICONTROL Tools]** &gt; **[!UICONTROL Visitor Profile Viewer]**.

1. *(可选)* 单击特征名称以在该特征中显示该特征 [!UICONTROL Trait Builder]。

   For more information, see [Traits](../features/traits/trait-details-page.md).

1. *(可选)* 单击区段名称，在该区段中显示该区段 [!UICONTROL Segment Builder]。

   For more information, see [Segments](../features/segments/segments-purpose.md).

1. *(视情况而定)* 在框 **[!UICONTROL UUID]** 中指定其他Audience Manager配置文件ID，然后单击 **[!UICONTROL Refresh]** 以查看该用户的特征和区段。