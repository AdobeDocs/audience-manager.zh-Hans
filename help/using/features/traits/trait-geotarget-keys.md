---
description: 介绍可用于目标用户的通用平台级键值对，这些键值对包含您Audience Manager帐户中所有属性的地理变量。
seo-description: 介绍可用于目标用户的通用平台级键值对，这些键值对包含您Audience Manager帐户中所有属性的地理变量。
seo-title: 使用平台级别关键值进行地理定位
solution: Audience Manager
title: 使用平台级别关键值进行地理定位
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# 使用平台级别关键值进行地理定位 {#geotargeting-with-platform-level-keys}

介绍可用于目标用户的通用平台级键值对，这些键值对包含您Audience Manager帐户中所有属性的地理变量。

<!-- c_tb_platform_vars.xml -->

## 平台级变量{#platform-variables}的用途

平台级变量允许您从特定站点传入数据，并使其可用于[!DNL Audience Manager]帐户中所有属性的定位。 这些变量由[键值对](../../reference/key-value-pairs-explained.md)组成，键前缀为`d_`，如下所示。

## 将值添加到平台级别键{#adding-values}

对于某些平台级键，您可以自行指定值。 与其他密钥相关联，这些密钥与在事件调用中传入的相应[!DNL IP]地址相关联。 无论哪种情况，在[!UICONTROL Trait Builder]中构建特征时，您仍需要指定值。

## 用户定义的平台级密钥{#user-defined-keys}

使用以下键值对构建特征时指定值：

| 键 | 针对定位 |
|---|---|
| `d_zx` | 邮政编码（例如`d_zx=10022`）。 |

## 由IP地址{#keys-ip-address}定义的平台级密钥

我们与[Digital Envoy](https://www.digitalenvoy.com/)合作，获取并更新以下密钥的人口统计和地理数据。 这些键的值通过将[!DNL IP]地址与相应的地理和人口统计数据相匹配来确定。 但是，在[!UICONTROL Trait Builder]中创建key-value对时，仍必须输入value参数。

| 键 | 针对定位 |
|--- |--- |
| d_area_code | [北美地区代码](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。例如： <ul><li>**特征**:d_area_code=801</li><li>**特征名称**:犹他州</li></ul> |
| d_city | 城市和城镇。 下载[城市列表](assets/d_city.txt)。  例如： <ul><li>特征： d_city=波恩</li><li>特征名称：波恩</li></ul> **提示**:您可以 `d_city` 结合使 `d_country` 用，确保您没有针对不同国家／地区同名的两个城市。使用`d_postal_code`可以更具体地定位。 |
| d_country | 值与ISO国家／地区代码相对应。 有关代码的可搜索列表，请参阅[ISO在线浏览平台](https://www.iso.org/obp/ui/#home)。 <br>  针对联合王国是唯一不遵守ISO 3166的特殊情况。您应使用“UK”而不是“GB”在英国进行定位。  目标荷属安的列斯群岛，代码“AN”自2010年起已弃用。 该地区已分为五个单独的领土单位。 这意味着，在荷属安的列斯群岛，不应使用“AN”，而应使用“CW”、“SX”和“BQ”的国家代码的组合。  例如： <br>  特征： d_country=CZ <br>  特征名称：捷克<br>  特征： d_country=UK <br>  特征名称：联合王国<br>  特征： d_country=CW OR d_country=SX OR d_country=BQ <br>  特征名称：荷属安的列斯群岛 |
| d_dma_code | 城域DMA代码。 下载[DMA区域列表](assets/DMAregions.csv)（.csv格式）。  例如： <ul><li>特征： d_dma_code=807</li><li>特征名称：旧金山</li></ul> |
| d_lat | Latitude（例如d_lat=40.75）。 下载[纬度列表](assets/d_lat.txt)。 |
| d_long | 经度（例如d_long=73.98）。 下载[经度列表](assets/d_long.txt)。 |
| d_postal_code | 邮政编码（不包括扩展+4代码）。 下载[邮政编码列表](assets/d_postal_code.txt)。  例如： <ul><li>特征： d_postal_code=84004 </li><li>特征名称：阿尔卑斯</li></ul> |
| d_state | 美国州的缩写（2个字符）。 下载[状态代码列表](assets/d_state.txt)。  例如： <ul><li>特征： d_state=NY </li><li>特征名称：纽约</li></ul>d_state包含不同国家／地区不同状态的重复值。 例如，d_state == &quot;on&quot;匹配多个状态：安大略省（加拿大）、翁多（尼日利亚）、奥沙纳（纳米比亚）。 我们建议将此信号与d_country等其他信号相结合，以实现更具体的地理定位。 |
| d_region | 区域字母数字ID。 下载[区域列表](assets/Country_RegionCodes_City.csv)。  然后，您可以使用此列表将区域ID与区域名称匹配。 |
| d_isp | ISP/组织。 下载[ISP列表](assets/d_isp.txt)。 |

[所有基于位置的信号](assets/all.txt)的列表按以下顺序包括上述所有信号：`d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

