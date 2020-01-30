---
description: 本页包括向Audience Manager客户关怀部门报告的热点问题。
seo-description: 本页包括向Audience Manager客户关怀部门报告的热点问题。
seo-title: 客户关怀——最常报告的问题
solution: Audience Manager
title: 客户关怀——最常报告的问题
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# 客户关怀——最常报告的问题{#most-frequent-issues}

本页包括2019年向Audience Manager客户关怀部门报告的热点问题。

## 为什么我们的只读用户能够创建、编辑或删除特征和区段？

**问题**

为什么我们的只读用户能够创建、编辑或删除特征和区段？

**回答**

除了在管理部分创建组和权限之外，您还需要联系客户关怀(amsupport@adobe.com)，以便代表可以为您的帐户启用基于角色的访问控制(RBAC)。

<br> 

## 为什么我的Onhocted特质群体在10月15日前后降至0? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

在2019年10月14日前后，我注意到我在设备ID图表上载入的特质群体已降至0，而之前这个数量要高得多。

![设备ID放置的图像](/help/using/support-issues/assets/device_id_populationdrop.png)

**回答**

10月15日，对Audience manager的“配置文件合并规则”功能的更新更改为，不再针对设备ID实现从上传到跨设备数据源的CRM ID中键入的已载入数据。  以前，Audience Manager是根据跨设备ID（或CRM ID）实现的，也是将这些实现复制到关联的Audience Manager UUID（设备ID）。  进行了更改，以更准确地反映特征数据的性质和正在实现的档案。

要查看特征实现，请从“特征”视图右上角的下拉菜单中选择“跨设备ID”选项。

![按跨设备ID查看实现](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## 为什么我的特征或区段不显示在“重叠报告”页面中？

为何特征和区段可能未显示在“重叠报告”页面中的说明。

**问题**

在尝试运行重叠报告时，为什么用户看不到重叠报告页面中列出的某些特征和区段？

**回答**

要在重叠报告中列出某个特征或区段，需要满足最低的唯一访客要求。


* 对于特征：超过14天
* 对于区段：70000个14天内的实时用户

有关此功能的更多详细信息，请参阅选定Audience Manager报 [告中的页面数据采样和错误率](/help/using/reporting/report-sampling.md)。