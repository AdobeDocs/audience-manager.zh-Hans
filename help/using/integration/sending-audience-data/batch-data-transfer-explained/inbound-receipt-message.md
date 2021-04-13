---
description: 每当处理入站服务器到服务器文件时，都会通过电子邮件将收据发送给合作伙伴解决方案，如果配置了，还会发送给合作伙伴。
seo-description: 每当处理入站服务器到服务器文件时，都会通过电子邮件将收据发送给合作伙伴解决方案，如果配置了，还会发送给合作伙伴。
seo-title: 入站处理后发送给合作伙伴的示例消息
solution: Audience Manager
title: 入站处理后发送给合作伙伴的示例消息
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: 入站数据传输
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---

# 入站处理后发送给合作伙伴的示例消息{#sample-message-to-partners-after-inbound-processing}

每当处理入站[!UICONTROL Server-to-Server]文件时，都会通过电子邮件将收据发送给合作伙伴解决方案，如果配置了，还会发送给合作伙伴。

<!-- r_inbound_message.xml -->

以下示例是电子邮件示例。 消息下面的表格描述了消息中的各行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>发件人：aam-noreply@adobe.com  </b> </p> <p> <b>主题：Adobe Audience Manager服务器到服务器处理结果：</b> </p> <p> <b>尊敬的Adobe合作伙伴：(ID:7)</b> <b></b> </p> <p> <b>我们已收到您的Adobe Audience Manager服务器到服务器文件投放</b> </p> <p> <b>文件名：</b> <i></i> </p> <p> <b> s3n://&lt;&gt; bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt; bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt; bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt; bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt; bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt; bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt; bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>收到的记录：40669900</b> </p> <p><b>格式错误：0</b> </p> <p> <b>无效的AAM ID:112  </b> </p> <p> <b>没有匹配的AAM ID:0  </b> </p> <p> <b>未实现任何特征：26730823  </b> </p> <p> <b>已处理记录：40669900  </b> </p> <p> <b>存储记录：13938958  </b> </p> <p> <b>设备总数：21  </b> </p> <p> <b>总信号：918878926  </b> </p> <p> <b>未使用信号总数：660348376  </b> </p> <p> <b>已实现特征总数：258086908  </b> </p> <p> <b>删除的特征总数：0  </b> </p> <p> <b>总特征未通过验证：0  </b> </p> <p> <b>具有未通过验证的特征的用户总数：0  </b> </p> <p> <b>作业开始时间：2018-05-17 18:07:49  </b> </p> <p> <b>作业结束时间：2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含与收到的电子邮件中的行相对应的行。

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 折线图 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 文件名 </td> 
   <td colname="col2"> <p>列表Adobe为此合作伙伴接收的所有已一起处理的入站文件。 在前面的示例电子邮件中，合作伙伴ID为7，数据所有者ID为901。 </p> <p>尾部编号(1,2,3...)是客户或入站分销商添加的拆分编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已收到记录 </td> 
   <td colname="col2"> <p>所有文件中收到的记录Adobe总数。 在大多数情况下，这应为入站文件中的行总数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式错误 </td> 
   <td colname="col2"> <p>与预期格式不匹配的行数。 入站作业无法识别这些行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 无效的AAM ID </td> 
   <td colname="col2"> <p>与预期的38位格式不匹配的Audience ManagerUUID的数量。 或者，文件中发送的Audience ManagerUUID不是数字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 无匹配的AAM ID </td> 
   <td colname="col2"> <p>Audience Manager找不到匹配UUID的用户总数。 这些文件尚未同步ID，因此Audience Manager无法查找UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未实现任何特征 </td> 
   <td colname="col2"> <p>行上没有信号映射到Audience Manager特征的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已处理记录 </td> 
   <td colname="col2"> <p>处理的记录Audience Manager总数。 在大多数情况下，此数字应与“已接收记录”相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 存储记录 </td> 
   <td colname="col2"> <p>生成要加载到系统中的数据的记录数=已处理记录 — 格式错误 — 无效AAM ID — 无匹配AAM ID — 无实现特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 设备总数 </td> 
   <td colname="col2"> <p>数据加载到系统中的设备数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 总信号 </td> 
   <td colname="col2"> <p> 所有入站文件中所有用户的信号总数（所处理记录中的键/值对总数）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用信号总数 </td> 
   <td colname="col2"> <p>所有入站文件(未映射到Audience Manager特征的键/值对)中所有用户的未使用信号的总数。 在大多数情况下，这意味着Audience Manager没有为信号定义规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已实现特征总数 </td> 
   <td colname="col2"> <p>所有入站文件中所有用户基于信号的Audience Manager特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 删除的特征总数 </td> 
   <td colname="col2"> <p> 所有入站文件中所有用户删除的特征总数。 对于完全同步，如果用户在上一次运行中具有该特征，但在当前运行中没有该特征，则会发生这种情况。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 总特征未通过验证 </td> 
   <td colname="col2"> <p>表示不属于在文件名中声明的数据源的特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有未通过验证的特征的用户总数 </td> 
   <td colname="col2"> <p>具有未通过验证的特征的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作业开始时间 </td> 
   <td colname="col2"> <p>入站作业开始的时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作业结束时间 </td> 
   <td colname="col2"> <p>入站作业结束的时间。 </p> </td> 
  </tr> 
 </tbody> 
</table>
