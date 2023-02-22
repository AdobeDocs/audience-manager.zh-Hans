---
description: 介绍可用于在Audience Manager帐户的所有属性中使用与设备相关的变量来定位用户的常用平台级别键值对。
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: 使用平台级别关键值定位设备
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# 使用平台级别关键值定位设备 {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google已更新 [!DNL Google Chrome] 全部 [!DNL Chromium]基于的浏览器，可最大程度地减少通过 `User-Agent` 标题。
>从2023年3月开始，Audience Manager可利用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). 继续使用通过 `User-Agent` 标题，您必须使用 [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 启用 [高熵用户代理客户端提示](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>不支持这些更新 [DIL](../../../using/dil/dil-overview.md)，因此Audience Manager使用 [!DNL DIL] 将无法通过 `User-Agent` 标题。

介绍可用于在Audience Manager帐户的所有属性中使用与设备相关的变量来定位用户的常用平台级别键值对。

## 平台级变量的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台级变量允许您获取从特定网站传入的数据，并使其可用于定位 [!DNL Audience Manager] 帐户。 这些变量由 [键值对](../../reference/key-value-pairs-explained.md) 键前缀为 `d_` 如下所示。

## 由用户代理定义的平台级别密钥 {#keys-user-agent}

的 [!UICONTROL Data Collection Servers] 从 [用户代理头](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` 请求。 这些值表示 [!UICONTROL Device Atlas] 数据库。 下表中的信号可用，这是从用户代理示例中提取的。 [下载最常用键的列表](assets/device_keys.csv)，根据 [!UICONTROL Device Atlas] 测量。

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
>即使一个或多个信号无法从用户代理标头中检索到，其他信号仍将传递到 [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

