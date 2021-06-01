---
description: 使用访客配置文件查看器可显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其SID、名称、有关访客特征实现方式（第一方或第三方）的详细信息、实现日期和实现频率。 对于每个区段，您可以查看其SID、名称和区段成员资格日期。 您还可以查看其他Audience Manager配置文件ID(UUID)的访客配置文件。 访客资料查看器有助于进行疑难解答。
keywords: 位置；位置参数
seo-description: 使用访客配置文件查看器可显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其SID、名称、有关访客特征实现方式（第一方或第三方）的详细信息、实现日期和实现频率。 对于每个区段，您可以查看其SID、名称和区段成员资格日期。 您还可以查看其他Audience Manager配置文件ID(UUID)的访客配置文件。 访客资料查看器有助于进行疑难解答。
seo-title: 访客配置文件查看器
solution: Audience Manager
title: 访客配置文件查看器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: 特征
exl-id: 6c1ee14c-6f78-4e45-9b88-24ace8400079
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# 访客配置文件查看器 {#visitor-profile-viewer}

使用[!UICONTROL Visitor Profile Viewer]显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其[!UICONTROL SID]、名称、有关访客特征实现方式（第一方或第三方）的详细信息、实现日期和实现频率。 对于每个区段，您可以查看其[!UICONTROL SID]、名称和区段成员资格日期。 您还可以查看其他Audience Manager配置文件ID([!UICONTROL UUID])的访客配置文件。 [!UICONTROL Visitor Profile Viewer]有助于进行故障排除。

>[!NOTE]
>
>* 访问需要[!UICONTROL Administrator]权限。
>* 在用户界面中显示有关已实现区段和已载入特征的信息之前，会有24小时的延迟。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 单击 **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *（可选）* 单击特征名称以在中显示该特 [!UICONTROL Trait Builder]征。

   有关更多信息，请参阅[特征](../features/traits/trait-details-page.md)。

1. *（可选）* 单击区段名称以在中显示该区 [!UICONTROL Segment Builder]段。

   有关更多信息，请参阅[区段](../features/segments/segments-purpose.md)。

1. *（视情况而定）* 在框中， **[!UICONTROL UUID]** 指定另一个Audience Manager配置文件ID，然后单 **[!UICONTROL Refresh]** 击以查看该用户的特征和区段。
