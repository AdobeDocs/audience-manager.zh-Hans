---
description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP地址模糊处理
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 12%

---

# IP地址模糊处理 {#ip-obfuscation}

使用此功能对Audience Manager中收集的IP地址进行模糊处理。

## 概述和方法 {#overview-and-methodology}

由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。

### IP模糊处理方法

按照“通过设计保护隐私”的原则，Adobe Audience Manager允许客户在UI中启用IP模糊处理，范围可以是全球所有地区，也可以是特定国家/地区。 启用此设置后，将IP地址摄取到Audience Manager中后，将立即丢弃IP地址的最后八位字节（最后一部分）。 在处理之前（包括选择对IP地址进行任何地理位置查找或记录之前），Audience Manager会丢弃IP地址的这个部分。 例如：

* 模糊处理前： `255.255.255.255`
* 模糊处理之后： `255.255.255.0`

另请参阅[数据隐私部分](/help/using/overview/data-security-and-privacy/data-privacy.md)中的收集IP地址和IP地址模糊处理。

### IP模糊处理优先级 {#precedence}

[数据流级别的IP模糊处理](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#create)优先于Audience Manager中设置的任何IP模糊处理选项，并将其应用于所有IP地址。 Audience Manager执行的任何地理位置查找都受数据流级别[!UICONTROL IP obfuscation]选项的影响。 基于完全模糊处理的IP的Audience Manager中的地理位置查找将生成未知区域，并且任何基于所生成地理位置数据的区段都不会实现。

## IP地址模糊处理要求 {#ip-obfuscation-requirements}

IP地址模糊处理仅适用于Audience Manager管理员帐户。 请参阅[创建用户](/help/using/features/administration/administration-overview.md#create-users)，了解如何为用户分配管理员权限。

>[!NOTE]
>
> 由于Audience Manager处理的数据量很大，IP模糊处理更改可能从更新设置的那一刻起需要4小时才能生效。

## 配置IP地址模糊处理 {#configure-ip-obfuscation}

请按照以下步骤配置IP地址模糊处理。

1. 使用管理员帐户登录Audience Manager，然后转到&#x200B;**管理>隐私**。
2. 选择要使用的IP模糊处理类型。
   1. **混淆所有IP地址：**&#x200B;选择此选项可使Audience Manager混淆所有访客IP地址的最后八位字节，而不管它们来自哪个区域。
   2. **模糊处理特定国家/地区的IP地址：**&#x200B;选择此选项可使Audience Manager模糊处理特定国家/地区的最后八位访客IP地址。 使用&#x200B;**国家/地区列表**&#x200B;或相应的&#x200B;**搜索**&#x200B;字段查找要为其启用IP模糊处理的国家/地区，然后单击+图标以将其添加到&#x200B;**选定进行模糊处理**&#x200B;列表中。 将所有必需的国家添加到&#x200B;**选定进行模糊处理**&#x200B;列表后，单击&#x200B;**保存**。

![](assets/ip-obfuscation.png)

## 禁用IP地址模糊处理 {#disable-ip-obfuscation}

要全局禁用IP地址模糊处理，请转到&#x200B;**管理>隐私**，选择&#x200B;**不模糊处理IP地址**，然后单击&#x200B;**保存**。

要禁用特定国家/地区的IP地址模糊处理，请在&#x200B;**选择进行模糊处理**&#x200B;列表中查找国家/地区，然后单击其对应的&#x200B;**X**&#x200B;图标。 完成后，单击&#x200B;**保存**。

## 相关概念 {#related-concepts}

* [数据隐私](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP地址模糊处理视频演示
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
