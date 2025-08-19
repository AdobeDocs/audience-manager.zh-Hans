---
description: 描述可用于通过Audience Manager帐户中所有属性的设备相关变量来定位用户的常用平台级别键值对。
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: 使用平台级别关键值定位设备
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# 使用平台级别关键值定位设备 {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google已更新[!DNL Google Chrome]和所有基于[!DNL Chromium]的浏览器的功能，以最大限度地减少通过`User-Agent`标头收集的信息。
>&#x200B;>从2023年3月开始，Audience Manager利用[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)支持这些更新。 要继续使用通过`User-Agent`标头提供的特征信息，您必须使用[Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=zh-Hans)并启用[高熵用户代理客户端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=zh-Hans)。
>&#x200B;>[DIL](../../../using/dil/dil-overview.md)不支持这些更新，因此使用[!DNL DIL]的Audience Manager客户将无法通过`User-Agent`标头收集特征信息。

描述可用于通过Audience Manager帐户中所有属性的设备相关变量来定位用户的常用平台级别键值对。

## 平台级别变量的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台级别的变量允许您获取从特定网站传入的数据，并使其可用于跨[!DNL Audience Manager]帐户中的所有属性进行定位。 这些变量由[键值对](../../reference/key-value-pairs-explained.md)组成，键的前缀为`d_`，如下所示。

## 用户代理定义的平台级别密钥 {#keys-user-agent}

[!UICONTROL Data Collection Servers]从[请求中的](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)用户代理标头`HTTP`提取这些密钥的值。 值表示来自[!UICONTROL Device Atlas]数据库的设备级信息。 下表中的信号可用，如从用户代理示例中提取的。 [根据](assets/device_keys.csv)测量结果，下载最常用键的列表[!UICONTROL Device Atlas]。

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>即使无法从用户代理标头中检索到一个或多个信号，其他信号仍将传递到[!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)
