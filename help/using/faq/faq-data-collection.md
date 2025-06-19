---
description: 有关数据收集和集成的常见问题。
seo-description: Common data collection and integration questions and issues.
seo-title: Data Collection and Product Integration FAQ
solution: Audience Manager
title: 数据收集和产品集成常见问题解答
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP；SFTP地址；STFP IP地址；FTP地址
feature: Administration
exl-id: 2951ab0c-6f1c-4126-b83e-ce4a33c0d4ab
source-git-commit: 974f45268d50c486c872137a3aa6d8fc7f691024
workflow-type: tm+mt
source-wordcount: '1255'
ht-degree: 74%

---


# 数据收集和产品集成常见问题解答{#data-collection-and-product-integration-faq}

有关数据收集和集成的常见问题。

<br> 

**如何在 [!DNL DCS] 日志文件导出中区分入站流量和 [!DNL DCS] 流量？**

对于通过 [!UICONTROL Inbound] 载入的特征，[!UICONTROL Inbound] 填充方式与 [!DNL DCS] 填充方式相同。可以通过以下几种方法判断流量来自 [!UICONTROL Inbound]：

* 远程IP将设置为68.67.173.18
* 域 ID 将设置为 5325
* 区域将设置为 0

<br> 

**能否为我提供可添加到dpm.demdex.net允许列表的IP地址列表？**

抱歉，我们无法为您提供这样的列表。这些 IP 是通过 [!DNL Amazon Web Services] 按地域动态分配的。因此，[!DNL Audience Manager] 无法控制可分配给此地址的 IP 范围。

 

**能否为我提供可添加到入站和出站SFTP服务器的允许列表中的IP地址？**

可以，请参见下文。

| 服务器 | IP 地址 |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119； 3.233.68.222 |
| ftp-out-gtw.demdex.com | 23.22.232.252； 18.211.109.184 |

 

以下SFTP服务器已被弃用。 不会使用这些服务器配置任何新帐户。

| 服务器 | IP 地址 |
|---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**如何将我的Audience Manager实例配置为使用新的SFTP服务器？**

请联系您的[!DNL Audience Manager]顾问或客户关怀团队，他们将配置您的新SFTP帐户。

 

**新SFTP服务器支持哪些身份验证方法？**

新的SFTP服务器（`ftp-in-gtw`和`ftp-out-gtw`）支持[!DNL OpenSSH Key-Based Authentication]。 我们可以为您生成[!DNL SSH]密钥，或者您可以向我们提供自己的公钥。

 

**对于 [!UICONTROL DIL]/[!DNL Analytics] 数据集成，有哪些代码放置和页面加载要求？**

要将 [!DNL Analytics] 数据导入 [!DNL Audience Manager]，请在加载 `s_code` 模块之后但在加载 `s.t()` 函数&#x200B;*之前*&#x200B;加载 [!UICONTROL DIL]。例如，按以下顺序放置代码，或确保代码按以下顺序加载：

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] 模块

3. [!DNL Analytics] `s.t()` 函数

最好从以下两种方法选择一种方法来设置 [!DNL Audience Manager] 与 [!DNL Analytics] 集成：

* 将 [!UICONTROL DIL] 直接放置到 `s_code` 中。

* 通过[!DNL Adobe Experience Platform Tags]为[!UICONTROL DIL]和`s_code`提供服务。

请参阅[数据集成库 (DIL) API](../dil/dil-overview.md)。

 

**为何 [!DNL Audience Manager] 事件调用中会缺少 [!DNL Analytics] 变量？**

此问题通常发生在以下情况中：

* 您通过标记管理系统为 [!UICONTROL DIL] 提供服务，但标记管理系统异步加载此模块和页面上的其他代码元素。
* `s.t()` 函数在 [!UICONTROL DIL] 之前加载。

 

**哪些版本的 [!DNL Analytics] 可以与 [!UICONTROL DIL] 结合使用？**

要结合使用 [!UICONTROL DIL]，必须使用 [!DNL Analytics] 版本 20.2（或更高版本）以及 [!DNL Adobe AppMeasurement AS] 库版本 3.5.2（或更高版本）。如果您不知道 [!DNL Analytics] 或 [!DNL AppMeasurement] 的版本，请检查从页面中进行的 [!DNL Analytics] 调用。版本信息如下所示：

此客户使用的是 [!DNL Analytics] 版本 24.4：

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

此客户使用的是 [!DNL AppMeasurement] 版本 3.5.2：

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**如果我不是 [!DNL Analytics] 用户，是否还能够收集页面数据？**

能。即使您未在使用 [!DNL Analytics]，[!UICONTROL DIL] 模块也可以帮助您收集页面数据。正确设置后，[!UICONTROL DIL] 便可从以下项目捕获相关数据：

* 元标记
* URL 和 URL 标头
* 搜索引擎类型
* 关键字

此外，客户可以在网站上部署一个简单的对象，并在该对象中填充希望 [!UICONTROL DIL] 对其收集数据的键值对。如此一来，您无需进行任何 [!DNL Audience Management] 更新，即可在网站上添加和删除特定受众数据点。请与合作伙伴解决方案代表合作以正确设置对象，并确保 [!DNL DIL] 模块正确引用页面对象。

