---
description: 此报告会返回在库存中收集并发送到Audience Manager的所有未使用信息的频率计数。
seo-description: 此报告会返回在库存中收集并发送到Audience Manager的所有未使用信息的频率计数。
seo-title: 未使用的信号报告
solution: Audience Manager
title: 未使用的信号报告
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
translation-type: tm+mt
source-git-commit: dcc44161df89b44ca1a234070c4afbb0210dc723

---


# 未使用的信号报告{#unused-signals-report}

此报告会返回在库存中收集并发送到Audience Manager的所有未使用信息的频率计数。 要访问此报告，请导航到“ **分析”>“受众报告”>“其他报告”>“未使用的信号”**。

>[!NOTE]
>
>如果看到消息“您无权访问受众报告”，请与Audience manager顾问或客户关怀联系，为您提供报告。

![未使用信号报告的屏幕截图](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 概述

信号是以键值对(例如， [!DNL Audience Manager] 等)形式从您的 [网站传递到的](../../reference/key-value-pairs-explained.md)`color=blue, price>100, gender=female`信息。

未使用的信号由您收集但尚未映射到某个特征的数据组成。 该报 [!UICONTROL Unused Signals] 告按日期、键值、值和频率计数显示表中的数据。 任何未映射的信号 [!DNL Audience Manager] 在一天内至少传入100次，都符合报告的 [!UICONTROL Unused Signals] 条件。

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
   <td colname="col1"> <p><b>确保特征一致性或向单键添加相关值</b> </p> </td> 
   <td colname="col2"> <p>查看报告，了解特定信号的不同值变化。 </p> <p>例如，假设您有一个州“North Carolina”的特征，该特征在键值对中定义为 <code> c_state = North Carolina</code>。 该报告可以帮助您查找名称变体并将其添加到特征(例如 <code> c_state = North Carolina, NC, N.C., NCarolina</code>)。 或者，您也可以使用报告发现名称变体，并在所有站点上用统一的值替换这些变体。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>创建新特征</b> </p> </td> 
   <td colname="col2"> <p>查看报告，查看在特定键上传递的新值。 您可能希望基于这些新值创建新键值对。 </p> <p> <p>注意： 查看报告，了解经常更改的值（例如节目、营销活动、名人等）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>查找未映射的值</b> </p> </td> 
   <td colname="col2"> <p>查看数字1的报告。 “未使用的信号”报 <span class="wintitle"> 告中的数字</span> 1表示空值。 这未必是坏事。 它只是表示特定键没有关联的值映射。 当您看到重要变量的大量值为1时，请咨询您的站点团队，确保正确标记所有页面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳实践

运行并检查报 [!UICONTROL Unused Signals] 告：

* 创建特征或更新特征规则后。 这有助于确保正确设置您的特征和规则。 结果中的数字1表示可能未正确配置新特征。
* 每周两次或每月一次。 计划的审阅有助于确保特征映射是最新的。

>[!NOTE]
>
>在报告中搜索未使用的值时，请考虑以下特殊性。 以下两个示例在表达式上有所不同：

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* 两个示例都显示一个特征，该特征包含两个键值对v和a。第一个表达式转换为：特征包含键v（值1）和键a( [!UICONTROL AND NOT] 值23)。 第二个表达式包含键v（值1）和键a( [!UICONTROL AND] 值23)，键v( [!UICONTROL NOT EQUAL] 值1)。
* 考虑到上述两个不同的表达式，假设您在中搜索键a上传递的值，其任何值都不同于23，因此您只会在第一种情况下获得结果，因为键的值未发送为AT ALL。 [!UICONTROL Unused Signals Report] 在第二种情况下，不同于23的值被发送，因此键a不是未使用的。

## 批量特征创建

如果需要根据从报告中获取的数据批量创建大量特征，请与合作伙伴解决方案代表联 [!UICONTROL Unused Signals] 系。
