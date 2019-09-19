---
description: 简单像素（可用于确定用户的特征）执行实时数据传输。 Audience manager界面允许客户自助创建任意数量的像素。 像素字符串由简单ID或键值对组成。
seo-description: 简单像素（可用于确定用户的特征）执行实时数据传输。 Audience manager界面允许客户自助创建任意数量的像素。 像素字符串由简单ID或键值对组成。
seo-title: 基于像素的数据传输
solution: Audience Manager
title: 基于像素的数据传输
uuid: 8773bfc0-6b8d-4a6a-a8b7-e04374486ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# 基于像素的数据传输 {#pixel-based-data-transfers}

简单像素（可用于确定用户的特征）执行实时数据传输。 Audience manager界面允许客户自助创建任意数量的像素。 像素字符串由简单ID或键值对组成。

<!-- c_rt_inbound_pixel_transfers.xml -->

要启用入站数据传输，供应商和客户端将：

1. 确定您希望供应商或合作伙伴触发哪些特征。
1. 获取特征的像素。 在特征列表屏幕中，将指针悬停在列 **[!UICONTROL Actions]** 上并单击所 **[!UICONTROL Get trait URL]** 需特征的符号。
1. 向供应 [!DNL URL] 商或合作伙伴提供。

## 示例

此基本事件调用将特征ID 1234发送到 [!DNL Audience Manager]。

```
https://something.demdex.net/event?d_sid=1234
```

您可以在事件调用中序列化特征ID，以帮助 `HTTP` 减少页面流量。 在URL字符串中附加其他特征ID，如下例所示：

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
