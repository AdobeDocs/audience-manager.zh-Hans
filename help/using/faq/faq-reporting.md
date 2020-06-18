---
description: 与报告相关的常见问题。
seo-description: 与报告相关的常见问题。
seo-title: 报表常见问题解答
solution: Audience Manager
title: 报表常见问题解答
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---


# 报表常见问题解答{#reporting-faq}

与报告相关的常见问题。

<br> 

<!-- 

faq_reports.xml

 -->

**对于新的已载入特征，为什[!UICONTROL Trait Graph]么有时显示低于预期数或0?**

有时，上传特征后， [!UICONTROL Trait Graph] 不会显示任何结果或显示低于预期的数字。 当我们收到的数据量如此之大，以至于入站处理作业直到该天的报告截止日期之后才能完成接收此信息时，会发生这种情况。

结果，该数据被延迟地发送到报告系统，并且不会在用于绘制该数据的1天报告间隔中出现 [!UICONTROL Trait Graph]。 但是，您可以在7天、14天、30天和60天报告间隔内视图此数据， [在次](../reporting/trend-reports.md#trend-report-overview) 日 [的趋势](../reporting/general-reports.md#general-reports-overview) 报告或一般报告中。

<br> 

**报表中缺少某些[!UICONTROL Overlap]区段。 他们在哪？**

为了减少计算需求，这些报告会忽略统计上微不足道的数据。 您的区段不会缺失，它们会被丢弃，因为它们不会产生有意义的结果或您可以目标的有用用户池。 另请参阅：

* [报告和数据采样方法](../reporting/report-sampling.md)
* [对重叠和一般报告中的唯一用户进行计数](../reporting/unique-user-counts.md)。

<br> 

**如果我运行电子邮件营销活动，如何确定重定向用户是从该活动还是从其他来源来到我的网站？**

在要监视的站点部分的URL后面附加特定于活动的查询字符串。 然后，设置特征规则以捕获此变量。 例如，如果URL以这样的活动ID传递 `www.test123.com/electronics?campaign=123`，则创建一个特征规则，用一个特征规则从变量中捕获该，该特征规则 `h_referer` 查找类似标题的特征 `h_referer = 'campaign=123'`)。

<br> 

**实时和总细分人口计数之间有何差异？**

* **实时：** 在设置的时间段内属于区段并且在您的属性上处于活动状态的唯一用户数(即 [!DNL Audience Manager] ，该用户在特定时间段内必须已记录活动)。

* **细分总人口：** 该区段中当前已分类的所有用户的汇总。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**我有一段只包含一个特质。 当我查看报告指标时，他们的数量不匹配。 为什么？**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**如果入站文件，则“入站”收据会显示大量成功处理的记录，但报告显示的数量要低得多。 为什么？**

在后端，已载入的数据仅会附加到在AAM中仍处于活动状态的用户(用户在过去120天 [!DNL DCS] 中必须具有最近活动)。 因此，如果您为已过期的用户提供数据 [!DNL Audience Manager], [!UICONTROL Inbound] 则可能会告诉您已载入了特定数量的用户记录，但如果这些用户没有任何最近活动，则此数据将在到达我们的报告时 [!UICONTROL User Profile Store] 丢弃，将显示。

<br> 

**为什么我的跨设备已载入特征的特征单位比已载入记录的总数高得多？**

如果您为锁定了客户ID的跨设备数据提供者安装了文件，Audience Manager将执行查找以获取与每个已载入的客户ID关联的所有设备ID。 然后，Audience Manager将载入的特征分配给与客户ID关联的设备ID。

例如，假定您已载入100条记录。 平均来说，对于每个客户ID,AAM都关联了三个设备ID。 因此，已载入的特征被分配给300个设备ID。

单个跨设备客户ID可以与多个设备ID关联的原因有二：

* 用户正从多台计算机／浏览器登录到同一跨设备帐户。
* 用户正在清除其cookie。 注意： 在用户120天不活动后，将删除“已放弃”cookie。

<br> 

**为什么我[!UICONTROL Total Trait Realizations]的个性总是0?**

[!UICONTROL Total Trait Realizations] 与页面加载相对应。 [!UICONTROL Total Trait Realizations] 提供该特定特征实时触发的次数。 此数字仅针对基于规则的特征计算。 已载入的特征 [!UICONTROL Total Trait Realizations] 始终显示为0。

<br> 

**我创建了一个特[!UICONTROL Trait Graph]征，显示的数[!UICONTROL Unique Trait Realizations]量比[!UICONTROL Total Trait Population]。 这正常吗？**

您之所以看到这一点， [!UICONTROL Unique Trait Realizations] 是因为它们是实时指标，但是我们计算报告的工作 [!UICONTROL Total Trait Population] 并不是实时的。 在 [!UICONTROL Total Trait Population] 两天内， [!UICONTROL Unique Trait Realizations] 应该比大。
