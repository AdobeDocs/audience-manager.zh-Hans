---
description: 介绍可用于目标用户的通用平台级键值对，这些对在Audience Manager帐户的所有属性中与设备相关的变量。
seo-description: 介绍可用于目标用户的通用平台级键值对，这些对在Audience Manager帐户的所有属性中与设备相关的变量。
seo-title: 使用平台级别关键值定位设备
solution: Audience Manager
title: 使用平台级别关键值定位设备
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 9%

---


# 使用平台级别关键值定位设备 {#device-targeting-with-platform-level-keys}

介绍可用于目标用户的通用平台级键值对，这些对在Audience Manager帐户的所有属性中与设备相关的变量。

## 平台级变量{#platform-variables}的用途

<!-- c_tb_device_targeting.xml -->

平台级变量允许您从特定站点传入数据，并使其可用于[!DNL Audience Manager]帐户中所有属性的定位。 这些变量由[键值对](../../reference/key-value-pairs-explained.md)组成，键前缀为`d_`，如下所示。

## 由用户代理{#keys-user-agent}定义的平台级密钥

[!UICONTROL Data Collection Servers]从`HTTP`请求中的[用户代理头](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)提取这些键的值。 这些值表示来自[!UICONTROL Device Atlas]数据库的设备级信息。 下表中的信号可用，从用户代理示例中提取。 [根据测量值下载最常用的](assets/device_keys.csv)列表键的 [!UICONTROL Device Atlas] 。

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
>即使一个或多个信号无法从用户代理头中检索，其他信号仍会传递到[!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

