---
description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
seo-description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
solution: Audience Manager
title: IP 地址模糊处理
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP 地址模糊处理 {#ip-obfuscation}

使用此功能模糊处理在Audience Manager中收集的IP地址。

## Overview and Methodology {#overview-and-methodology}

由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。

### IP模糊处理方法

遵循“隐私依据设计”的原则，Adobe Audience Manager允许客户从用户界面(全球所有地理区域或针对特定国家/地区)启用IP模糊处理。启用此设置后，将在将IP地址收录到Audience Manager时立即放弃IP地址的最后一个字节(最后一部分)。Audience Manager会在处理之前放弃IP地址的此部分(包括在任何可选地理位置查找或记录IP地址之前)。例如：

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

IP地址模糊处理仅可用于Audience Manager管理员帐户。See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> 由于Audience Manager处理的大量数据，从您更新设置之日起，IP模糊处理更改可能需要长达个小时才能生效。

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

请按照以下步骤配置IP地址模糊处理。

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. 选择要使用的IP模糊处理类型。
   1. **模糊处理所有IP地址：** 选择此选项可让Audience Manager模糊化所有访客IP地址的最后八位字节，而不管其来源所在的区域。
   2. **为特定国家/地区模糊化IP地址：** 选择此选项可让Audience Manager模糊化特定国家/地区的访客IP地址的最后八位字节。Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you&#39;ve added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you&#39;re done.

## 相关概念 {#related-concepts}

* [数据隐私](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP地址模糊处理视频演示
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=chi_hans)

