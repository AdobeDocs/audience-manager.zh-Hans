---
description: 使用访客配置文件查看器显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其SID、名称、有关如何实现访客特征（第一方或第三方）的详细信息、实现日期和实现频率。 对于每个区段，您可以查看其SID、名称和区段成员资格日期。 您还可以查看其他Audience Manager配置文件ID (UUID)的访客配置文件。 访客资料查看器有助于进行故障排除。
keywords: 位置；位置参数
seo-description: Use the Visitor Profile Viewer to display the current state of a user profile for the current browser, including its traits and segments. For each trait, you can view its SID, name, details about how visitor traits were realized (first- or third-party), the realization date, and the frequency of realizations. For each segment, you can view its SID, name, and the segment membership date. You can also view the visitor profile for another Audience Manager profile ID (UUID). The Visitor Profile Viewer is helpful for troubleshooting purposes.
seo-title: Visitor Profile Viewer
solution: Audience Manager
title: 访客资料查看器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# 访客资料查看器 {#visitor-profile-viewer}

使用[!UICONTROL Visitor Profile Viewer]显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其[!UICONTROL SID]、名称、有关如何实现访客特征（第一方或第三方）的详细信息、实现日期和实现频率。 对于每个区段，您可以查看其[!UICONTROL SID]、名称和区段成员资格日期。 您还可以查看其他Audience Manager配置文件ID ([!UICONTROL UUID])的访客配置文件。 [!UICONTROL Visitor Profile Viewer]有助于进行疑难解答。

>[!NOTE]
>
>* 访问需要[!UICONTROL Administrator]权限。
>* 在用户界面中出现有关已实现的区段和载入的特征的信息之前，存在24小时的延迟。

<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 单击&#x200B;**[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**。

1. *（可选）*&#x200B;单击特征名称可在[!UICONTROL Trait Builder]中显示该特征。

   有关详细信息，请参阅[特征](../features/traits/trait-details-page.md)。

1. *（可选）*&#x200B;单击区段名称以在[!UICONTROL Segment Builder]中显示该区段。

   有关详细信息，请参阅[区段](../features/segments/segments-purpose.md)。

1. *（有条件）*&#x200B;在&#x200B;**[!UICONTROL UUID]**&#x200B;框中，指定其他Audience Manager配置文件ID，然后单击&#x200B;**[!UICONTROL Refresh]**&#x200B;以查看该用户的特征和区段。
