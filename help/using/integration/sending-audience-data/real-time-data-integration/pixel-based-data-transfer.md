---
description: 简单像素（可用于限定用户具有特征）执行实时数据传输。 Audience Manager界面允许客户端在自助的基础上创建任意数量的像素。 像素字符串由简单ID或键值对组成。
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: 基于像素的数据传输
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# 基于像素的数据传输 {#pixel-based-data-transfers}

简单像素（可用于限定用户具有特征）执行实时数据传输。 Audience Manager界面允许客户端在自助的基础上创建任意数量的像素。 像素字符串由简单ID或键值对组成。

<!-- c_rt_inbound_pixel_transfers.xml -->

要启用入站数据传输，供应商和客户应：

1. 确定您希望供应商或合作伙伴触发哪些特征。
1. 获取特征的像素。 在特征列表屏幕中，将鼠标悬停在&#x200B;**[!UICONTROL Actions]**&#x200B;列上，然后单击所需特征的&#x200B;**[!UICONTROL Get trait URL]**&#x200B;符号。
1. 将[!DNL URL]提供给供应商或合作伙伴。

## 示例

此基本事件调用将特征ID 1234发送到[!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件调用中序列化特征ID，以帮助减少来自页面的`HTTP`流量。 将其他特征ID附加到URL字符串，如以下示例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
