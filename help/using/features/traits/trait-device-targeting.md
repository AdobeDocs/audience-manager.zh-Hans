---
description: 介绍在Audience Manager帐户中的所有属性中，使用设备相关变量定位用户的常见平台级键值对。
seo-description: 介绍在Audience Manager帐户中的所有属性中，使用设备相关变量定位用户的常见平台级键值对。
seo-title: 使用平台级密钥进行设备定位
solution: Audience Manager
title: 使用平台级密钥进行设备定位
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

介绍在Audience Manager帐户中的所有属性中，使用设备相关变量定位用户的常见平台级键值对。

## 平台级变量的用途 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

平台级变量允许您从特定站点传入的数据，并使其可用于在帐户中的所有属性中进行 [!DNL Audience Manager] 定位。 这些变量由键值对 [组成](../../reference/key-value-pairs-explained.md) ，键前缀 `d_` 如下所示。

## 由用户代理定义的平台级密钥 {#keys-user-agent}

从 [!UICONTROL Data Collection Servers] 请求中的用户代理头提取这 [些键的值](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)`HTTP` 。 这些值表示来自数据库的设备级 [!UICONTROL Device Atlas] 信息。 下表中的信号可用，从用户代理示例中提取。 [根据度量值下载最常用键的列表](assets/device_keys.csv)[!UICONTROL Device Atlas] 。

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
>即使一个或多个信号无法从用户代理头检索，其他信号仍将被传递给用户 [!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

