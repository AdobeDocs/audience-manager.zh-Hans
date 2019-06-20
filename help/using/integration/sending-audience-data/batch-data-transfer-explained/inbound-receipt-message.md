---
description: 每当处理入站服务器到服务器文件时，收据将通过电子邮件发送到合作伙伴解决方案，如果已配置，则会发送给合作伙伴。
seo-description: 每当处理入站服务器到服务器文件时，收据将通过电子邮件发送到合作伙伴解决方案，如果已配置，则会发送给合作伙伴。
seo-title: 入站处理后向合作伙伴发送的示例消息
solution: Audience Manager
title: 入站处理后向合作伙伴发送的示例消息
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Sample Message to Partners after Inbound Processing{#sample-message-to-partners-after-inbound-processing}

Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.

<!-- r_inbound_message.xml -->

以下示例为示例电子邮件。消息下的表描述了消息中的各行。

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>发件人：aam-noreply@adobe.com </b> </p> <p> <b>主题：Adobe Audience Manager Server与服务器处理结果：</b> </p> <p> <b>尊敬的Adobe合作伙伴：(ID：7)</b><b></b> </p> <p> <b>我们已收到您的Adobe Audience Manager Server至服务器文件交付</b> </p> <p> <b>文件名：</b><i></i> </p> <p> <b> sn://&lt;<i>bucket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368806402. sync</b> </p> <p> <b> sn://&lt;<i>bucket_ name&gt;</i>/2018-05-16/ ftp_ dpm_7_901_13686525202. sync </b> </p> <p> <b>sn://&lt;<i>bucket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368784804. sync </b> </p> <p> <b>sn://&lt;<i>bucket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_136880640.sync </b> </p> <p> <b>sn://&lt;<i>bucket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368784802. sync </b> </p> <p> <b>sn://&lt;<i>bucket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368784803. sync </b> </p> <p> <b>sn://&lt;<i>bucket_ name&gt;</i>/2018-05-17/ ftp_ dpm_7_901_1368806404. sync</b> </p> <p> <b>收到的记录：40669900</b> </p> <p><b>格式错误：0</b> </p> <p> <b>无效AAM ID：112 </b> </p> <p> <b>不匹配AAM ID：0 </b> </p> <p> <b>未实现特征：26730823 </b> </p> <p> <b>已处理记录：40669900 </b> </p> <p> <b>存储的记录：13938958 </b> </p> <p> <b>设备总数：21 </b> </p> <p> <b>总信号：91887926 </b> </p> <p> <b>未使用的信号总数：660348376 </b> </p> <p> <b>已识别的特征总数：258086908 </b> </p> <p> <b>删除的特征总数：0 </b> </p> <p> <b>总特征失败验证：0 </b> </p> <p> <b>具有未验证验证特征的用户总数：0 </b> </p> <p> <b>工作开始时间：2018-05-1718：07：49 </b> </p> <p> <b>作业结束时间：2018-05-1718：44：02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

下表包含与收到的电子邮件中的行对应的行。

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
   <td colname="col2"> <p>Adobe收到的与合作伙伴一起处理的所有入站文件的列表。在以前的示例电子邮件中，合作伙伴ID为7，数据所有者ID为901。 </p> <p>尾部编号(1,2,3…)是由客户或入站分销商添加的拆分号码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收到的记录 </td> 
   <td colname="col2"> <p>Adobe在所有文件中收到的记录总数。在大多数情况下，这应该是入站文件中的行数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 格式错误 </td> 
   <td colname="col2"> <p>与预期格式不符的行数。这些线无法被入站作业识别。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AAM ID无效 </td> 
   <td colname="col2"> <p>Audience Manager UI与预期38位格式不匹配的数量。或者，在文件中发送的Audience Manager UI不是数字。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 不匹配AAM ID </td> 
   <td colname="col2"> <p>Audience Manager未能找到匹配UUID的用户数。这些文件尚未同步ID，因此Audience Manager无法查找UUID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未实现特征 </td> 
   <td colname="col2"> <p>记录中没有任何信号映射到Audience Manager特征的记录数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已处理记录 </td> 
   <td colname="col2"> <p>已处理Audience Manager的总数。在大多数情况下，此数字应与“收到的记录”相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 存储的记录 </td> 
   <td colname="col2"> <p>导致加载到系统中的数据的数量=已处理的记录-格式错误-无效AAM ID-不匹配AAM ID-未实现特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 设备总数 </td> 
   <td colname="col2"> <p>将数据载入系统的设备数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 总信号 </td> 
   <td colname="col2"> <p> 所有入站文件中所有用户的信号总数(处理所处理的记录中的键/值对总数)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 未使用的信号总数 </td> 
   <td colname="col2"> <p>所有入站文件(未映射到Audience Manager特征的键/值对)中所有用户的未使用信号总数。在大多数情况下，这意味着Audience Manager没有为信号定义规则。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 已识别的特征总数 </td> 
   <td colname="col2"> <p>所有基于这些信号的入站文件中所有用户的Audience Manager特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 删除的特征总数 </td> 
   <td colname="col2"> <p> 所有入站文件中所有用户的全部删除特征总数。对于完全同步，如果用户具有之前运行中的特征但当前运行中没有该特征，则会发生这种情况。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 总特征失败验证 </td> 
   <td colname="col2"> <p>表示不属于文件名中声明的数据源的特征数。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有未验证身份的特性的用户总数 </td> 
   <td colname="col2"> <p>验证失败的记录的数量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作开始时间 </td> 
   <td colname="col2"> <p>入站作业开始的时间。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作业结束时间 </td> 
   <td colname="col2"> <p>入站作业结束的时间。 </p> </td> 
  </tr> 
 </tbody> 
</table>