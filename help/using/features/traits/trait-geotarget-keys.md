---
description: 描述可用于定位用户使用Audience Manager帐户中所有属性的地理变量的常用平台级密钥值对。
seo-description: 描述可用于定位用户使用Audience Manager帐户中所有属性的地理变量的常用平台级密钥值对。
seo-title: 使用平台级密钥进行地理定位
solution: Audience Manager
title: 使用平台级密钥进行地理定位
uuid: c7e4cbfe-e564-404e-a565-bbe5 fb519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

描述可用于定位用户使用Audience Manager帐户中所有属性的地理变量的常用平台级密钥值对。

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

对于某些平台级别的键，您可以自己指定值。With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

在使用这些键值对构建特征时，您可以指定值：

| 键 | 针对定位 |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

We work with [Digital Envoy](https://www.digitalenvoy.com/) to obtain and update the demographic and geographic data for the keys below. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| 键 | 针对定位 |
|--- |--- |
| d_ area_ code | [北美地区代码](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。例如： <ul><li>**特征**：d_ area_ code=801</li><li>**特征名称**：犹他</li></ul> |
| d_ city | 城市和城镇。Download the [cities list](assets/d_city.txt).  例如： <ul><li>特征：d_ city= bonn</li><li>特征名称：Bonn</li></ul> **提示**：您可以结合使用 `d_city` ， `d_country` 确保不针对在不同国家/地区具有相同名称的两个城市。You can be even more specific in your targeting by using `d_postal_code`. |
| d_ countries | 值对应ISO国家/地区代码。For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>针对英国的定位是唯一一个不符合ISO3166的特殊案例。对于在英国定位，您应使用“英国”而不是“GB”。为了定位荷兰安的列斯群岛，2010年以来已弃用代码“AN”。该区域已分为五个单独的领土单元。隐含在于，对于在荷兰安的列斯群岛定位，您不应使用“AN”，但不应使用“CW”、“SX”和“BQ”国家代码组合。For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ DMA_ code | Metropitan区域DMA代码。Download the [DMA region list](assets/DMAregions.csv) (.csv format).  例如： <ul><li>特征：d_ DMA_ code=807</li><li>特征名称：旧金山</li></ul> |
| d_ lat | 纬度(例如，d_ lat=40.75)。Download the [latitudes list](assets/d_lat.txt). |
| d_ long | Publisher(例如，d_ long=73.98)。Download the [longitudes list](assets/d_long.txt). |
| d_ mail_ code | 邮政编码(排除扩展的+代码)。Download the  [postal codes list](assets/d_postal_code.txt).  例如： <ul><li>特征：d_ mail_ code=84004 </li><li>特征名称：Alpin</li></ul> |
| d_ state | 美国州个字符缩写。Download the [states codes list](assets/d_state.txt).  例如： <ul><li>特征：d_ state= NY </li><li>特征名称：纽约</li></ul>d_ state包含不同国家/地区不同状态的重复值。例如，d_ state=="on"匹配多个状态：Ontario(加拿大)、Ondo(尼日利亚境内)、Oshana(纳米比亚)。我们建议将此信号与dd_ country这样的其他信号配对，以便更具体地定位。 |
| d_地区 | 区域字母数字ID。Download the [region list](assets/Country_RegionCodes_City.csv).  然后，您可以使用此列表将区域ID与区域名称匹配。 |
| d_ sp | ISP/组织。Download the [ISP List](assets/d_isp.txt). |

[所有基于位置的信号](assets/all.csv) 列表包括以上所有信号，按顺序排列： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ This]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

