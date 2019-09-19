---
description: 常见定位相关问题和问题。
seo-description: 常见定位相关问题和问题。
seo-title: 定位常见问题解答
solution: Audience Manager
title: 定位常见问题解答
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# 定位常见问题解答{#targeting-faq}

常见定位相关问题和问题。

<br> 

<!-- 

faq_targeting.xml

 -->

**在哪里可以找到Audience manager支持的第三方数据提供商的完整列表？**

有关支 [持的第三方数据提供商的完整列表，请参阅Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) ( [!DNL Audience Manager] https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html)。

<br> 

**要瞄准在我的网站上从未见过使用第三方数据的用户，我是否应在Audience manager或DSP中使用第三方数据？**

答案取决于你的目标。 例如，如果您的营销活动设计为使用第三方数据查找新客户，则直接使用DSP。 请记住，Audience manager仅在我们看到该用户时才会与第三方数据提供者同步数据。 如果我们从未见过用户，则系统将没有该网站访客的任何信息。 对于仅希望使用第三方数据定位从未访问过您任何属性的用户的营销活动，请通过DSP创建这些细分。

<br> 

**我可以向个人营销吗？**

Audience manager允许您根据共享属性或特征汇总用户并向他们进行营销。 但是，为了遵守行业法规，客 [!DNL Audience Manager] 户不得将个人识别信息(PII)发送到我们的系统。 因此，您无法使用电子邮件地址、个人姓名、实际地址等。 （针对定位）。

<br> 

**如何安全地重定位数据？**

我们建议您使用服务器到服务器连接与首选重定向平台交换数据。 Audience manager通过服务器到服务器连接与大多数主要DSP交换数据。 服务器到服务器的数据传输有助于防止其他行为者拦截数据并再销售受众信息。

<br> 

**Audience Manager唯一用户ID(UUID)是否通过ID直接在页面上同步而绑定到广告服务器的唯一用户ID?**

不会。站点内发布者或服务器在页面上不会进行ID同步。 Audience Manager UUID将插入广告服 `u=` 务器日志文件的字段。 当区段传入进行定位时，会发生这种情况。 DIL代码模块执行此功能。 这是同一机制，它允许我们将服务器的用户ID映射到Audience manager用户，以便进行细分性能报告。 但是，如果站点上存在广告服务器，则我们会直接在页面上同步ID。

<br> 

**Audience manager是否将从不同设备登录的用户计算为一个唯一用户或不同的唯一用户？**

[Declared ID Targeting帮助](../features/declared-ids.md#declared-id-targeting) Audience Manager使用单个唯一标识符跨多个设备识别访客。 但是，从定位或目标角度来看，这仍然是2个（或更多）用户，因为DSP无法协调这些多个ID。

<br> 

**Audience manager能否通过显示和移动设备识别用户。**

能。请参阅 [声明的ID定位](../features/declared-ids.md#declared-id-targeting)。

<br> 

**我是否可以使用在线收集的数据对用户进行评分并根据此模型得分重新定位他们？**

能。Audience manager可以提供数据文件来帮助您对用户评分，但您必须与其他供应商或软件合作来分析和排名这些信息。 以键值对的形式将此数据发送到Audience Manager。 我们可以将这些信息附加到现有用户配置文件中。 请联系您的合作伙伴解决方案代表来查看此过程。

<br> 

**给定的1 - 2个月期间的Cookie删除率是多少？**

Cookie删除很难衡量。 大多数Cookie删除来自经常删除Cookie的少数访客。 但是，大多数浏览器Cookie至少在30天内保持稳定，即使某些浏览器Cookie的寿命有限。 一些研究表明，超过30天的上漏斗定位将有效消除30天内7%的浏览器目标受众。 如您所知，为特定创意消息进行30天的营销活动是行业中的标准操作。 从我们所看到的情况来看，7%的降幅是准确的。

Cookie删除对访问范围和频率计算有不利影响。 因此，在尝试了解展示广告营销活动规划的消费者趋势的真实性质时，我们强调行为数据的价值。 我们的客户可以利用Audience manager细分重叠报告、最佳印象频率报告和特定日期范围内的独特用户趋势，更科学地规划营销活动以及运行营销活动的最佳日期范围。

<br> 

**Audience Manager Cookies的到期窗口是什么？**

通过用户界面可确定Cookie的过期时间间隔。 您可以将cookie设置为在 *n天* 或永不过期。

<br> 

**在活动呼叫中实施营销活动创意是否花费我们更多？**

看情况。 成本基于独特用户。 如果营销活动产生净新用户，那么是的，则成本会更高。 如果您的营销活动到达我们已经收集数据的地方，则无需支付额外费用。 如果您的营销活动在重叠程度较大的相关网站上运行，则我们看到的新的独特用户将需要额外付费。

<br> 

**Audience manager仅显示[!UICONTROL Addressable Audiences]目标的指标和匹配[!UICONTROL Server-to-Server]率。 您能否解释为什么我们看不到Cookie和URL目标的这些数字？**

这归结于ID同步。 对于目 [!UICONTROL Server-to-Server] 标，我们离线传输数据（实时传输或批量传输），并且我们需要发送目标合作伙伴了解的ID，以便他们将其映射回浏览器。 区段可寻址编号是总区段总量的子集。

对于Cookie和URL目标，用户已在浏览器上，所发送的只 [!DNL Audience Manager] 是用户限定的区段。 目标合作伙伴只需选取区段映射并处理该信息即可。 因此，请考虑Cookie和URL目标的匹配率始终为100%。
