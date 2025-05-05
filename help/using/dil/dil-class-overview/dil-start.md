---
description: 描述类级别DIL文档中使用的身份验证要求和文本格式。
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: 开始使用类级别DILAPI
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# 开始使用类级别DILAPI{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>从2023年7月开始，Adobe已停止开发[!DNL Data Integration Library (DIL)]和[!DNL DIL]扩展。
>
>现有客户可以继续使用其[!DNL DIL]实施。 但是，Adobe在此点之后不会开发[!DNL DIL]。 建议客户评估[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)的长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应改用[Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)。

类级别DILAPI允许您以编程方式创建和使用Audience Manager对象。 类级别API与其他实例级别函数结合使用来设置值或返回数据。

## 开始使用类级别DILAPI {#get-started}

描述类级别[!UICONTROL DIL]文档中使用的身份验证要求和文本格式。

<!-- 

c_class_start.xml

 -->

使用类级别[!UICONTROL DIL] API时：

* 访问需要合作伙伴名称和容器命名空间ID (NSID)。 请联系您的Audience Manager客户经理以获取此信息。
* 将API文档中的任何示例&#x200B;*斜体*&#x200B;文本替换为您正在处理的方法所需的值、ID或其他变量。
* [!UICONTROL DIL]将编码数据写入目标Cookie。 例如，空格编码为`%20`，分号编码为`%3B`。
