---
description: 在2019年10月14日前后，我注意到我在设备ID图表上载入的特质群体已降至0，而之前这个数量要高得多。
seo-description: 在2019年10月14日前后，我注意到我在设备ID图表上载入的特质群体已降至0，而之前这个数量要高得多。
seo-title: 为什么我的Onhocted特质群体在10月15日前后降至0?
solution: Audience Manager
title: 为什么我的Onhocted特质群体在10月15日前后降至0?
translation-type: tm+mt
source-git-commit: eb129bbf642cb666ce3ea05ff606c051e02f4d1e

---


# 为什么我的Onhocted特质群体在10月15日前后降至0? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

在2019年10月14日前后，我注意到我在设备ID图表上载入的特质群体已降至0，而之前这个数量要高得多。

![设备ID放置的图像](/help/using/support-issues/assets/device_id_populationdrop.png)

**回答**

10月15日，对Audience manager的“配置文件合并规则”功能的更新更改为，不再针对设备ID实现从上传到跨设备数据源的CRM ID中键入的已载入数据。  以前，Audience Manager是根据跨设备ID（或CRM ID）实现的，也是将这些实现复制到关联的Audience Manager UUID（设备ID）。  进行了更改，以更准确地反映特征数据的性质和正在实现的档案。

要查看特征实现，请从“特征”视图右上角的下拉菜单中选择“跨设备ID”选项。

![按跨设备ID查看实现](/help/using/support-issues/assets/deviceid-crossdevice.png)

