---
description: 此报表返回在清单中收集并发送到Audience Manager的所有未使用信息的频率计数。
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: 未使用的信号报表
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# 未使用的信号报表{#unused-signals-report}

此报表返回在清单中收集并发送到Audience Manager的所有未使用信息的频率计数。 要访问此报表，请导航至&#x200B;**Analytics >受众报表>其他报表>未使用的信号**。

>[!NOTE]
>
>如果您看到消息“您无权访问Audience报表”，请联系您的Audience Manager顾问或客户关怀团队为您配置报表。

![未使用的信号报表屏幕截图](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

信号是来自您网站的信息，以[键值对](../../reference/key-value-pairs-explained.md) （例如`color=blue, price>100, gender=female`等）的形式传递到[!DNL Audience Manager]。

未使用的信号由您收集但尚未映射到某个特征的数据组成。 [!UICONTROL Unused Signals]报表按日期、键、值和频率计数显示表中的数据。 任何传入到[!DNL Audience Manager]的未映射信号在一天内至少100次符合[!UICONTROL Unused Signals]报表的条件。

未使用的信号会存储45天然后被丢弃。 未使用的信号报表显示过去10天的数据。

查看此报表，以帮助识别可映射到新特征或现有特征的孤立信号。

>[!NOTE]
>
>在搜索字段中指定键或值名称，以将结果限制为特定记录。

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
   <td colname="col2"> <p>查看报告以说明特定信号的不同值变化。 </p> <p>例如，假设您在键值对中定义了“北卡罗来纳”州的特征，即<code> c_state = North Carolina</code>。 该报表可帮助您查找名称变体并将这些变体添加到特征中（例如，<code> c_state = North Carolina, NC, N.C., NCarolina</code>）。 或者，您可以使用报告发现名称变体，并使用所有网站上的统一值替换这些变体。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>创建新特征</b> </p> </td> 
   <td colname="col2"> <p>查看报告以了解在特定键上传递了哪些新值。 您可能需要根据这些新值创建新的键值对。 </p> <p> <p>注意：请每两周检查一次报表中是否有频繁更改的值（例如，节目、促销活动、名人等）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>查找未映射的值</b> </p> </td> 
   <td colname="col2"> <p>查看数字1的报告。 <span class="wintitle">未使用的信号</span>报表中的数字1表示空值。 这不一定是坏事。 它只是表示特定键没有关联的值映射。 当您看到重要变量的1个值很多时，请与您的网站团队确认，以确保您的所有页面都已正确标记。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳实践

运行并检查[!UICONTROL Unused Signals]报告：

* 在创建特征或更新特征规则之后。 这有助于确保正确设置您的特征和规则。 结果中的数字1表示新特征可能未正确配置。
* 每两周或每月。 计划的查看有助于确保特征映射为最新。

>[!NOTE]
>
>在报告中搜索未使用的值时，请考虑以下特殊性。 以下两个示例在表达式上存在差异：

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a！=23))
* 两个示例都显示了一个特征，该特征包含两个键值对v和a。第一个表达式将转换为：特征包含值为1 [!UICONTROL AND NOT]的键v和值为23的键a。 第二个表达式包含值为1 [!UICONTROL AND]的键v和值为[!UICONTROL NOT EQUAL] 23的键a。
* 考虑到上述两种不同的表达式，假设您在[!UICONTROL Unused Signals Report]中搜索传递给key a的值，无论其值是否为23，您只能在第一种情况下获得结果，因为key的值根本未发送。 在第二种情况下，发送了不同于23的值，因此键a未使用。

## 批量特征创建

如果您需要根据从[!UICONTROL Unused Signals]报表中获取的数据批量创建大量特征，请联系您的合作伙伴解决方案代表。
