---
description: 描述类级别DIL文档中使用的身份验证要求和文本格式。
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: 开始使用类级别 DIL API
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# 开始使用类级别 DIL API{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>自2023年7月起，Adobe已停止开发电子烟产品。 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 扩展。
><br><br>
>现有客户可以继续使用其 [!DNL DIL] 实现。 但是，Adobe将不会开发 [!DNL DIL] 超越了这一点。 建议客户评估 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 长期数据收集策略。
><br><br>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而是。

类级别DILAPI允许您以编程方式创建和使用Audience Manager对象。 类级别API与其他实例级别的函数结合使用来设置值或返回数据。

## 开始使用类级别 DIL API {#get-started}

描述类级别中使用的身份验证要求和文本格式 [!UICONTROL DIL] 文档。

<!-- 

c_class_start.xml

 -->

使用类级别时 [!UICONTROL DIL] API：

* 访问需要合作伙伴名称和容器命名空间ID (NSID)。 请联系您的Audience Manager客户经理以获取此信息。
* 替换任何示例 *斜体* API文档中的文本，其中包含值、ID或您使用的方法所需的其他变量。
* [!UICONTROL DIL] 将编码数据写入目标Cookie。 例如，空格将编码为 `%20` 和分号为 `%3B`.
