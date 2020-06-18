---
description: 常见数据收集和集成问题。
seo-description: 常见数据收集和集成问题。
seo-title: 数据收集和产品集成常见问题解答
solution: Audience Manager
title: 数据收集和产品集成常见问题解答
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---


# 数据收集和产品集成常见问题解答{#data-collection-and-product-integration-faq}

常见数据收集和集成问题。

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**如何在日志文件导出中区分[!DNL DCS]入站流[!DNL DCS]量和流量？**

通过载入的 [!UICONTROL Inbound] 特征填充 [!UICONTROL Inbound] 方式与填充方式相同 [!DNL DCS]。 有几种不同的方法可以判断流量来自 [!UICONTROL Inbound]:

* 远程IP将设置为68.67.173.18
* 域ID将设置为5325
* 区域将设置为0

<br> 

**能否向我提供一列表IP地址，我可以将其添加到dpm.demdex.net的允许列表？**

不幸的是，我们不能。 这些IP是通过按地理区域动态分配的 [!DNL Amazon Web Services]。 因此，不 [!DNL Audience Manager] 控制可分配给此地址的IP的范围。

<br> 

**能否向我提供可添加到入站和出站sFTP服务器允许列表的IP地址？**

是，请参见下文。

| 项目 | 地址 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**/数据集成的代码放置和页面加载[!UICONTROL DIL]要求[!DNL Analytics]有哪些？**

要将数 [!DNL Analytics] 据导入 [!DNL Audience Manager]，在模块之 [!UICONTROL DIL] 后加载，但 `s_code` 在函数之 *前加*`s.t()` 载。 例如，按以下顺序放置代码或确保它加载：

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] 模块

3. [!DNL Analytics] `s.t()` 函数

作为最佳实践，请设置您 [!DNL Audience Manager]与以 [!DNL Analytics] 下两种方法之一的集成：

* 直 [!UICONTROL DIL] 接放入 `s_code`。

* 服 [!UICONTROL DIL] 务和 `s_code` 通过 [!DNL Adobe Experience Platform Launch] 或 [!DNL Adobe DTM]。

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**为什么事件[!DNL Analytics]调用中缺少[!DNL Audience Manager]我的变量？**

这通常发生在：

* 您可以通 [!UICONTROL DIL] 过标签管理系统提供，该系统将标签与页面上的其他代码元素异步加载。
* 函数 `s.t()` 在之前加载 [!UICONTROL DIL]。

<br> 

**哪些版本[!DNL Analytics]可以使用[!UICONTROL DIL]?**

必须使用 [!DNL Analytics] 版本20.2（或更高版本）和 [!DNL Adobe AppMeasurement AS] 库版本3.5.2（或更高版本）才能使用 [!UICONTROL DIL]。 如果您不知道您的版 [!DNL Analytics] 本或 [!DNL AppMeasurement] 版本，请检查 [!DNL Analytics] 从页面进行的调用。 版本信息如下所示：

此客户使 [!DNL Analytics] 用版本24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

此客户使 [!DNL AppMeasurement] 用版本3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**如果我不是客户，是否可以收集页面[!DNL Analytics]数据？**

能。该 [!UICONTROL DIL] 模块可帮助您收集页面数据，即使您不在使用 [!DNL Analytics]。 正确设置后，可 [!UICONTROL DIL] 以从以下位置捕获数据：

* 元标记
* URL和URL头
* 搜索引擎类型
* 关键字

此外，客户可以部署一个简单的现场对象，并用要收集数据的键 [!UICONTROL DIL] 值对填充它。 这样，您无需进行任何更新即可在网站上添加和删除特定受众 [!DNL Audience Management] 数据点。 请与合作伙伴解决方案代表合作以正确设置此设置，并确保 [!DNL DIL] 模块正确引用页面对象。

<br> 

**能否[!UICONTROL DIL]从中收集数[!DNL Google Analytics]据？**

