---
description: 介绍可用于在Audience Manager帐户的所有属性中使用与设备相关的变量来定位用户的常用平台级别键值对。
seo-description: 介绍可用于在Audience Manager帐户的所有属性中使用与设备相关的变量来定位用户的常用平台级别键值对。
seo-title: 使用平台级别关键值定位设备
solution: Audience Manager
title: 使用平台级别关键值定位设备
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: 特征
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---

# 使用平台级别关键值定位设备 {#device-targeting-with-platform-level-keys}

介绍可用于在Audience Manager帐户的所有属性中使用与设备相关的变量来定位用户的常用平台级别键值对。

## 平台级变量{#platform-variables}的用途

<!-- c_tb_device_targeting.xml -->

平台级变量允许您获取从特定站点传入的数据，并使其可用于[!DNL Audience Manager]帐户中所有属性的定位。 这些变量由[键值对](../../reference/key-value-pairs-explained.md)组成，键的前缀为`d_`，如下所示。

## 用户代理{#keys-user-agent}定义的平台级密钥

[!UICONTROL Data Collection Servers]从`HTTP`请求的[用户代理标头](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)中提取这些键的值。 值表示[!UICONTROL Device Atlas]数据库中的设备级别信息。 下表中的信号可用，这是从用户代理示例中提取的。 [根据测量值下载最常用键](assets/device_keys.csv)的列 [!UICONTROL Device Atlas] 表。

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
>即使一个或多个信号无法从用户代理标头中检索到，其他信号仍将传递到[!UICONTROL Data Collection Servers]。

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

