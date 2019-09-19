---
description: 通过“配置文件链接”设备图表，为细分重定向和个性化细分资格提供推荐和使用案例。
seo-description: 通过“配置文件链接”设备图表，为细分重定向和个性化细分资格提供推荐和使用案例。
seo-title: 配置文件链接设备图形使用案例
solution: Audience Manager
title: 配置文件链接设备图形使用案例
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 配置文件链接设备图形使用案例 {#profile-link-device-graph-use-cases}

通过设备图表推荐和使用案例，实现细分重定向和个性化细 [!UICONTROL Profile Link] 分资格认定。

## 推荐 {#recommendations}

考虑以下 [!UICONTROL Profile Link] 营销活动的设备图：

* 在其数字资产中进行高级身份验证。 如果您 [有少量经过身份验证的用户](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) ，请使用外部设备图形选项。
* 需要准确定位已知受众。 使用 [!UICONTROL Profile Link device graph] 第一方的实名数据构建。
* 实时在其已验证和未验证状态中定位已知受众。

![](assets/merge-rule-triangle2.png)

## 重新定位用例和配置文件合并规则配置 {#retargeting-use-cases}

重新定位之前在多个设备上通过现场和／或应用程序内身份验证的受众。 区段可以由以下配置文件组成：

* 上次已知的已验证设备配置文件。
* 每个设备配置文件中的匿名活动。

>[!NOTE]
>
>任何一种配置文件类型的特征信息都可用于创建区段。

### 重定向示例

让我们来看一下，这个示例信用卡公司是如何运作的。 此示例仅使用从3个设备配置文件中看到的匿名活动收集的特征信息。

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p>此用例假定以下条件： </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">用户有3台设备，是在所有3台设备上在信用卡公司站点／应用程序上进行身份验证的最后一个人。 </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">在第一设备上，处于未认证状态的用户查看付费信用卡的优惠。 </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">在第二台设备上，处于未验证状态的用户查看付费信用卡优势页面。 </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">在第三台设备上，处于未验证状态的用户查看付费信用卡费用和费率页面。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于这些条件， <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">使用当前设备上最后一个已验证的配置文件合并从所有3台设备收集的匿名未验证活动。 </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">根据以下情况评估匿名用户的细分资格： 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">所有3台设备上的匿名活动组合。 </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">当前设备上经过身份验证的最后一个配置文件。 </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">将区段发送到任何实时目标，以便在所有3台设备上重新定位。 </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 重定位配置文件合并规则示例

要设置重定位， [!UICONTROL Profile Link]您的 [!UICONTROL Authenticated Options] 和 [!UICONTROL Device Options] 应类似于下面显示的规则配置。 这些 [!UICONTROL Authenticated Profile] 选项与此示例不同，因为这些设置使用跨设备数据源的名称。

![配置文件合并规则设置](assets/merge-rules-internal3.png)

## 个性化用例和配置文件合并规则配置 {#personalization-use-case}

根据跨多个设备的活动，为现场和／或应用程序内的实名受众提供个性化体验。 区段可以由以下配置文件组成：

* 当前已验证的设备配置文件。
* 匿名设备配置文件。

>[!NOTE]
>
>用户必须处于已验证状态才能有资格访问区段。

### 个性化示例

让我们来看一下，这个示例信用卡公司是如何运作的。

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 用例 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>条件</b> </p> </td> 
   <td colname="col2"> <p>我们的使用案例假设以下条件： </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">用户有3台设备，是在所有3台设备上在信用卡公司站点／应用程序上进行身份验证的最后一个人。 </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">在第一设备上，处于未认证状态的用户查看付费信用卡的优惠。 </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">在第二台设备上，处于未验证状态的用户查看付费信用卡优势页面。 </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">在第三台设备上，处于未验证状态的用户查看付费信用卡费用和费率页面。 </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">在任何这些设备上，客户都会进行身份验证（通过登录）以检查其余额。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>鉴于这些条件， <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">使用当前已验证的配置文件合并从所有3台设备收集的匿名未验证活动。 经过身份验证的配置文件在每个设备上提供一个通用标识符。 </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">根据以下情况评估经过身份验证的用户的区段资格： 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">所有3台设备上的匿名活动组合。 </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">他们当前的已验证配置文件。 </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">将区段发送到任何实时目标，以便在用户当前设备上进行身份验证时为用户创建个性化的浏览体验。 <p>注意： 这使区段的所有3台设备都符合条件，而不管身份验证状态如何。 如果这些设备是共享设备，则此结果可能会引起隐私问题。 </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### 个性化配置文件合并规则示例

要设置个性化，您 [!UICONTROL Profile Link]的和 [!UICONTROL Authenticated Options] 应 [!UICONTROL Device Options] 当类似于下面显示的规则配置。 这些 [!UICONTROL Authenticated Profile] 选项与此示例不同，因为这些设置使用跨设备数据源的名称。

![](assets/merge-rules-internal4.png)

有关这些设备图形处理方式的更多信息，请下载我们的PDF、 [Audience manager和外部设备图形](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)。

>[!MORE_LIKE_THIS]
>
>* [外部设备图形使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [配置文件合并规则的一般用例](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

