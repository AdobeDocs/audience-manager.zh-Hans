---
description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
seo-description: 由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。
solution: Audience Manager
title: IP 地址模糊处理
feature: 数据治理和隐私
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# IP 地址模糊处理 {#ip-obfuscation}

使用此功能可模糊化在Audience Manager中收集的IP地址。

## 概述和方法{#overview-and-methodology}

由于全球隐私法规，贵公司可能希望在许多国家/地区模糊处理 IP 地址。Audience Manager 允许您在全球范围或者根据具体国家或地区来模糊处理访客 IP 地址。

### IP模糊处理方法

遵循“以设计为隐私”的原则，Adobe Audience Manager允许客户从UI启用IP模糊处理，无论是在全球所有地理区域还是针对特定国家/地区。 启用此设置后，当将IP地址引入Audience Manager时，将立即放弃IP地址的最后八位字节（最后一部分）。 Audience Manager在处理之前（包括在任何可选的地理查找或IP地址记录之前）放弃这部分IP地址。 例如：

* 混淆前：`255.255.255.255`
* 混淆后：`255.255.255.0`

另请参阅[数据隐私部分](/help/using/overview/data-security-and-privacy/data-privacy.md)中的收集IP地址和IP地址模糊处理。

## IP地址混淆要求{#ip-obfuscation-requirements}

IP地址模糊处理仅适用于Audience Manager管理员帐户。 请参阅[创建用户](/help/using/features/administration/administration-overview.md#create-users)以了解如何为用户分配管理员权限。

>[!NOTE]
>
> 由于Audience Manager处理的数据量很大，从您更新设置开始，IP模糊处理更改可能需要多达4小时才能生效。

## 配置IP地址模糊处理{#configure-ip-obfuscation}

请按照以下步骤配置IP地址模糊处理。

1. 使用管理员帐户登录Audience Manager，然后转到&#x200B;**管理>隐私**。
2. 选择要使用的IP模糊处理类型。
   1. **模糊处理所有IP地址：** 选择此选项可让Audience Manager模糊处理所有访客IP地址的最后一个二进制八位数，而不管这些二进制八位数来自哪个区域。
   2. **模糊处理特定国家/地区的IP地** 址：选择此选项可让Audience Manager模糊处理特定国家/地区的访客IP地址的最后八位字节。使用“国家/地区”**列表**&#x200B;或相应的&#x200B;**搜索**&#x200B;字段查找国家/地区以启用其的IP模糊处理，然后单击+图标将其添加到“选择用于模糊处理&#x200B;**列表”。**&#x200B;将所有必需国家/地区添加到“已选择用于混淆&#x200B;**”列表后，单击“**&#x200B;保存&#x200B;**”。**

![](assets/ip-obfuscation.png)

## 禁用IP地址模糊处理{#disable-ip-obfuscation}

要全局禁用IP地址模糊处理，请转至&#x200B;**管理>隐私**，选择&#x200B;**不要模糊IP地址**，然后单击&#x200B;**保存**。

要禁用特定国家/地区的IP地址模糊处理，请在“**已选择用于模糊处理**”列表中查找国家/地区，然后单击相应的&#x200B;**X**&#x200B;图标。 完成后，单击&#x200B;**保存**。

## 相关概念 {#related-concepts}

* [数据隐私](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP地址模糊化视频演示
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
