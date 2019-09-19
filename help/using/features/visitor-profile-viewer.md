---
description: 使用访客配置文件查看器可显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其SID、名称、访客特征实现方式的详细信息（第一方或第三方）、实现日期和实现频率。 对于每个区段，您可以查看其SID、名称和区段成员日期。 您还可以查看其他Audience Manager配置文件ID(UUID)的访客配置文件。 访客资料查看器有助于排除故障。
keywords: 位置；位置参数
seo-description: 使用访客配置文件查看器可显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其SID、名称、访客特征实现方式的详细信息（第一方或第三方）、实现日期和实现频率。 对于每个区段，您可以查看其SID、名称和区段成员日期。 您还可以查看其他Audience Manager配置文件ID(UUID)的访客配置文件。 访客资料查看器有助于排除故障。
seo-title: 访客资料查看器
solution: Audience Manager
title: 访客资料查看器
uuid: 77ffe134-e08f-41de-8fc4-15494847b1d0
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


#  访客资料查看器 {#visitor-profile-viewer}

使用 [!UICONTROL Visitor Profile Viewer] 显示当前浏览器的用户配置文件的当前状态，包括其特征和区段。 对于每个特征，您可以查看其名称、访客特征的实现方式的详细信息（第一方或第三方）、实现日期和实现频率。 [!UICONTROL SID]对于每个区段，您可以查看其 [!UICONTROL SID]名称和区段会员资格日期。 您还可以查看其他Audience Manager配置文件ID()的访客配置[!UICONTROL UUID]文件。 该 [!UICONTROL Visitor Profile Viewer] 功能有助于疑难解答。

>[!NOTE]
>
>* 访问需要 [!UICONTROL Administrator] 权限。
>* 在用户界面中显示有关已实现区段和已载入特征的信息之前，有24小时的延迟。


<!-- 
Traits that are not part of a segment will not appear in the
<span class="wintitle"> Visitor Profile Viewer</span>.
-->

1. Click **[!UICONTROL Tools]** &gt; **[!UICONTROL Visitor Profile Viewer]**.

1. *（可选）* ，单击特征名称以在中显示该特征 [!UICONTROL Trait Builder]。

   有关详细信息，请参阅 [特征](../features/traits/trait-details-page.md)。

1. *（可选）* ，单击区段名称以在中显示该区段 [!UICONTROL Segment Builder]。

   For more information, see [Segments](../features/segments/segments-purpose.md).

1. *（视情况而定）* ，在框中 **[!UICONTROL UUID]** 指定另一个Audience Manager配置文件ID，然后单击 **[!UICONTROL Refresh]** 以查看该用户的特征和区段。