能。[!UICONTROL DIL] 可以收集 [!DNL Google Analytics] 一些(GA)元素并将该数据传递给 [!DNL Audience Manager]。 请参阅：

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**能否从中获取原始数[!DNL Audience Manager]据，其粒度如何？**

是的， [!DNL Audience Manager] 可以为您提供为我们在您的清单上看到的用户收集的数据。 这包括：

* 由 [!DNL Audience Manager]
* 特征和区段ID
* 未使用的信号
* 时间戳
* 页面URL

<br> 

**我希望通过DFP在一个站点上收集数据，并通过其他站点上的目标用户收集数据。 如果我不想从另一个位置收集数据，是否需要在另一个属性上部署代码？**

不会。如果不需要在第二个站点上收集数据，则无需在那里部署DIL。 只要您通过DFP访问第二个站点的库存，您就可以通过DFP使用从初始站点和目标收集的数据。

<br> 

**什么是最好的第三方数据提供商？**

每个提供商都会为表带来一些独一无二的内容，因此答案取决于您所寻找的内容。 我们可以启用重叠报告（免费）来帮助您了解哪家提供商最适合您。

<br> 

**如何设[!DNL Audience Manager]置cookies并将变量传递给DFP?**

[!DNL Audience Manager] 设置2个cookie: 一个向DFP ad标签发送段变量，另一个设置我们的唯一用户ID(UUID),DFP也读取该UUID。 将UUID添加到广告标记意味着我们可以执行用户级报告和受众发现。

<br> 

**能否发送用户所到达的转换漏斗中点的DSP信息？**

能。我们可以发送漏斗数据，但DSP必须具备技术能力才能使用。 DSP必须确认他们可以处理多个段。 如果客户无法进行转换，我们可能需要创建特定细分，以便根据客户的转换进度（例如，已完成步骤1和步骤2，但不是步骤3）将用户从其他细分中拉出。 您可能希望将此信息发送到DSP，以便他们能够重新定位用户、将其定向到特定登陆页或显示特定创意。

<br> 

**如何确认通过FTP发送的数据已被提取[!DNL Audience Manager]?**

扩展名从更改为时，已拾取文 `.sync` 件 `.processed`。 发生这种情况时，文件位于摄取队列中。 此外，您的客户经理还可以确认文件何时上传。

<br> 

**我想测试DCS API的[功能](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)。 我正在发送事件呼叫，如下所示。 这些调用[包含Declared](../features/declared-ids.md)ID和信号，它们应该可以实现我已设置的某些特征和区段。 我是否可以使[!UICONTROL General Reports]用和[!UICONTROL Trend Reports]验证特征和区段群体是否在增加？**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

不，不要依赖这 [!UICONTROL General Reports] 个 [!UICONTROL Trend Reports] 案例。

报表根据生成报表时在后端看到的未验证用户档案记录(UUID)计算总量。

在对的第一次调 [!DNL DCS]用中，声 *明的ID不链* 接到 [任何UUID(即，客户端](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) 上不存在demdex cookie)。 将随 [!DNL DCS] 机生成一个UUID并设置一个 [!DNL demdex] cookie并在响应调用中传递它，但它不会将UUID传输到后端。

>[!NOTE]
>
>只有在设置了cookie的设备触发进一步活动后，才会在后端存储中实现生成的UUID。

因此，报告不会反映您呼叫中声明的ID触发的事件。 我们建议您在对的事件测试调用中使用UUID、ECID（以前称为MID）或移动设备ID [!DNL DCS]。 然后，您可以在和中验证特征 [!UICONTROL General Reports] 和段实现 [!UICONTROL Trend Reports]。

另请参阅 [Audience ManagerID索引](../reference/ids-in-aam.md)。

<br> 

**用户用户档案跨区域同步需要多长[时间](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

用户用户档案通常需要24小时才能跨区域同步。 但是，在极少情况下，该过程可能需要48小时。
