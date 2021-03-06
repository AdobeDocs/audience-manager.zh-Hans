---
description: 描述可用于通过您的Audience Manager帐户中所有属性的地理变量定位用户的常用平台级别键值对。
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: 使用平台级别关键值进行地理定位
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# 使用平台级别关键值进行地理定位 {#geotargeting-with-platform-level-keys}

描述可用于通过您的Audience Manager帐户中所有属性的地理变量定位用户的常用平台级别键值对。

<!-- c_tb_platform_vars.xml -->

## 平台级变量的用途 {#platform-variables}

平台级变量允许您获取从特定网站传入的数据，并使其可用于定位 [!DNL Audience Manager] 帐户。 这些变量由 [键值对](../../reference/key-value-pairs-explained.md) 键前缀为 `d_` 如下所示。

## 向平台级别键值添加值 {#adding-values}

对于某些平台级别的键，您可以自行指定值。 与其他密钥相关联 [!DNL IP] 在事件调用中传入的地址。 无论哪种情况，在中构建特征时，您仍需要指定值 [!UICONTROL Trait Builder].

## 用户定义的平台级别键值 {#user-defined-keys}

如果您已经或正在建立定义和收集键值对的流程，则使用此选项。 如果要使用由IP地址预定义的密钥，请继续下一部分。 对于用户定义的键，您可以在使用以下键值对构建特征时指定值：

| 键 | 用于定位 |
|---|---|
| `d_zx` | 邮政编码(例如， `d_zx=10022`)。 |

## 由IP地址定义的平台级别密钥 {#keys-ip-address}

我们合作 [Digital Envoy](https://www.digitalenvoy.com/) 获取和更新以下键的人口统计和地理数据。 这些键的值由匹配 [!DNL IP] 地址对应的地理和人口数据。 但是，在中创建键值对时，您仍必须输入值参数 [!UICONTROL Trait Builder].

| 键 | 用于定位 |
|--- |--- |
| d_area_code | [北美地区代码](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  例如： <ul><li>**特征**:d_area_code=801</li><li>**特征名称**:犹他州</li></ul> |
| d_city | 城镇。 下载 [城市列表](assets/d_city.txt).  例如： <ul><li>特征：d_city=bonn</li><li>特征名称：波恩</li></ul> **笔尖**:您可以使用 `d_city` 耦合 `d_country` 以确保您不会针对不同国家/地区名称相同的两个城市。 通过使用 `d_postal_code`. |
| d_country | 值与ISO国家/地区代码相对应。 有关可搜索的代码列表，请参阅 [ISO在线浏览平台](https://www.iso.org/obp/ui/#home). <br>  针对英国的定位是唯一不遵守ISO 3166的特例。 在英国应使用“UK”而不是“GB”进行定位。  要定位荷属安的列斯群岛，自2010年起，代码“AN”已被弃用。 该地区已分为五个单独的领土单位。 这意味着，在荷属安的列斯群岛，对于目标，不应使用“AN”，而应使用“CW”、“SX”和“BQ”的国家/地区代码的组合。  例如：  <br>  特征：d_country=CZ  <br>  特征名称：捷克共和国 <br>  特征：d_country=UK <br>  特征名称：英国  <br>  特征：d_country=CW OR d_country=SX OR d_country=BQ  <br>  特征名称：荷属安的列斯群岛 |
| d_dma_code | 城域DMA代码。 下载 [DMA区域列表](assets/DMAregions.csv) （.csv格式）。  例如： <ul><li>特征：d_dma_code=807</li><li>特征名称：旧金山</li></ul> |
| d_lat | 纬度（例如d_lat=40.75）。 下载 [纬度列表](assets/d_lat.txt). |
| d_long | 经度（例如d_long=73.98）。 下载 [经度列表](assets/d_long.txt). |
| d_postal_code | 邮政编码（排除扩展的+4代码）。 下载  [邮政编码列表](assets/d_postal_code.txt).  例如： <ul><li>特征：d_postal_code=84004 </li><li>特征名称：阿尔派</li></ul> |
| d_state | 美国州的缩写（2个字符）。 下载 [状态代码列表](assets/d_state.txt).  例如： <ul><li>特征：d_state=NY </li><li>特征名称：纽约</li></ul>d_state包含不同国家/地区中不同状态的重复值。 例如，d_state == &quot;on&quot;匹配多个状态：安大略省（加拿大）、翁多（尼日利亚）、奥沙纳（纳米比亚）。 我们建议将此信号与其他信号（如d_country）耦合，以便进行更具体的地理定位。 |
| d_region | 区域字母数字ID。 下载 [地区列表](assets/Country_RegionCodes_City.csv).  然后，您可以使用此列表将区域ID与区域名称匹配。 |
| d_isp | ISP/组织。 下载 [ISP列表](assets/d_isp.txt). |

列表 [所有基于位置的信号](assets/all.txt) 按以下顺序包含上述所有信号： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

