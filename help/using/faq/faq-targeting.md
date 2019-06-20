---
description: 常见定位相关问题和问题。
seo-description: 常见定位相关问题和问题。
seo-title: 定位常见问题解答
solution: Audience Manager
title: 定位常见问题解答
uuid: ee96ef71-b903-4953-afc4-8ec8 e48 bd49 e
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

常见定位相关问题和问题。

<br> 

<!-- 

faq_targeting.xml

 -->

**哪里可以找到Audience Manager支持的第三方数据提供商的完整列表？**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**要瞄准我在站点中从未见过第三方数据的用户，我应该在Audience Manager或DSP中使用第三方数据吗？**

答案取决于您的目标。例如，如果您的营销活动旨在使用第三方数据查找新客户，则直接使用DSP。请记住，只有当我们看到用户时，Audience Manager才会将数据与第三方数据提供商同步。如果我们以前从未见过某个用户，我们的系统将不会有该网站访客的任何信息。对于仅希望使用第三方数据定位从未访问过您的任何属性的用户的营销活动，请通过DSP创建这些区段。

<br> 

**我能否向个人营销？**

Audience Manager可让您整合用户并根据共享属性或特征对其进行营销。However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. 因此，您无法使用电子邮件地址、个人姓名、实际地址等。进行定位。

<br> 

**如何安全地重新定位数据？**

我们建议您使用服务器连接服务器连接，与首选重定向平台交换数据。Audience Manager通过服务器到服务器连接与大部分主要DSP交换数据。服务器到服务器数据传输有助于防止其他演员截取您的数据并重新销售该受众信息。

<br> 

**Audience Manager唯一用户ID(UUID)是否通过ID直接同步到页面上的广告服务器唯一用户ID？**

不会。不在站点发布者或服务器的页面上创建ID同步。The Audience Manager UUID is inserted into the `u=` field of the ad server log files. 这种情况发生在定向传入定位时。DIL代码模块执行此函数。这与允许我们将服务器的用户ID映射到Audience Manager用户以进行细分性能报告的机制相同。但是，如果站点上存在广告服务器，则我们将在页面上直接同步ID。

<br> 

**Audience Manager是否会将从不同设备登录的用户计为一个唯一用户或不同的独特用户？**

[Decled ID Targeting](../features/declared-ids.md#declared-id-targeting) 可帮助Audience Manager利用单个唯一标识符跨多个设备识别访客。但是，从定位或目标角度来看，这仍是个(或更多)用户，因为DSP无法协调这些多个ID。

<br> 

**Audience Manager可从显示屏和移动设备识别用户。**

能。See [Declared ID Targeting](../features/declared-ids.md#declared-id-targeting).

<br> 

**我是否可以为在线收集的数据得分，并根据此模型分数重新定位它们？**

能。Audience Manager可提供数据文件以帮助您得分用户，但您必须与其他供应商或软件合作以分析和排名此信息。以关键值对的形式将此数据发送到Audience Manager。我们可以收集此信息并将其附加到现有用户配置文件。要查看此过程，请与您的合作伙伴解决方案代表联系。

<br> 

**在给定的1-个月期限内，cookie删除率有哪些？**

无法评估cookie删除。大多数cookie删除来自几个经常删除cookies的访客。但是，大多数浏览器cookie在至少30天内保持稳定，即使某些浏览器可能具有有限的生命。某些研究建议，超过30天的高漏斗定位将有效消除七天内70%的浏览器目标受众。正如您所知，针对给定创意消息的30天营销活动是业界标准。从我们所看到的内容来看，7%的流失是准确的。

Cookie删除会对范围和频率计算产生不利影响。因此，在尝试了解展示营销活动规划的消费者趋势的真实本质时，我们会强调行为数据的价值。我们的客户可以利用Audience Manager细分报告、最优印象频率报告和特定日期范围内独特的用户趋势，以更科学地了解营销活动规划和运行活动的最优日期范围。

<br> 

**Audience Manager cookies的过期窗口是什么？**

用户界面允许您确定cookie到期间隔。You can set cookies to expire after *n* number of days or never.

<br> 

**在活动电话中实施营销活动创意会节省更多吗？**

它取决于。成本基于独特的用户。如果营销活动会产生净新用户，那么，这将节省更多。如果您的营销活动到达我们已经收集数据的地方，则无需支付额外费用。如果您的营销活动在存在明显重叠的相关站点上运行，则我们会为新的独特用户提供额外的成本。

<br> 

**Audience Manager仅显示[!UICONTROL Addressable Audiences][!UICONTROL Server-to-Server]目标的指标和匹配率。Can you explain why we don&#39;t see these figures for Cookie and URL destinations?**

它与ID同步。[!UICONTROL Server-to-Server] 对于目标，我们会脱机传输数据(实时或批量)，我们需要发送目标合作伙伴理解的ID，以便将其映射回浏览器。区段可寻址数字是区段总人口的子集。

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. 目标合作伙伴只需选取区段映射并使用该信息即可。因此，请考虑Cookie和URL目标的匹配率总是100%。
