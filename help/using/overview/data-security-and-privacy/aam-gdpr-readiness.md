---
description: 面向 Audience Manager 客户的 GDPR 准备指南
seo-description: 面向 Audience Manager 客户的 GDPR 准备指南
seo-title: 面向 Audience Manager 客户的 GDPR 准备指南
solution: Audience Manager
title: 面向 Audience Manager 客户的 GDPR 准备指南
feature: 数据治理和隐私
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 99%

---

# 面向 Audience Manager 客户（数据控制者）的 GDPR 准备指南{#gdpr-readiness-guidance}

Audience Manager 建议在数据管理和组织准备方面采取主动行动。这将帮助您确保为与访问或删除请求相关的流程组织消费者数据，使您的团队有能力并有权管理这些请求，并且消费者（数据主体）将对您的品牌拥有积极而独特的体验。

作为数据处理者，Adobe 无法就 GDPR 要求以及获得数据主体同意的流程提供法律建议。请咨询您的法律顾问，以便为贵组织提供有关 GDPR 合规性的指导。

## 数据管理：开始思考如何在 Audience Manager 实例中管理消费者数据

* 查看您的营销团队用于在 Audience Manager 中标识用户的各种客户 ID，以及存储这些客户 ID 的数据源。这将简化请求（如删除或访问）流程，因为某些数据类型在摄取到 Audience Manager 之前将由您的团队进行哈希处理。
* IDFA/GAID 移动设备 ID 可用于 Audience Manager 中的多个用例。如果您使用的是 Adobe Mobile SDK，请确保一起提交 Experience Cloud ID (MID) 和 IDFA/GAID，以确保 GDPR 响应是完整的。
* 随着个人数据的定义越来越广泛，IP 地址可能会被视为您所在区域的个人数据。主动联系 Adobe 咨询团队，以模糊处理 IP 地址的最后八位字节。
* 确定验证/身份验证策略和流程，以在数据主体提出 GDPR 请求时确认其身份。
* 考虑使用[数据导出控制](../../features/data-export-controls.md)以阻止受众激活个人数据存储技术。例如，具有第三方数据的区段不应整合到电子邮件服务提供程序中。设置 [!UICONTROL Data Export Control] 以确保贵组织中的任何人都不会意外激活此数据。
* 开始利用[基于角色的访问控制](../../features/administration/administration-overview.md)，确保相应的团队能够访问预期的数据。
* 考虑为数据设置适当的[保留期](../../faq/faq-privacy.md#data-retention-faq)。
* 查看身份链接和隐私政策及法律要求，了解何时何地可将身份集合绑定在一起；可通过 Audience Manager 的[配置文件合并规则](../../features/profile-merge-rules/merge-rules-overview.md)合理使用。

## 组织准备：建立业务流程

* 确定接收/响应数据主体请求的流程。考虑构建一个自动化工具，用于将请求提交给 Audience Manager。
* 在您的 DMP 卓越中心内指定一个隐私联系人。将贵组织的隐私联系人与 Audience Manager 产品使用团队联系起来，了解如何管理输入 ID 要求。
* 在与数据主体共享数据之前，先对数据进行审查。记录实施的各个步骤，帮助您建立问责制。
