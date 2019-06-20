---
description: 常见报告相关问题和问题。
seo-description: 常见报告相关问题和问题。
seo-title: 报表常见问题解答
solution: Audience Manager
title: 报表常见问题解答
uuid: 78cd6c86-8a4a-4748-ab71-b6 e8 d6078 c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 报表常见问题解答{#reporting-faq}

常见报告相关问题和问题。

<br> 

<!-- 

faq_reports.xml

 -->

**对于新载入的特征，为什么[!UICONTROL Trait Graph]有时显示低于预期的数字或0？**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn&#39;t show any results or shows lower than expected numbers. 当我们收到的数据量如此之大时，入站处理作业将无法完成摄取此信息，直到该天的报告截止日期结束。

As a result, this data is sent to the reporting system late and won&#39;t show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br> 

**[!UICONTROL Overlap]报表中缺少部分区段。Where are they?**

为了帮助降低计算需求，这些报告从结果中忽略了统计不重要的数据。您的区段没有丢失，因为它们没有产生有意义的结果，或您可以定位的有用的大量用户。另请参阅：

* [报告和数据采样方法](../reporting/report-sampling.md)
* [在重叠和常规报告中计算唯一用户](../reporting/unique-user-counts.md)。

<br> 

**如果我运行电子邮件营销活动，如何确定重定向的用户是否从该营销活动来到我的网站或从其他来源访问？**

将特定于营销活动的查询字符串追加到要监视的站点部分的URL。接下来，设置特征规则以捕获此变量。For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br> 

**实时和总细分人口统计之间有何区别？**

* **实时：** 在设定的时间段内属于区段并处于活动状态的唯一用户的数量(即 [!DNL Audience Manager] ，必须在特定时间段内为该用户已记录活动)。

* **总细分人口：** 当前在该区段中进行分类的所有用户的集合。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**我的区段只包含一个特征。查看报告指标时，其计数不匹配。为什么？**

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

**我将文件放入一个文件，并且我的入站收据显示大量成功处理的记录，但报告显示的数量较少。为什么？**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br> 

**为什么我跨设备的跨设备特征的特征统一远远超出已载入记录的总数？**

如果您将跨设备数据提供商的文件停放在客户ID之外，Audience Manager会执行查找以获取所有与载入的客户ID关联的设备ID。Audience Manager随后将载入的特征分配给与客户ID关联的设备ID。

例如，假定您已载入100个记录。对于每个客户ID，AAM平均关联三个设备ID。因此，已载入的特征分配给300台设备ID。

单个跨设备客户ID可以与多个设备ID关联的原因有两个原因：

* 用户从多台计算机/浏览器登录到同一跨设备帐户。
* 用户正在清除他们的cookies。注意：“放弃”cookies在用户不活动的120天后被删除。

<br> 

**为什么我[!UICONTROL Total Trait Realizations]的星座特征总是0？**

[!UICONTROL Total Trait Realizations] 与页面加载相对应。[!UICONTROL Total Trait Realizations] 提供实时触发特定特征的次数。此编号只针对基于规则的特征计算。Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br> 

**我创建了一个特征，而且它[!UICONTROL Trait Graph]显示的数量比它更[!UICONTROL Unique Trait Realizations]大[!UICONTROL Total Trait Population]。Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. The [!UICONTROL Total Trait Population] should be larger than the [!UICONTROL Unique Trait Realizations] within a couple of days.
