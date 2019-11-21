---
description: 面向Audience Manager客户的GDPR就绪性指南
seo-description: 面向Audience Manager客户的GDPR就绪性指南
seo-title: 面向Audience Manager客户的GDPR就绪性指南
solution: Audience Manager
title: 面向Audience Manager客户的GDPR就绪性指南
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# 面向Audience Manager客户（数据管理者）的GDPR就绪性指南 {#gdpr-readiness-guidance}

Audience manager建议在数据管理和组织就绪性方面采取主动行动。 这将帮助您确保为与访问或删除请求相关的流程组织消费者数据，您的团队将能够被启用并被授权管理这些请求，而您的消费者（数据主体）将拥有与您的品牌相关的积极且差异化的体验。

作为您的数据处理者，Adobe无法就GDPR要求以及从数据主体获得同意的过程提供法律建议。 请咨询您的法律顾问，以获得有关贵组织遵守GDPR的指导。

## 数据管理：开始考虑如何在Audience manager实例中管理您的消费者数据

* 查看您的营销团队用来识别Audience manager中用户的各种客户ID以及存储这些用户的数据源。 这将简化请求流程（如删除或访问），因为某些数据类型在引入Audience manager之前将由您的团队散列化。
* IDFA/GAID移动设备ID用于Audience manager中的多个用例。 如果您使用的是Adobe Mobile SDK，请确保提交Experience Cloud ID(MID)和IDFA/GAID，以确保GDPR答复完成。
* 随着个人数据的定义越来越广泛，IP地址可能会被视为您所在地区的个人数据。 主动与Adobe Consulting联系以模糊化最后八位字节。
* 确定在数据主体发出GDPR请求时确认其身份的验证／身份验证策略和流程。
* 考虑使用 [数据导出控制](../../features/data-export-controls.md) ，阻止受众激活存储个人数据的技术。 例如，具有第三方数据的细分不应整合到电子邮件服务提供商处。 设置一 [!UICONTROL Data Export Control] 个值，以确保组织中的任何人都不会意外激活此数据。
* 开始使用 [基于角色的访问控制](../../features/administration/administration-overview.md) ，以确保正确的团队可以访问预期的数据。
* 请考虑适 [当的数据保](../../faq/faq-privacy.md#data-retention-faq) 留期。
* 查看身份联系和隐私政策以及法律要求，了解何时何地将身份集合绑定在一起；通过Audience Manager的Profile Merge Rules(配置文件合并规 [则)进行适当的使用](../../features/profile-merge-rules/merge-rules-overview.md)。

## 组织就绪性：建立业务流程

* 确定接收／响应数据主体请求的流程。 考虑构建一个自动化工具，将请求提交到Audience Manager。
* 在您的DMP卓越中心内指定一个隐私联系人。 将贵组织的隐私联系人与您的Audience manager产品使用团队联系，了解您如何管理输入ID要求。
* 在与数据主体共享之前进行数据审阅。 记录您所执行的步骤，以帮助您建立责任。
