---
description: 常见报表相关问题。
seo-description: 常见报表相关问题。
seo-title: 报表常见问题解答
solution: Audience Manager
title: 报表常见问题解答
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting Reference
exl-id: 1e6531b2-bb39-4056-9d5e-164f50955f99
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 99%

---

# 报表常见问题解答{#reporting-faq}

常见报表相关问题。

<br> 

<!-- 

faq_reports.xml

 -->

**对于新载入的特征，为何 [!UICONTROL Trait Graph] 显示的数量有时低于预期值或为 0？**

有时，上传特征后，[!UICONTROL Trait Graph] 不会显示任何结果或显示的数量低于预期值。当我们收到的数据量太大，以至于入站处理作业要到当天的报告截止时间之后才能摄取完此信息时，会发生这种情况。

在这种情况下，此数据会被延迟发送到报告系统，并且不会在报告时间间隔为 1 天（绘制 [!UICONTROL Trait Graph] 时使用的报告时间间隔是 1 天）的报表中显示。但是，您可以于次日在报告时间间隔为 7 天、14 天、30 天和 60 天的[趋势报表](../reporting/trend-reports.md#trend-report-overview)或[常规报表](../reporting/general-reports.md#general-reports-overview)中查看此数据。

<br> 

**[!UICONTROL Overlap] 报表中缺少某些区段。这些区段在何处？**

为了帮助减少计算需求，这些报表会在结果中忽略统计上没有显著意义的数据。所以，您的区段并不是缺失，而是被丢弃，因为它们不会产生有意义的结果，或可定位的有用用户池。另请参阅：

* [报表和数据取样方法](../reporting/report-sampling.md)
* [对重叠报表和常规报表中的独特用户进行计数](../reporting/unique-user-counts.md)。

<br> 

**在运行电子邮件营销活动时，如何确定用户是通过该活动还是其他来源重定向到我的网站？**

在要监视的网站部分的 URL 后面附加一个特定于促销活动的查询字符串。然后，设置一个特征规则以捕获此变量。例如，如果 URL 以 `www.test123.com/electronics?campaign=123` 形式传递促销活动 ID，则可以创建一个特征规则以从 `h_referer` 变量中捕获相应数据，该特征规则将查找类似于 `h_referer = 'campaign=123'` 的标头。

<br> 

**实时区段人口计数和总区段人口计数之间有何差异？**

* **实时：**&#x200B;在设定的时间段内属于相应区段并且在您的资产上处于活动状态（即 [!DNL Audience Manager] 在特定时间段内必须记录到该用户的活动）的独特用户数。

* **总区段人口：**&#x200B;当前被分类到相应区段的所有用户总数。

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**我的一个区段只包含一个特征。但是，当我查看报表量度时，特征数量不匹配。为什么会出现这种情况？**

请参阅[区段生成器中的特征和区段人口数据](../features/segments/segment-builder-data.md)。

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**我接收了一个入站文件，“入站”接收情况显示成功处理的记录数较高，但报表显示的数量要低得多。为什么会出现这种情况？**

在后端，已载入的数据仅会附加到在 AAM 中仍处于活动状态的用户（用户在过去 120 天内必须开展过 [!DNL DCS] 活动）。因此，如果您为 [!DNL Audience Manager] 中已过期的用户载入数据，[!UICONTROL Inbound] 可能会告诉您已载入特定数量的用户记录，但是如果这些用户最近没有任何活动，则此数据在到达 [!UICONTROL User Profile Store] 时将被丢弃，且我们的报表会反映这一点。

<br> 

**对于跨设备载入的特征，为何特征独特计数要远远大于载入的总记录数？**

如果您载入跨设备数据提供商的无客户 ID 键的文件，则 Audience Manager 将执行查找以获取与每个已载入的客户 ID 相关联的所有设备 ID。Audience Manager 随后会将载入的特征分配给与客户 ID 关联的设备 ID。

例如，假定您已载入 100 条记录。对于每个客户 ID，AAM 一般都关联了三个设备 ID。因此，已载入的特征会被分配给 300 个设备 ID。

单个跨设备客户 ID 可以与多个设备 ID 相关联的原因有两点：

* 用户正从多个计算机/浏览器登录同一跨设备帐户。
* 用户正在清除其 Cookie。注意：如果用户在 120 天内一直未活动，则将删除“已被丢弃”的 Cookie。

<br> 

**对于已载入的特征，[!UICONTROL Total Trait Realizations] 为何总是 0？**

[!UICONTROL Total Trait Realizations] 与页面加载次数相对应。[!UICONTROL Total Trait Realizations] 提供特定特征实时触发的次数。此数值的计算范围仅限于基于规则的特征。对于已载入的特征，[!UICONTROL Total Trait Realizations] 始终显示为 0。

<br> 

**我创建了一个特征，但 [!UICONTROL Trait Graph] 显示的 [!UICONTROL Unique Trait Realizations] 数大于 [!UICONTROL Total Trait Population]。这种情况正常吗？**

您之所以会看到这种情况，是因为 [!UICONTROL Unique Trait Realizations] 属于实时量度，而为计算 [!UICONTROL Total Trait Population] 而执行的报告作业并不是实时的。因此，[!UICONTROL Total Trait Population] 应该会有几天大于 [!UICONTROL Unique Trait Realizations]。