<br> 

**[!UICONTROL DIL] 能否从 [!DNL Google Analytics] 中收集数据？**

能。[!UICONTROL DIL] 可以收集一些 [!DNL Google Analytics] (GA) 元素并将收集到的数据传递给 [!DNL Audience Manager]。请参阅：

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**我能否从 [!DNL Audience Manager] 中获取原始数据？数据粒度是多少？**

能，[!DNL Audience Manager] 可以为您提供收集到的有关您清单范围内的用户的数据。这包括：

* 由 [!DNL Audience Manager] 分配的独特用户 ID (UUID)
* 特征 ID 和区段 ID
* 未使用的信号
* 时间戳
* 页面 URL

<br> 

**我想在一个网站上收集数据，并通过[!DNL Google Ad Manager]在另一个网站上定位用户。 如果我不想从其他资产中收集数据，是否需要在该位置部署代码？**

不需要。如果不需要在另一个网站上收集数据，则无需在该网站上部署 DIL。只要您有权通过[!DNL Google Ad Manager]访问第二个网站上的清单，就可以通过[!DNL Google Ad Manager]使用从初始网站和目标收集的数据。

<br> 

**最佳的第三方数据提供商是哪个？**

每个提供商都有其独特的特点，因此要根据您的需求确定最适合的提供商。我们可以通过启用重叠报表（免费）来帮助您了解哪个提供商最适合您。

<br> 

**[!DNL Audience Manager]如何设置Cookie并将变量传递给[!DNL Google Ad Manager]？**

[!DNL Audience Manager]设置2个Cookie：一个向[!DNL Google Ad Manager]广告标记发送区段变量，另一个设置我们的独特用户ID (UUID)，该ID也由[!DNL Google Ad Manager]读取。 将 UUID 添加到广告标记意味着我们可以执行用户级报表和受众发现操作。

<br> 

**我们能否向 DSP 发送有关转化漏斗中用户所实现的点数信息？**

能。我们可以发送漏斗数据，但 DSP 必须具备一定的技术能力才能使用该数据。DSP 必须确认可以处理多个区段。如果 DSP 无法处理多个区段，我们可能需要创建特定区段，以便根据客户的转化进度（例如，已完成步骤 1 和步骤 2，但未完成步骤 3）将用户从其他区段中删除。您可能希望将此信息发送到 DSP，以便 DSP 能够重新锁定用户、将用户定向到特定登录页面或向用户显示特定创意内容。

<br> 

**如何确认通过 FTP 发送的数据已被 [!DNL Audience Manager] 接收？**

当扩展名从 `.sync` 更改为 `.processed` 时，即表示文件已被接收。接收后，文件将位于导入队列中。此外，您的客户经理也可以确认文件是否已上传。

<br> 

**我想要测试 [DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md) 的功能。我正在发送类似于下面所示的事件调用。这些调用包含[声明的 ID](../features/declared-ids.md) 和信号，它们应该可以实现我已设置的某些特征和区段。我能否使用 [!UICONTROL General Reports] 和 [!UICONTROL Trend Reports] 来验证特征和区段人口是否有所增加？**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

不能，在这种情况下，请勿使用 [!UICONTROL General Reports] 和 [!UICONTROL Trend Reports]。

这两个报表会根据生成时在后端看到的未验证用户配置文件记录 (UUID) 来计算人口。

在第一次调用 [!DNL DCS] 时，声明的 ID *不会*&#x200B;关联到任何 UUID（这表示客户端上不存在任何 [demdex cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html))。[!DNL DCS] 将随机生成一个 UUID 并设置一个 [!DNL demdex] Cookie，然后在响应调用中传递该 UUID，但不会将该 UUID 传输到后端。

>[!NOTE]
>
>只有在设置了 Cookie 的设备触发后续活动时，生成的 UUID 才会在后端数据存储中实现。

因此，这两个报表不会反映由声明的 ID 在调用中触发的事件。在对 [!DNL DCS] 发起的事件测试调用中，我们建议您使用 UUID、ECID（以前称为 MID）或移动设备 ID。然后，您便可以在 [!UICONTROL General Reports] 和 [!UICONTROL Trend Reports] 中确认特征和区段的实现情况。

另请参阅 [Audience Manager ID 索引](../reference/ids-in-aam.md)。

<br> 

**在各[区域](../api/dcs-intro/dcs-api-reference/dcs-regions.md)之间同步用户配置文件需要多长时间？**

要在各区域之间同步用户配置文件，通常最多需要 24 小时。但是，在极少数情况下，该过程可能长达 48 小时。

 

**非活动的Amazon S3用户访问密钥发生了什么情况？**

Adobe为Audience Manager客户提供了[!DNL Amazon S3]存储段的访问密钥。 出于安全考虑，如果这些访问密钥在100天内未使用，则会自动禁用它们。

如果您的访问密钥被禁用，您可以联系客户支持以重新启用它们或请求新的访问密钥。

为了增强安全性，1000天未使用的访问密钥将与Amazon S3 IAM用户帐户一起永久删除。 如果您是旧客户，并且在此时间段后需要访问，请联系客户支持以重新创建您的帐户并接收新的访问密钥。
