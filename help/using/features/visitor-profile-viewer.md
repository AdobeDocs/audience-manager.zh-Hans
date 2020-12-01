---
description: 使用访客用户档案查看器可显示当前浏览器的用户用户档案的当前状态，包括其特征和区段。 对于每个特征，您可以视图其SID、名称、访客特征的实现方式（第一方或第三方）、实现日期和实现频率的详细信息。 对于每个区段，您可以视图其SID、名称和区段成员资格日期。 您还可以视图访客用户档案，使其成为另一个Audience Manager用户档案ID(UUID)。 访客用户档案查看器有助于排除故障。
keywords: location;location parameter
seo-description: 使用访客用户档案查看器可显示当前浏览器的用户用户档案的当前状态，包括其特征和区段。 对于每个特征，您可以视图其SID、名称、访客特征的实现方式（第一方或第三方）、实现日期和实现频率的详细信息。 对于每个区段，您可以视图其SID、名称和区段成员资格日期。 您还可以视图访客用户档案，使其成为另一个Audience Manager用户档案ID(UUID)。 访客用户档案查看器有助于排除故障。
seo-title: 访客配置文件查看器
solution: Audience Manager
title: 访客配置文件查看器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 2%

---


# 访客配置文件查看器 {#visitor-profile-viewer}

使用[!UICONTROL Visitor Profile Viewer]可显示当前浏览器的用户用户档案的当前状态，包括其特征和区段。 对于每个特征，您可以视图其[!UICONTROL SID]、名称、访客特征的实现方式（第一方或第三方）、实现日期和实现频率。 对于每个区段，您可以视图其[!UICONTROL SID]、名称和区段成员资格日期。 您还可以视图访客用户档案，以获取另一个Audience Manager用户档案ID([!UICONTROL UUID])。 [!UICONTROL Visitor Profile Viewer]对于故障排除有用。

>[!NOTE]
>
>* 访问需要[!UICONTROL Administrator]权限。
>* 在用户界面中显示有关已实现区段和已载入特征的信息之前，有24小时的延迟。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. 单击 **[!UICONTROL Tools]** > **[!UICONTROL Visitor Profile Viewer]**.

1. *（可选）* 单击特征名称以在中显示该特征 [!UICONTROL Trait Builder]。

   有关详细信息，请参阅[Traits](../features/traits/trait-details-page.md)。

1. *（可选）单* 击区段名称以在中显示该区段 [!UICONTROL Segment Builder]。

   有关详细信息，请参阅[区段](../features/segments/segments-purpose.md)。

1. *(视情况* 而定) **[!UICONTROL UUID]** 在框中，指定其他Audience Manager用户档案ID，然 **[!UICONTROL Refresh]** 后单击以视图该用户的特征和区段。