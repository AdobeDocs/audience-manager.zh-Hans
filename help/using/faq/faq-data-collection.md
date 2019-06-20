---
description: 常见数据收集和集成问题和问题。
seo-description: 常见数据收集和集成问题和问题。
seo-title: 数据收集和产品集成常见问题解答
solution: Audience Manager
title: 数据收集和产品集成常见问题解答
uuid: fa8e79f4-99cb-41fd-8a85-d4 f92 d03 c7 a5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

常见数据收集和集成问题和问题。

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**如何将入站流量与日志文件导出中[!UICONTROL DCS][!UICONTROL DCS]的流量区分开来？**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* 远程IP将设置为68.67.173.18
* domainID将设置为5325
* 区域将设置为0

<br> 

**您可以为我提供一个IP地址列表，我可以为dpm. demdex. net提供白名单吗？**

不幸的是，我们无法做到。These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**您是否可以为我提供用于入站和出站FTP服务器的IP地址？**

是的，请参阅下面的内容。

| 项目 | 地址 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**什么是[!UICONTROL DIL]/[!DNL Analytics]数据集成的代码放置和页面加载要求？**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. 例如，放置代码或确保它加载，按顺序：

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] module

3. [!DNL Analytics]`s.t()` function

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**为什么活动调用中缺少我[!DNL Analytics][!DNL Audience Manager]的变量？**

通常情况下，发生以下情况时发生这种情况：

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* `s.t()` 函数之前加载 [!UICONTROL DIL]。

<br> 

**哪些版本[!DNL Analytics][!UICONTROL DIL]的工作？**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. If you don&#39;t know your [!DNL Analytics] or [!DNL AppMeasurement] version, check the [!DNL Analytics] call that gets made from the page. 以下版本信息：

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**如果不[!DNL Analytics]是客户，能否收集页面数据？**

能。[!UICONTROL DIL] 模块可帮助您收集页面数据，即使您未使用 [!DNL Analytics]也是如此。When set up properly, [!UICONTROL DIL] can capture data from and about:

* meta标记
* URL和URL标题
* 搜索引擎类型
* 关键字

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**是否可以[!UICONTROL DIL]收集数据[!DNL Google Analytics]？**

能。[!UICONTROL DIL] 可以收集一些 [!DNL Google Analytics] (GA)元素并将该数据传递 [!DNL Audience Manager]给。请参阅：

* [GA. SubmitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**我是否可以从原始[!DNL Audience Manager]数据获取原始数据？**

Yes, [!DNL Audience Manager] can provide you with data collected for users we&#39;ve seen on your inventory. 这包括：

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* 特征和区段ID
* 未使用的信号
* 时间戳
* 页面URL

<br> 

**我希望在一个不同站点上通过DFP收集一个站点和目标用户的数据。Do I need to deploy code on the other property if I don&#39;t want to collect data from that location?**

不会。如果第二个站点上的数据收集不是必需的，您无需在那里部署DIL。只要您通过DFP访问第二个站点上的库存，就可以通过DFP将数据收集从初始站点和目标使用。

<br> 

**什么是最佳第三方数据提供商？**

每个提供商都会引入表格特有的内容，因此答案取决于您需要的内容。我们可以启用重叠报告(免费)来帮助您了解哪个提供商最适合您。

<br> 

**[!DNL Audience Manager]如何设置cookie并将变量传递到DFP？**

[!DNL Audience Manager] 设置cookies：其中一个将区段变量发送到DFP广告标签，另一个会设置我们唯一的用户ID(UUID)，该ID也由DFP读取。将UUID添加到广告标签意味着我们可以进行用户级报告和受众发现。

<br> 

**我们能否向用户发送有关转化漏斗中的积分的DSP信息？**

能。我们可以发送漏斗数据，但DSP必须具有技术能力才能使用。DSP必须确认他们可以处理多个区段。如果不能，我们可能需要创建特定细分，以根据客户转化进度(例如完成步骤和步骤2，但不是步骤3)吸引用户。您可能希望将此信息发送到DSP，以便重新定位用户、将其定向到特定登陆页面或显示特定创意。

<br> 

**我如何确认通过FTP发送的数据已被选取[!DNL Audience Manager]？**

A file has been picked up when the extension changes from `.sync` to `.processed`. 当发生这种情况时，文件位于摄取队列中。此外，您的客户经理可以在上传文件时进行确认。

<br> 

**我希望测试[DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)的功能。我发送的活动调用如下所示。The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

这些报告会根据生成报表时在后端看到的未经过身份验证的配置文件记录(UUID)计算人群。

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>在设置Cookie的设备触发进一步活动后，生成的UUID只会在我们的后端数据存储中进行实例化。

因此，报告将不反映调用中被声明ID触发的事件。We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**用户配置文件需要多长时间才能跨[地区同步](../api/dcs-intro/dcs-api-reference/dcs-regions.md)？**

用户配置文件通常需要长达24小时才能跨地区同步。但是，在少数情况下，该过程最多可能需要48小时。
