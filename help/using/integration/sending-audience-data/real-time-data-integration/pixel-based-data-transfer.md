---
description: 简单像素(可用于确定特征的用户)执行实时数据传输。Audience Manager界面允许客户端基于自助服务创建任意数量的像素。像素字符串由简单的ID或键值对组成。
seo-description: 简单像素(可用于确定特征的用户)执行实时数据传输。Audience Manager界面允许客户端基于自助服务创建任意数量的像素。像素字符串由简单的ID或键值对组成。
seo-title: 基于像素的数据传输
solution: Audience Manager
title: 基于像素的数据传输
uuid: 8773bfc0-6b8d-4a6a6b7b7-e043744486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixel-based Data Transfers {#pixel-based-data-transfers}

简单像素(可用于确定特征的用户)执行实时数据传输。Audience Manager界面允许客户端基于自助服务创建任意数量的像素。像素字符串由简单的ID或键值对组成。

<!-- c_rt_inbound_pixel_transfers.xml -->

要启用入站数据传输，供应商和客户端将：

1. 确定您希望供应商或合作伙伴开火的特征。
1. 获取特征的像素。In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait.
1. Provide the [!DNL URL] to the vendor or partner.

## 示例

This basic event call sends trait ID 1234 to [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

You can serialize trait IDs in an event call to help reduce `HTTP` traffic from the page. 将其他特征ID追加到URL字符串，如以下示例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
