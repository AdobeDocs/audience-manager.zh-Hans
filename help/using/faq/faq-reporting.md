---
description: 常见报告相关问题。
seo-description: 常见报告相关问题。
seo-title: 报表常见问题解答
solution: Audience Manager
title: 报表常见问题解答
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 报表常见问题解答{#reporting-faq}

常见报告相关问题。

<br> 

<!-- 

faq_reports.xml

 -->

**对于新的已载入特征，为什么这些特征[!UICONTROL Trait Graph]有时显示的数字低于预期数字或0?**

有时，在上传特征后， [!UICONTROL Trait Graph] 不会显示任何结果或显示低于预期数字。 当我们收到的数据量如此之大，以致入站处理作业直到该日的报告截止日期之后才能完成收集此信息时，会发生这种情况。

因此，该数据会延迟发送到报告系统，并且不会在用于绘制报告的1天报告间隔中显示 [!UICONTROL Trait Graph]。 但是，您可以在第二天的趋势或一般报表中以7、14、30和60天报告间隔查 [看](../reporting/trend-reports.md#trend-report-overview)[此数据](../reporting/general-reports.md#general-reports-overview) 。

<br> 

**报表中缺少某些区[!UICONTROL Overlap]段。 他们在哪？**

为了帮助减少计算需求，这些报告会忽略从结果中统计上微不足道的数据。 您的区段不会丢失，它们会被丢弃，因为它们不会产生有意义的结果或您可以定位的有用用户池。 另请参阅：

* [报告和数据采样方法](../reporting/report-sampling.md)
* [对重叠和常规报告中的唯一用户计数](../reporting/unique-user-counts.md)。

<br> 

**如果我运行电子邮件营销活动，如何确定重定向用户是从该营销活动还是从其他来源进入我的网站？**

在要监视的站点部分的URL后面附加市场活动特定的查询字符串。 接下来，设置一个特征规则以捕获此变量。 例如，如果您的URL通过类似的系列活动ID，则创建一个特征规则以从变量中捕获该数据，并使用一个特征规则来查找标题(如 `www.test123.com/electronics?campaign=123``h_referer``h_referer = 'campaign=123'`)。

<br> 

**实时和总细分人口计数之间有何差异？**

* **** 实时：在设置的时间段内属于区段并在您的属性上处于活动状态的唯一用户数(即， [!DNL Audience Manager] 在特定时间段内该用户必须已记录活动)。

* **** 细分总数：该区段中当前已分类的所有用户的汇总。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**我有一段只有一个特质。 当我查看报告指标时，其计数不匹配。 为什么？**

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

**“入站”时，文件和“入站”接收显示大量成功处理的记录，但报告显示的数量要低得多。 为什么？**

在后端，已载入的数据仅会附加到在AAM中仍处于活动状态的用户(用户在过去120天 [!UICONTROL DCS] 中必须有最近的活动)。 因此，如果您为已过期的用户提供数据 [!DNL Audience Manager], [!UICONTROL Inbound][!UICONTROL User Profile Store] 则可能会告诉您已载入了特定数量的用户记录，但是，如果这些用户没有任何近期活动，则当这些数据到达我们时，会丢弃该数据，并且报告会显示该数据。

<br> 

**为什么我的跨设备已载入特征的特征单位比已载入记录的总数高得多？**

如果您为已键入客户ID的跨设备数据提供者安装了文件，Audience manager会执行查找以获取与每个已载入的客户ID关联的所有设备ID。 然后，Audience manager将载入的特征分配给与客户ID关联的设备ID。

例如，假设您已载入100条记录。 对于每个客户ID,AAM平均有三个设备ID。 因此，已载入的特征被分配给300个设备ID。

单个跨设备客户ID可以与多个设备ID关联有两个原因：

* 用户正在从多台计算机／浏览器登录到同一跨设备帐户。
* 用户正在清除其cookie。 注意：在用户120天不活动后，将删除“已放弃”Cookie。

<br> 

**为什么我[!UICONTROL Total Trait Realizations]的亲生特征总是0?**

[!UICONTROL Total Trait Realizations] 与页面加载相对应。 [!UICONTROL Total Trait Realizations] 提供该特定特征实时触发的次数。 此数字仅针对基于规则的特征计算。 已载入的特征始终 [!UICONTROL Total Trait Realizations] 显示为0。

<br> 

**我创建了一个特征，[!UICONTROL Trait Graph]并且显示的数量比[!UICONTROL Unique Trait Realizations]上的要大[!UICONTROL Total Trait Population]。 这正常吗？**

您之所以看到这一点，是 [!UICONTROL Unique Trait Realizations] 因为它们是实时指标，但我们计算这些指标的报告工作 [!UICONTROL Total Trait Population] 并非实时。 在 [!UICONTROL Total Trait Population] 几天内，应该比 [!UICONTROL Unique Trait Realizations] 这个大。
