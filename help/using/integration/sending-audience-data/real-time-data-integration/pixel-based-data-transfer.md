---
description: 简单像素（可用于确定用户的特征）执行实时数据传输。 Audience Manager界面允许客户自助创建任意数量的像素。 像素字符串由简单ID或键值对组成。
seo-description: 简单像素（可用于确定用户的特征）执行实时数据传输。 Audience Manager界面允许客户自助创建任意数量的像素。 像素字符串由简单ID或键值对组成。
seo-title: 基于像素的数据传输
solution: Audience Manager
title: 基于像素的数据传输
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 4%

---


# 基于像素的数据传输 {#pixel-based-data-transfers}

简单像素（可用于确定用户的特征）执行实时数据传输。 Audience Manager界面允许客户自助创建任意数量的像素。 像素字符串由简单ID或键值对组成。

<!-- c_rt_inbound_pixel_transfers.xml -->

要启用入站数据传输，供应商和客户端将：

1. 确定您希望供应商或合作伙伴触发哪些特征。
1. 获取特征的像素。 在特征列表屏幕中，将指针悬停在&#x200B;**[!UICONTROL Actions]**&#x200B;列上，然后单击所需特征的&#x200B;**[!UICONTROL Get trait URL]**&#x200B;符号。
1. 向供应商或合作伙伴提供[!DNL URL]。

## 示例

此基本事件调用将特征ID 1234发送到[!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件调用中序列化特征ID，以帮助减少页面的`HTTP`流量。 在URL字符串中附加其他特征ID，如下例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
