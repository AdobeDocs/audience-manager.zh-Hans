---
description: 用于让DIL知道它会在窗口加载后加载。
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>自2023年7月起，Adobe已停止开发新能源。 [!DNL Data Integration Library (DIL)] 和 [!DNL DIL] 扩展。
>
>现有客户可继续使用其 [!DNL DIL] 实现。 但是，Adobe将不会开发 [!DNL DIL] 超越这一步。 我们鼓励客户对 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 长期数据收集策略。
>
>如果客户希望在2023年7月之后实施新的数据收集集成，则应使用 [Experience PlatformWeb SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 而是。

用于让DIL知道它会在窗口加载后加载。

**函数签名：** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## 示例代码

```
DIL.isAddedPostWindowLoad();
```
