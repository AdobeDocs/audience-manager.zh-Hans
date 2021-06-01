---
description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
seo-description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
solution: Audience Manager
title: IP 地址模糊处理
feature: 数据管理和隐私
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# IP 地址模糊处理 {#ip-obfuscation}

使用此功能可模糊处理在Audience Manager中收集的IP地址。

## 概述和方法{#overview-and-methodology}

由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。

### IP模糊处理方法

遵循“通过设计保护隐私”的原则，Adobe Audience Manager允许客户从UI中启用IP模糊处理，范围可以是全球所有地区，还是特定国家/地区。 启用此设置后，当将IP地址摄取到Audience Manager中时，将立即丢弃IP地址的最后八位字节（最后一部分）。 Audience Manager在处理之前（包括在选择对IP地址进行任何地理查找或记录之前），会先丢弃IP地址的这一部分。 例如：

* 在模糊处理之前：`255.255.255.255`
* 模糊处理后：`255.255.255.0`

另请参阅[数据隐私部分](/help/using/overview/data-security-and-privacy/data-privacy.md)中的收集IP地址和IP地址模糊处理。

## IP地址模糊处理要求{#ip-obfuscation-requirements}

IP地址模糊处理仅适用于Audience Manager管理员帐户。 请参阅[创建用户](/help/using/features/administration/administration-overview.md#create-users)以了解如何为用户分配管理员权限。

>[!NOTE]
>
> 由于由Audience Manager处理的数据量很大，因此IP模糊处理更改可能需要长达4小时才能生效，从您更新设置之时起便开始生效。

## 配置IP地址模糊处理{#configure-ip-obfuscation}

请按照以下步骤配置IP地址模糊处理。

1. 使用管理员帐户登录Audience Manager，然后转到&#x200B;**管理>隐私**。
2. 选择要使用的IP模糊处理类型。
   1. **模糊处理所有IP地址：** 选择此选项可让Audience Manager模糊处理所有访客IP地址的最后八位字节，而不考虑它们源自的区域。
   2. **模糊处理特定国家/地区的IP地址：** 选择此选项可让Audience Manager模糊处理特定国家/地区的访客IP地址的最后八位字节。使用&#x200B;**国家/地区列表**&#x200B;或相应的&#x200B;**搜索**&#x200B;字段查找国家/地区以启用IP模糊处理，然后单击+图标以将它们添加到&#x200B;**选定进行模糊处理**&#x200B;列表。 将所有必需的国家/地区添加到&#x200B;**选定进行模糊处理**&#x200B;列表后，单击&#x200B;**保存**。

![](assets/ip-obfuscation.png)

## 禁用IP地址模糊处理{#disable-ip-obfuscation}

要全局禁用IP地址模糊处理，请转到&#x200B;**管理>隐私**，选择&#x200B;**不对IP地址进行模糊处理**，然后单击&#x200B;**保存**。

要禁用特定国家/地区的IP地址模糊处理，请在&#x200B;**为模糊处理选择的**&#x200B;列表中找到相应的国家/地区，然后单击相应的&#x200B;**X**&#x200B;图标。 完成后，单击&#x200B;**Save**。

## 相关概念 {#related-concepts}

* [数据隐私](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP地址模糊处理视频演示
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
