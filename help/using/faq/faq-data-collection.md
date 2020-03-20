---
description: 常见数据收集和集成问题和问题。
seo-description: 常见数据收集和集成问题和问题。
seo-title: 数据收集和产品集成常见问题解答
solution: Audience Manager
title: 数据收集和产品集成常见问题解答
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: d221890d2a80cd557a6968d3382ee8842fea9aef

---


# 数据收集和产品集成常见问题解答{#data-collection-and-product-integration-faq}

常见数据收集和集成问题和问题。

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**如何在日志文件导出中区分[!UICONTROL DCS]入站[!UICONTROL DCS]流量和流量？**

通过载入的 [!UICONTROL Inbound] 特征填充 [!UICONTROL Inbound] 方式与填充方式相同 [!UICONTROL DCS]。 有几种不同的方法可以判断流量来自 [!UICONTROL Inbound]:

* 远程IP将设置为68.67.173.18
* 域ID将设置为5325
* 区域将设置为0

<br> 

**能否提供dpm.demdex.net的IP地址列表？**

不幸的是，我们不能。 这些IP会按地理区域动态分配到 [!DNL Amazon Web Services]。 因此，不 [!DNL Audience Manager] 控制可分配给此地址的IP的范围。

<br> 

**能否为我提供入站和出站sFTP服务器的白名单中的IP地址？**

是的，请参见下面的内容。

| 项目 | 地址 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**对于[!UICONTROL DIL]/数据集成，有哪些代码放置和页面加[!DNL Analytics]载要求？**

要将数 [!DNL Analytics] 据导入 [!DNL Audience Manager]，在模块之后，但在功能之 [!UICONTROL DIL] 前，加 `s_code` 载 *(Load)*`s.t()` 。 例如，按照以下顺序放置代码或确保其加载：

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] 模块

3. [!DNL Analytics] `s.t()` 函数

作为最佳实践，请设置您 [!DNL Audience Manager]-与 [!DNL Analytics] 以下两种方法之一的集成：

* 直接 [!UICONTROL DIL] 放入 `s_code`。

* 服务 [!UICONTROL DIL] 和 `s_code` 通过 [!DNL Adobe Experience Platform Launch] 或 [!DNL Adobe DTM]。

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**为什么事件调[!DNL Analytics]用中缺少我的[!DNL Audience Manager]变量？**

这种情况通常发生在：

* 您可以通 [!UICONTROL DIL] 过标签管理系统来提供，该系统将标签与页面上的其他代码元素异步加载。
* 函数 `s.t()` 在之前加载 [!UICONTROL DIL]。

<br> 

**哪些版本[!DNL Analytics]可以使用[!UICONTROL DIL]?**

必须使用 [!DNL Analytics] 版本20.2（或更高版本）和 [!DNL Adobe AppMeasurement AS] 库版本3.5.2（或更高版本）才能使用 [!UICONTROL DIL]。 如果您不知道自己的版 [!DNL Analytics] 本或 [!DNL AppMeasurement] 版本，请检查 [!DNL Analytics] 从页面发出的调用。 版本信息如下：

此客户使 [!DNL Analytics] 用版本24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

此客户使 [!DNL AppMeasurement] 用版本3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**如果我不是客户，是否可以收集页面数[!DNL Analytics]据？**

能。该 [!UICONTROL DIL] 模块可帮助您收集页面数据，即使您不使用 [!DNL Analytics]。 正确设置后，可 [!UICONTROL DIL] 以从以下位置捕获数据：

* Meta标签
* URL和URL标题
* 搜索引擎类型
* 关键字

此外，客户端还可以部署一个简单的现场对象，并用要收集数据的键值对 [!UICONTROL DIL] 填充它。 这样，您无需任何更新即可在站点上添加和删除特定受众数据 [!DNL Audience Management] 点。 与您的合作伙伴解决方案代表合作以正确设置此设置，并确保 [!DNL DIL] 模块正确引用页面对象。

<br> 

