---
description: 每当处理入站服务器到服务器文件时，都会通过电子邮件将接收情况发送给合作伙伴解决方案，如果已配置，还会发送给合作伙伴。
seo-description: Whenever an inbound Server-to-Server file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.
seo-title: Sample Message to Partners after Inbound Processing
solution: Audience Manager
title: 入站处理后发送给合作伙伴的示例消息
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# 入站处理后发送给合作伙伴的示例消息{#sample-message-to-partners-after-inbound-processing}

每当处理入站[!UICONTROL Server-to-Server]文件时，都会通过电子邮件将接收信息发送给合作伙伴解决方案，如果已配置，还会发送给合作伙伴。

<!-- r_inbound_message.xml -->

以下示例是一封示例电子邮件。 消息下面的表格描述了消息中的各个行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>发件人： aam-noreply@adobe.com </b> </p> <p> <b>主题： Adobe Audience Manager服务器到服务器处理结果：</b> </p> <p> <b>尊敬的Adobe合作伙伴： (ID：7)</b> <b></b> </p> <p> <b>我们已收到您的Adobe Audience Manager服务器到服务器文件投放</b> </p> <p> <b>文件名：</b> <i></i> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3n://&lt;<i>bucket_name&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3n://&lt;<i>bucket_name&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>已接收的记录： 40669900</b> </p> <p><b>格式错误： 0</b> </p> <p> <b>无效的AAM ID： 112 </b> </p> <p> <b>没有匹配的AAM ID： 0 </b> </p> <p> <b>未实现特征： 26730823 </b> </p> <p> 已处理<b>条记录： 40669900 </b> </p> <p> <b>存储的记录： 13938958 </b> </p> <p> <b>设备总数： 21 </b> </p> <p> <b>总信号数： 918878926 </b> </p> <p> <b>未使用的信号总数： 660348376 </b> </p> <p> <b>已实现特征总数： 258086908 </b> </p> <p> <b>删除的特征总数： 0 </b> </p> <p> <b>验证失败的特征总数： 0 </b> </p> <p> <b>具有验证失败的特征的用户总数： 0 </b> </p> <p> <b>作业开始时间： 2018-05-17 18:07:49 </b> </p> <p> <b>作业结束时间： 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含与接收的电子邮件中的行对应的行。

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
   <td colname="col2"> <p>Adobe为此合作伙伴收到的、一起处理的所有入站文件的列表。 在上一个示例电子邮件中，合作伙伴ID为7，数据所有者ID为901。 </p> <p>尾编号(1,2，3...)是客户或入站分销商添加的分解编号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已接收的记录 </td> 
   <td colname="col2"> <p>在所有文件中Adobe接收的记录总数。 在大多数情况下，这应该是集客文件中的总行数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式错误 </td> 
   <td colname="col2"> <p>不符合预期格式的行数。 集客作业无法识别这些行。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AAM ID无效 </td> 
   <td colname="col2"> <p>与预期的38位数格式不匹配的Audience ManagerUUID数。 或者文件中发送的Audience ManagerUUID不是数字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 没有匹配的AAM ID </td> 
   <td colname="col2"> <p>Audience Manager未能找到匹配UUID的用户总数。 这些文件尚未进行ID同步，因此Audience Manager无法查找UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未实现特征 </td> 
   <td colname="col2"> <p>行上没有任何信号映射到Audience Manager特征的记录数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已处理的记录 </td> 
   <td colname="col2"> <p>Audience Manager处理的记录总数。 在大多数情况下，此数字应与“收到的记录数”相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 存储的记录 </td> 
   <td colname="col2"> <p>导致数据加载到系统中的记录数=处理的记录数 — 格式错误 — 无效的AAM ID — 没有匹配的AAM ID — 未实现特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 设备总数 </td> 
   <td colname="col2"> <p>将数据加载到系统中的设备数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 信号总数 </td> 
   <td colname="col2"> <p> 所有入站文件中所有用户的信号总数（处理的记录中的键/值对总数）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用的信号总数 </td> 
   <td colname="col2"> <p>所有入站文件(未映射到Audience Manager特征的键/值对)中所有用户的未使用信号总数。 在大多数情况下，这意味着Audience Manager没有为信号定义规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已实现特征总数 </td> 
   <td colname="col2"> <p>所有入站文件中所有用户基于信号的Audience Manager特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 删除的特征总数 </td> 
   <td colname="col2"> <p> 所有入站文件中所有用户的已删除特征总数。 对于完全同步，如果用户在上一次运行中具有特征，但在当前运行中没有特征，则会发生这种情况。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 验证失败的特征总数 </td> 
   <td colname="col2"> <p>表示不属于在文件名中声明的数据源的特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有验证失败的特征的用户总数 </td> 
   <td colname="col2"> <p>具有验证失败的特性的记录数。 </p> </td> 
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
