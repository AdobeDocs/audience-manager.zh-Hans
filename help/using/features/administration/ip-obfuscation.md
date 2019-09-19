---
description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
seo-description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
solution: Audience Manager
title: IP 地址模糊处理
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP 地址模糊处理 {#ip-obfuscation}

使用此功能可模糊化在Audience Manager中收集的IP地址。

## 概述和方法 {#overview-and-methodology}

由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。

### IP模糊化方法

Adobe Audience manager遵循“按设计保护隐私”的原则，允许客户在全球所有地理区域或特定国家／地区的UI中启用IP模糊化。 启用此设置后，当将IP地址引入Audience manager时，IP地址的最后八位字节（最后一部分）将立即被丢弃。 Audience manager在处理之前（包括在任何可选的地理查找或IP地址记录之前），会丢弃IP地址的这一部分。 例如：

* 模糊处理前： `255.255.255.255`
* 混淆后： `255.255.255.0`

另请参阅“数据隐私”部分中的收集IP地址和IP [地址模糊化](/help/using/overview/data-security-and-privacy/data-privacy.md)。

## IP地址模糊化要求 {#ip-obfuscation-requirements}

IP地址模糊化仅对Audience manager管理员帐户可用。 请参 [阅创建用户](/help/using/features/administration/administration-overview.md#create-users) ，了解如何为用户分配管理员权限。

>[!NOTE]
>
> 由于Audience manager处理的数据量很大，从更新设置开始，IP模糊化更改可能需要4小时才能生效。

## 配置IP地址模糊化 {#configure-ip-obfuscation}

请按照以下步骤配置IP地址模糊化。

1. 使用管理员帐户登录到Audience Manager，然后转到“管理”&gt;“ **隐私”**。
2. 选择要使用的IP模糊处理类型。
   1. **** 模糊处理所有IP地址：选择此选项可让Audience Manager模糊化所有访客IP地址的最后八位字节，而不管它们来自哪个区域。
   2. **** 模糊化特定国家／地区的IP地址：选择此选项可让Audience Manager模糊化特定国家／地区的访客IP地址的最后八位字节。 使用国 **家／地区列表** 或相应的“搜索”字段查找国家／地区以启用其IP模糊处理，然后单击“+”图标以将其添加到“已选 **定进行模糊处理****** ”列表。 将所有必需国家／地区添加到“选定进行模糊 **处理”列表后** ，单击 **保存**。

![](assets/ip-obfuscation.png)

## 禁用IP地址模糊处理 {#disable-ip-obfuscation}

要全局禁用IP地址模糊处理，请转到“管 **理”&gt;“隐私**”，选择“ **不模糊化IP地址**”，然后单击“ **保存**”。

要禁用特定国家／地区的IP地址模糊处理，请在“选定进行模糊处理”列 **表中查找国家／地区** ，然后单击相应的 **X** 图标。 Click **Save** when you're done.

## 相关概念 {#related-concepts}

* [数据隐私](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP地址模糊化视频演示
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hans)