**能否[!UICONTROL DIL]从中收集数据[!DNL Google Analytics]?**

能。[!UICONTROL DIL] 可以收集 [!DNL Google Analytics] 一些(GA)元素并将该数据传递给 [!DNL Audience Manager]。 请参阅：

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**能否从中获得原始数[!DNL Audience Manager]据，其粒度如何？**

是的，可 [!DNL Audience Manager] 以为您提供为我们在您的库存中看到的用户收集的数据。 这包括：

* 由 [!DNL Audience Manager]
* 特征和区段ID
* 未使用的信号
* 时间戳
* 页面URL

<br> 

**我希望通过DFP收集一个站点上的数据并定位其他站点上的用户。 如果我不想从该位置收集数据，是否需要在另一个属性上部署代码？**

不会。如果不需要在第二个站点上收集数据，则无需在那里部署DIL。 只要您通过DFP访问第二个站点上的库存，您就可以通过DFP使用从初始站点和目标站点收集的数据。

<br> 

**什么是最佳的第三方数据提供商？**

每个提供商都会为表格带来一些独一无二的内容，因此答案取决于您所寻找的内容。 我们可以启用重叠报告（免费）以帮助您了解哪家提供商最适合您。

<br> 

**如何设[!DNL Audience Manager]置cookies并将变量传递给DFP?**

[!DNL Audience Manager] 设置2个cookie:一个将段变量发送到DFP ad标签，另一个将设置我们的唯一用户ID(UUID),DFP也读取该UUID。 将UUID添加到广告标记意味着我们可以执行用户级报告和受众发现。

<br> 

**我们能否发送有关用户到达的转换漏斗中点的DSP信息？**

能。我们可以发送漏斗数据，但DSP必须具备相应的技术能力才能使用。 DSP必须确认他们可以处理多个段。 如果客户无法转化，我们可能需要创建特定细分，以便根据其转化进度将用户从其他细分中拉出（例如，已完成步骤1和2，但不是步骤3）。 您可能希望将此信息发送到DSP，以便他们能够重新定位用户、将其定向到特定登录页面或显示特定创意。

<br> 

**如何确认通过FTP发送的数据已被收集[!DNL Audience Manager]?**

扩展名从更改为时，已选取一个 `.sync` 文件 `.processed`。 发生这种情况时，文件将位于摄取队列中。 此外，您的客户经理还可以确认文件何时上传。

<br> 

**我要测试[DCS API的功能](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。 我发送的活动调用与下面显示的一样。 这些调用包[含Declared ID](../features/declared-ids.md)（声明的ID）和信号，这些ID和信号应该可以实现我已设置的某些特征和区段。 我是否可以使用[!UICONTROL General Reports]和[!UICONTROL Trend Reports]验证特征和区段群体是否在增加？**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

不，不要依赖这 [!UICONTROL General Reports] 个 [!UICONTROL Trend Reports] 案例。

这些报告根据生成报告时我们在后端看到的未验证配置文件记录(UUID)来计算人口。

在对的第一次调 [!UICONTROL DCS]用中，声明的ID *不链接到任何UUID* (即，客户端上不 [存在demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) )。 将 [!UICONTROL DCS] 随机生成UUID并设置 [!DNL demdex] cookie，并在响应调用中传递它，但不会将UUID传输到后端。

>[!NOTE]
>
>生成的UUID仅在设置了cookie的设备触发进一步活动后，才会在我们的后端数据存储中实现。

因此，报告不会反映由呼叫中声明的ID触发的事件。 我们建议您在对的事件测试调用中使用UUID、ECID（以前称为MID）或移动设备ID [!UICONTROL DCS]。 然后，您可以在和中验证特征和 [!UICONTROL General Reports] 段实现 [!UICONTROL Trend Reports]。

另请参阅Audience [Manager ID的索引](../reference/ids-in-aam.md)。

<br> 

**用户配置文件跨区域同步需要多长[时间](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

用户配置文件跨区域同步通常需要24小时。 但是，在极少的情况下，该过程最多可能需要48小时。
