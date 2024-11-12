---
description: 描述可用于通过Audience Manager帐户中所有属性的地理变量来定位的常用平台级别键值对。
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: 带有平台级别密钥的Geotargeting
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# 带有平台级别密钥的Geotargeting {#geotargeting-with-platform-level-keys}

描述可用于通过Audience Manager帐户中所有属性的地理变量来定位的常用平台级别键值对。

<!-- c_tb_platform_vars.xml -->

## 平台级别变量的用途 {#platform-variables}

平台级别的变量允许您获取从特定网站传入的数据，并使其可用于跨[!DNL Audience Manager]帐户中的所有属性进行定位。 这些变量由[键值对](../../reference/key-value-pairs-explained.md)组成，键的前缀为`d_`，如下所示。

## 向平台级别键值添加值 {#adding-values}

对于某些平台级别的键，您可以自行指定值。 与其他人一起，这些键与在事件调用中传入的相应[!DNL IP]地址相关联。 无论哪种情况，在[!UICONTROL Trait Builder]中构建特征时，您仍需要指定值。

## 用户定义的平台级别键 {#user-defined-keys}

如果您已经或正在建立一个流程来定义和收集键值对，则利用此选项。 如果要使用由IP地址预定义的密钥，请继续下一部分。 对于用户定义的键值，您可以在使用这些键值对构建特征时指定值：

| 键 | 用于定位 |
|---|---|
| `d_zx` | 邮政编码（例如，`d_zx=10022`）。 |

## 由IP地址定义的平台级别密钥 {#keys-ip-address}

我们与[数字特使](https://www.digitalenvoy.com/)合作，获取并更新以下键值的人口统计和地理数据。 这些键的值是通过将[!DNL IP]地址与相应的地理和人口统计数据匹配来确定的。 但是，在[!UICONTROL Trait Builder]中创建键值对时，仍必须输入value参数。

| 键 | 用于定位 |
|--- |--- |
| d_area_code | [北美区域代码](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes)。  例如： <ul><li>**特征**： d_area_code=801</li><li>**特征名称**：犹他州</li></ul> |
| d_city | 城镇。 下载[城市列表](assets/d_city.txt)。  例如： <ul><li>特征： d_city=bonn</li><li>特征名称：Bonn</li></ul> **提示**：您可以将`d_city`与`d_country`结合使用，以确保您的目标城市不是位于不同国家/地区的两个同名城市。 通过使用`d_postal_code`，您可以在定位中更加具体。 |
| d_country | 值对应于ISO国家/地区代码。 有关代码的可搜索列表，请参阅[ISO在线浏览平台](https://www.iso.org/obp/ui/#home)。 <br>  针对联合王国是唯一不遵守ISO 3166的特殊情况。 在英国进行定位时，您应该使用“UK”而非“GB”。  为了定位荷属安的列斯，代码“AN”自2010年以来已被弃用。 这一地区已分成五个单独的领土单位。 这意味着，在荷属安的列斯群岛进行定位时，不应使用“AN”，而应结合使用“CW”、“SX”和“BQ”等国家/地区代码。  例如： <br>  特征： d_country=CZ <br>  特征名称：捷克共和国<br>  特征： d_country=UK <br>  特征名称：英国<br>  特征： d_country=CW OR d_country=SX OR d_country=BQ <br>  特征名称：荷属安的列斯 |
| d_dma_code | 都市区DMA代码。 下载[DMA区域列表](assets/DMAregions.csv) （.csv格式）。  例如： <ul><li>特征：d_dma_code=807</li><li>特征名称：旧金山</li></ul> |
| d_lat | 纬度（例如d_lat=40.75）。 下载[纬度列表](assets/d_lat.txt)。 |
| d_long | 经度（例如d_long=73.98）。 下载[经度列表](assets/d_long.txt)。 |
| d_postal_code | 邮政编码（不包括扩展的+4代码）。 下载[邮政编码列表](assets/d_postal_code.txt)。  例如： <ul><li>特征：d_postal_code=84004 </li><li>特征名称：Alpine</li></ul> |
| d_state | 美国州的2个字符缩写。 下载[州代码列表](assets/d_state.txt)。  例如： <ul><li>特征：d_state=NY </li><li>特征名称：New York</li></ul>d_state包含不同国家/地区的不同状态的重复值。 例如， d_state==“on”匹配多个州：安大略（在加拿大）、安多（在尼日利亚）、奥沙纳（在纳米比亚）。 我们建议将此信号与d_country等其他信号相结合，以获得更具体的地理定位。 |
| d_region | 区域字母数字ID。 下载[区域列表](assets/Country_RegionCodes_City.csv)。  然后，您可以使用此列表将区域ID与区域名称进行匹配。 |
| d_isp | ISP/组织 下载[ISP列表](assets/d_isp.txt)。 |

[所有基于位置的信号](assets/all.txt)的列表按以下顺序包含上述所有信号： `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [关键变量的前缀要求](../../features/traits/trait-variable-prefixes.md)

