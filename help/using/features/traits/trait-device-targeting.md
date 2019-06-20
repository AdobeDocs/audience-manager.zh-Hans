---
description: 描述常用平台级密钥-值对，以使用Audience Manager帐户中所有属性中的设备相关变量定位用户。
seo-description: 描述常用平台级密钥-值对，以使用Audience Manager帐户中所有属性中的设备相关变量定位用户。
seo-title: 使用平台级密钥定位设备
solution: Audience Manager
title: 使用平台级密钥定位设备
uuid: bc048cc5-3df1-49bc-ac78-3ea5 d7 edd9 cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

描述常用平台级密钥-值对，以使用Audience Manager帐户中所有属性中的设备相关变量定位用户。

## Purpose of Platform-level Variables {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Platform-level Keys Defined by User Agent {#keys-user-agent}

[!UICONTROL Data Collection Servers] 从请求中 [的用户代理标头](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) 提取这些键 `HTTP` 的值。The values represent device-level information from the [!UICONTROL Device Atlas] database. 下表中的信号可从用户代理示例中提取。[根据度量，下载最常用密钥](assets/device_keys.csv)[!UICONTROL Device Atlas] 的列表。

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
>Even if one or more signals cannot be retrieved from the user agent header, the other signals will still be passed to the [!UICONTROL Data Collection Servers].

>[!MORE_ LIKE_ This]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

