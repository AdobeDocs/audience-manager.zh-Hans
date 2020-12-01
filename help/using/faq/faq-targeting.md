---
description: 常见定位相关问题。
seo-description: 常见定位相关问题。
seo-title: 定位常见问题解答
solution: Audience Manager
title: 定位常见问题解答
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
translation-type: tm+mt
source-git-commit: 27ce94084e35ffa770858027d12235ca9f1f8430
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 100%

---


# 定位常见问题解答{#targeting-faq}

常见定位相关问题。

<br> 

<!-- 

faq_targeting.xml

 -->

**在哪里可以找到 Audience Manager 支持的第三方数据提供商的完整列表？**

请参阅 [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html)，获得 [!DNL Audience Manager] 支持的第三方数据提供商的完整列表。

<br> 

**若要使用第三方数据定位从未在网站上出现过的用户，我应该使用 Audience Manager 中的第三方数据还是 DSP 中的第三方数据？**

答案取决于您的目标。例如，如果促销活动设计为使用第三方数据寻找新客户，则直接使用 DSP。请记住，只有当我们看到该用户时，Audience Manager 才会与第三方数据提供商同步数据。如果我们之前从未见过用户，则我们的系统将没有该网站访客的任何信息。对于仅希望使用第三方数据来定位从未访问过您的任何资产的用户的促销活动，请通过 DSP 创建这些区段。

<br> 

**我可以向个人进行营销吗？**

Audience Manager 允许您根据共享属性或特征汇总用户并向他们进行营销。但是，为了遵循行业法规，[!DNL Audience Manager] 客户不得将个人身份信息 (PII) 发送到我们的系统。因此，您无法使用电子邮件地址、个人姓名、物理地址等进行定位。

<br> 

**如何安全地保留重定位数据？**

我们建议您使用服务器到服务器连接与首选重定位平台交换数据。Audience Manager 可通过服务器到服务器连接与大多数主要 DSP 交换数据。服务器到服务器数据传输有助于防止其他行为者拦截您的数据并转售该受众信息。

<br> 

**能否通过直接在页面上同步 ID 将 Audience Manager 独特用户 ID (UUID) 绑定到广告服务器的独特用户 ID？**

不能。网站上的发布者或服务器的 ID 同步不在页面上进行。Audience Manager UUID 会插入到广告服务器日志文件的 `u=` 字段中。当传入区段以进行定位时，会发生这种情况。DIL 代码模块将执行此功能。这一机制使我们能够将服务器的用户 ID 映射到 Audience Manager 用户以报告区段性能。但是，如果网站上存在广告服务器，则我们会直接在页面上同步 ID。

<br> 

**Audience Manager 会将从不同设备登录的一位用户计作一个独特用户还是多个不同的独特用户？**

[声明的 ID 定位](../features/declared-ids.md#declared-id-targeting)可帮助 Audience Manager 使用单个唯一标识符识别跨多个设备的访客。但是，从定位或目标角度来看，这仍然是 2 个（或更多）用户，因为 DSP 无法协调这些 ID。

<br> 

**Audience Manager 能否识别显示设备用户和移动设备用户？**

能。请参阅[声明的 ID 定位](../features/declared-ids.md#declared-id-targeting)。

<br> 

**我能否使用在线收集的数据对用户进行评分，并根据此模型得分重新定位他们？**

能。Audience Manager 可以提供数据文件来帮助您对用户进行评分，但您必须与其他供应商合作或结合使用其他软件对该信息进行分析和排名。此数据将以键值对的形式发送到 Audience Manager。我们可以将此信息附加到现有用户配置文件中。请联系您的合作伙伴解决方案代表来了解此过程。

<br> 

**在给定 1-2 个月内，Cookie 删除率是多少？**

Cookie 删除率难以衡量。大多数 Cookie 删除操作由经常删除 Cookie 的少数访客执行。但是，大多数浏览器 Cookie 至少在 30 天内能够保持稳定，尽管有些浏览器 Cookie 的寿命可能有限。一些研究表明，超过 30 天的顶部漏斗定位将在 30 天内有效地消除 7% 的浏览器目标受众。如您所知，将给定创意消息的促销活动期限设为 30 天是业界的标准。从我们所看到的情况来看，7% 的降幅是准确的。

删除 Cookie 会对访问范围和频度计算产生不利影响。因此，在尝试了解展示促销活动规划的消费者趋势真实本质时，我们会强调行为数据的价值。我们的客户可以利用 Audience Manager 区段重叠报表、最佳展示次数频度报表和特定日期范围内的独特用户趋势，更科学地规划促销活动，更合理地设定运行促销活动的最佳日期范围。

<br> 

**Audience Manager Cookie 的过期期限是多长时间？**

您可以通过用户界面确定 Cookie 过期间隔。您可以设置 Cookie 在 *n* 天后过期或永不过期。

<br> 

**在事件调用中实施促销活动创意所花费的成本是否更高？**

视情况而定。成本取决于独特用户。如果促销活动产生了全新的用户，则成本会更高。如果您的促销活动在我们已经收集数据的网站上运行，则无需支付额外费用。如果您的促销活动在重叠程度很高的相关网站上运行，而我们又看到了新的独特用户，则需要支付额外费用。

<br> 

**Audience Manager 仅显示 [!UICONTROL Server-to-Server] 目标的 [!UICONTROL Addressable Audiences] 量度和匹配率。能否解释一下为什么我们看不到 Cookie 和 URL 目标的这些数据吗？**

原因在于 ID 同步。对于 [!UICONTROL Server-to-Server] 目标，我们会离线传输数据（实时传输或批量传输），并且我们需要发送目标合作伙伴了解的 ID，以便他们可以将其映射回浏览器。区段可寻址数是区段人口总数的子集。

对于 Cookie 和 URL 目标，用户已在浏览器上，且 [!DNL Audience Manager] 所发送的内容只是用户符合条件的区段。而目标合作伙伴只需选取区段映射并处理该信息即可。因此，可考虑将 Cookie 和 URL 目标的匹配率始终设为 100%。
