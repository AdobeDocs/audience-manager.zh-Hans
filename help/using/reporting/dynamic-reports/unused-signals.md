---
description: 此报表返回在您的库存中收集并发送给Audience Manager的所有未使用信息的频率计数。
seo-description: 此报表返回在您的库存中收集并发送给Audience Manager的所有未使用信息的频率计数。
seo-title: 未使用的信号报表
solution: Audience Manager
title: 未使用的信号报表
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: 重叠报表
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 2%

---

# 未使用的信号报表{#unused-signals-report}

此报表返回在您的库存中收集并发送给Audience Manager的所有未使用信息的频率计数。 要访问此报告，请导航到&#x200B;**分析>受众报告>其他报告>未使用信号**。

>[!NOTE]
>
>如果您看到消息“您无权访问受众报表”，请与您的Audience Manager顾问或客户关怀部门联系，为您准备报表。

![未使用信号报告的屏幕截图](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

信号是来自您网站以[键值对](../../reference/key-value-pairs-explained.md)（例如`color=blue, price>100, gender=female`等）形式传递到[!DNL Audience Manager]的信息。

未使用的信号由您收集但尚未映射到特征的数据组成。 [!UICONTROL Unused Signals]报表按日期、键值、值和频率计数显示表中的数据。 任何未映射的信号在一天中至少传入[!DNL Audience Manager]100次，符合[!UICONTROL Unused Signals]报告的条件。

查看此报告以帮助识别可映射到新特征或现有特征的孤立信号。

>[!NOTE]
>
>在搜索字段中指定键名或值名称，以将结果限制为特定记录。

## 用例

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 示例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>确保特征一致性或向单个键添加相关值</b> </p> </td> 
   <td colname="col2"> <p>查看报告，了解特定信号的不同值变化。 </p> <p>例如，假设您具有在键值对中定义为<code> c_state = North Carolina</code>的状态“North Carolina”的特征。 该报表可帮助您查找名称变体并将其添加到特征（例如<code> c_state = North Carolina, NC, N.C., NCarolina</code>）。 或者，您也可以使用报表找到名称变体，并将所有站点中的名称变体替换为统一值。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>创建新特征</b> </p> </td> 
   <td colname="col2"> <p>查看报告，了解在特定密钥上传入的新值。 您可能希望根据这些新值创建新键值对。 </p> <p> <p>注意： 查看报告，了解频繁更改的值(例如，节目、活动、名人等)。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>查找未映射的值</b> </p> </td> 
   <td colname="col2"> <p>查看数字1的报告。 <span class="wintitle">未使用信号</span>报表中的数字1表示空值。 这未必是坏的。 它只是意味着特定键没有关联的值映射。 当您看到重要变量的大量1个值时，请咨询您的网站团队，以确保所有页面均已正确标记。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳实践

运行并检查[!UICONTROL Unused Signals]报告：

* 创建特征或更新特征规则后。 这有助于确保正确设置您的特征和规则。 结果中的数字1表示可能未正确配置新特征。
* 每周或每月两次。 计划的审阅有助于确保特征映射是最新的。

>[!NOTE]
>
>在报表中搜索未使用的值时，请考虑以下特殊性。 以下两个示例的表达式有所不同：

* T(v=1 [!UICONTROL AND NOT](a=23))
* T(v=1 [!UICONTROL AND](a!=23))
* 两个示例都显示一个特征，它包含两个键值对v和a。第一个表达式是：特征包含键v，键v的值为1 [!UICONTROL AND NOT]，键a的值为23。 第二个表达式包含键v，键v的值为1 [!UICONTROL AND]，键a的值为[!UICONTROL NOT EQUAL] 23。
* 考虑到上述两个不同的表达式，假设您在[!UICONTROL Unused Signals Report]中搜索键a上传递的值，其中任何值都不同于23，因此您只会在第一种情况下获得结果，因为键的值未发送AT ALL。 在第二种情况下，发送的值不同于23，因此键a不是未使用的。

## 批量特征创建

如果您需要根据从[!UICONTROL Unused Signals]报表获取的数据批量创建大量特征，请与您的合作伙伴解决方案代表联系。
