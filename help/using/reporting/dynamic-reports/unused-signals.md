---
description: 此报告返回您的库存中收集的所有未使用信息的频率计数，并发送至Audience Manager。
seo-description: 此报告返回您的库存中收集的所有未使用信息的频率计数，并发送至Audience Manager。
seo-title: 未使用的信号报告
solution: Audience Manager
title: 未使用的信号报告
uuid: 04334a5c-3e21-44db-b971-0b4457685 e9 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Unused Signals Report{#unused-signals-report}

此报告返回您的库存中收集的所有未使用信息的频率计数，并发送至Audience Manager。

<!-- 

c_unused_signals.xml

 -->

## 未使用的信号报告

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

未使用的信号由您收集但尚未映射到特征的数据组成。[!UICONTROL Unused Signals] 报告按日期、键、值和频率计数显示表中的数据。Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

查看此报告可帮助识别可映射到新特征或现有特征的孤立信号。

>[!NOTE]
>
>在搜索字段中指定密钥或值名称，以将结果限制为特定记录。

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
   <td colname="col1"> <p><b>确保特征统一性或向单个密钥添加相关值</b> </p> </td> 
   <td colname="col2"> <p>查看报告以了解特定信号的不同值变量。 </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). 此外，您还可以使用报告发现名称变体，并替换所有站点中具有统一值的变量。 </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>创建新特征</b> </p> </td> 
   <td colname="col2"> <p>查看报告以查看在特定密钥上传递的新值。您可能希望根据这些新值创建新的键值对。 </p> <p> <p>注意：检查每周变化的值(例如，显示、营销活动、名人等)的报告两周。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>查找未映射的值</b> </p> </td> 
   <td colname="col2"> <p>查看数字的报告1。<span class="wintitle"> 未使用信号</span> 报告中的数字表示空值。这并不一定是坏事。这只是表示特定键没有关联的值映射。当您看到一个重要变量的多个值时，请咨询您的站点团队，确保正确标记您的所有页面。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 最佳实践

Run and check the [!UICONTROL Unused Signals] report:

* 创建特征或更新特征规则后。这有助于确保您的特征和规则设置得当。结果中的1表示新特征可能无法正确配置。
* 两周或每月。定时审阅有助于确保特征映射处于最新状态。

>[!NOTE]
>
>在报告中搜索未使用的值时，请考虑以下特殊性。以下两个示例之间存在差异：

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let's say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you'll only obtain results in the first case because values for key were not sent AT ALL. 在第二种情况下，发送的值不同于23，因此键不会取消使用。

## 批量特征创建

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
