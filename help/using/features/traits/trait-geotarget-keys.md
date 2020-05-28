---
description: 介绍可用于目标用户的通用平台级键值对，这些键值对具有跨受众管理器帐户中所有属性的地理变量。
seo-description: 介绍可用于目标用户的通用平台级键值对，这些键值对具有跨受众管理器帐户中所有属性的地理变量。
seo-title: 使用平台级密钥进行地理定位
solution: Audience Manager
title: 使用平台级密钥进行地理定位
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
translation-type: tm+mt
source-git-commit: 8959e0023f7663d7a20080aaf130d469ed8a4313
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

介绍可用于目标用户的通用平台级键值对，这些键值对具有跨受众管理器帐户中所有属性的地理变量。

<!-- c_tb_platform_vars.xml -->

## 平台级变量的用途 {#platform-variables}

平台级变量允许您从特定站点传入数据，并使其可用于在帐户中的所有属性中进行 [!DNL Audience Manager] 定位。 这些变量由键 [值对组成](../../reference/key-value-pairs-explained.md) ，键前缀 `d_` 如下所示。

## 向平台级键添加值 {#adding-values}

对于某些平台级键，您可以自行指定值。 与其他一样，密钥与在事件呼 [!DNL IP] 叫中传入的相应地址相关联。 无论哪种情况，在中构建特征时仍需要指定值 [!UICONTROL Trait Builder]。

## 用户定义的平台级密钥 {#user-defined-keys}

使用以下键值对构建特征时指定值：

| 键 | 针对定位 |
|---|---|
| `d_zx` | 邮政编码(例如 `d_zx=10022`)。 |

## 由IP地址定义的平台级别密钥 {#keys-ip-address}

我们与Digital [Envoy合作](https://www.digitalenvoy.com/) ，获取并更新以下密钥的人口统计和地理数据。 这些键的值通过将地址与相应的地 [!DNL IP] 理和人口统计数据匹配来确定。 但是，在中创建键值对时，仍必须输入value参数 [!UICONTROL Trait Builder]。

| 键 | 针对定位 |
|--- |--- |
| d_area_code | [北美地区代码](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。  例如： <ul><li>**特征**:  d_area_code=801</li><li>**特征名称**: 犹他州</li></ul> |
| d_city | 城市和城镇。 下载城 [市列表](assets/d_city.txt)。  例如： <ul><li>特征：  d_city=波恩</li><li>特征名称： 波恩</li></ul> **提示**: 您可以 `d_city` 结合使 `d_country` 用，确保不针对不同国家／地区同名的两个城市。 使用，您可以在定位中更加具体 `d_postal_code`。 |
| d_country | 值与ISO国家／地区代码相对应。 有关代码的可搜索列表，请参 [阅ISO在线浏览平台](https://www.iso.org/obp/ui/#home)。 <br>  针对联合王国是唯一不遵守ISO 3166的特殊情况。 您应使用“UK”而不是“GB”在英国进行定位。  目标荷属安的列斯群岛，代码“AN”自2010年起已弃用。 该地区已分为五个单独的领土单位。 这意味着，在荷属安的列斯群岛，不应使用“AN”，而应使用“CW”、“SX”和“BQ”的国家代码的组合。  例如：  <br>  特征：  d_country=CZ特 <br>征名称： 捷克共 <br>和国特征：  d_country=英国特 <br>征名称： 英国特 <br>征：  d_country=CW OR d_country=SX OR d_country=BQ特 <br>征名称： 荷属安的列斯群岛 |
| d_dma_code | 城域DMA代码。 下载 [DMA区域列表](assets/DMAregions.csv) （.csv格式）。  例如： <ul><li>特征：  d_dma_code=807</li><li>特征名称： 旧金山</li></ul> |
| d_lat | Latitude（例如d_lat=40.75）。 下载纬度 [列表](assets/d_lat.txt)。 |
| d_long | 经度（例如d_long=73.98）。 下载经 [度列表](assets/d_long.txt)。 |
| d_postal_code | 邮政编码（不包括扩展+4代码）。 下载邮 [政编码列表](assets/d_postal_code.txt)。  例如： <ul><li>特征：  d_postal_code=84004 </li><li>特征名称： 阿尔卑斯</li></ul> |
| d_state | 美国州的缩写（2个字符）。 下载状 [态代码列表](assets/d_state.txt)。  例如： <ul><li>特征：  d_state=NY </li><li>特征名称： 纽约</li></ul>d_state包含不同国家／地区不同状态的重复值。 例如，d_state == &quot;on&quot;匹配多个状态： 安大略省（加拿大）、翁多（尼日利亚）、奥沙纳（纳米比亚）。 我们建议将此信号与d_country等其他信号相结合，以便更具体地理定位。 |
| d_region | 区域字母数字ID。 下载地 [区列表](assets/Country_RegionCodes_City.csv)。  然后，您可以使用此列表将区域ID与区域名称匹配。 |
| d_isp | ISP/组织。 下载 [ISP列表](assets/d_isp.txt)。 |

所有基 [于位置的信号的列表](assets/all.txt) ，按以下顺序包括上述所有信号： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [密钥变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

