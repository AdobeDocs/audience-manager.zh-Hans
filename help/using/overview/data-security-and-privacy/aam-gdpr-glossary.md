---
description: 本文介绍欧洲《通用数据保护条例》(GDPR) 所使用的概念和术语，以及 Adobe Audience Manager 作为数据处理者如何满足各项 GDPR 要求。
seo-description: 本文介绍欧洲《通用数据保护条例》(GDPR) 所使用的概念和术语，以及 Adobe Audience Manager 作为数据处理者如何满足各项 GDPR 要求。
seo-title: GDPR 术语表
solution: Audience Manager
title: GDPR 术语表
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
feature: 数据治理和隐私
exl-id: 36930703-745e-4fbd-ad18-ba9efb77eb7e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 99%

---

# GDPR 术语表 {#gdpr-glossary}

## 概述 {#overview}

本文介绍欧洲《通用数据保护条例》(GDPR) 所使用的概念和术语，以及 Adobe Audience Manager 作为数据处理者如何满足各项 GDPR 要求。

GDPR 于 2018 年 5 月 25 日生效，其主要目标是让欧盟地区的每个人（数据主体）能够更好地控制其个人数据，同时通过统一欧盟内部的法规来简化对国际企业的监管环境。在 Adobe 为实现 GDPR 合规积极做准备的过程中，Adobe Audience Manager 团队根据需要对服务和流程进行了改进，以支持来自数据主体（即您的消费者）的数据访问和删除请求。

另请参阅 [Experience Cloud GDPR 常见问题解答](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)，以更好地了解 Experience Cloud 为实现 GDPR 合规采取的措施。

## GDPR 术语表 {#gdpr-glossay}

了解与 GDPR 相关的主要术语。下面重点介绍了一些最常用的术语。

 

**数据控制者：** GDPR 将“控制者”定义为“...单独或与他人共同决定个人数据处理目的和方式的法人...”。Audience Manager 客户属于数据控制者。客户可以控制在 Audience Manager 中管理数据的方式。

 

**数据处理者：**“处理者”是指“...代表控制者处理个人数据的法人...”。对于 Audience Manager，Adobe 在运行该服务时，便是在充当“数据处理者”，因为 Adobe 是在代表控制者通过 Audience Manager 处理个人数据。Adobe 仅根据数据控制者的指示处理个人数据（如与客户达成的协议中所述，或通过在 Audience Manager 中采取相应措施）。

 

**数据主体：**&#x200B;与个人数据相关联的个人。对于 Audience Manager，数据主体是指 Audience Manager 客户的消费者或最终用户。如果 Adobe 直接从数据主体接收请求，Adobe 会将这些请求转发给相应的 Audience Manager 客户。

 

**同意：**“同意”是指“数据主体通过声明或明确的肯定性行为作出的自愿、具体、知情且明确的意思表示，表明其同意处理与其有关的个人数据”。获取同意是数据控制者的责任，而非 Adobe（通过 Audience Manager）的责任。

 

**访问：**&#x200B;数据主体有权要求数据控制者确认是否对其个人数据进行了处理。如果数据控制者确实对数据主体的个人数据进行了处理，则必须提供对个人数据的访问和备份。数据控制者可要求 Adobe 协助处理来自数据主体的访问请求。

 

**删除：** GDPR 规定了“被遗忘权”或“删除权”。数据主体有权要求数据控制者删除其个人数据。数据控制者与数据处理者（包括 Adobe）合作，共同支持来自数据主体的数据删除请求。

 

**更正：**&#x200B;数据主体有权要求数据控制者更正不准确的个人数据。数据控制者与数据处理者（包括 Adobe）合作，共同支持来自数据主体的数据更正请求。

 

**Audience Manager 标识符 (ID)：** Adobe Audience Manager 存储各种类型的 ID。[Audience Manager 标识符](data-privacy-ids.md)页面汇总了这些 ID 及其相应数据源，还提供了简短说明。向 [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 发送请求时，需引用这些 ID 以发送数据主体提出的数据删除或访问请求。

 

**个人数据：** GDPR 扩展了对个人数据的定义。依照 GDPR 的规定，Audience Manager 中的所有数据均可根据客户用例归类为个人数据。

 

**禁止的数据：** Audience Manager 禁止客户摄取可直接识别个人身份的信息，例如名字和姓氏、电子邮件 ID、CRM ID。Adobe Experience Cloud 解决方案也禁止获取敏感信息。有关这些要求的详细信息，请参阅您与 Adobe 签署的合同。如果需要将这些类型的数据点摄取到 Audience Manager 中，请联系 Adobe 咨询团队，以获取有关在摄取数据前对这些 ID 进行哈希处理的建议。
