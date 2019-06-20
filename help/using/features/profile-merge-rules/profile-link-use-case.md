---
description: 使用“个人资料链接”设备图表进行细分重定向和个性化细分资格的推荐和使用案例。
seo-description: 使用“个人资料链接”设备图表进行细分重定向和个性化细分资格的推荐和使用案例。
seo-title: 个人资料链接设备图表使用案例
solution: Audience Manager
title: 个人资料链接设备图表使用案例
uuid: bd5567fd-fcd5-40ba-b6 f1-035d2 ddbcd3 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Link Device Graph Use Cases {#profile-link-device-graph-use-cases}

Recommendations and use cases for segment retargeting and personalized segment qualification with the [!UICONTROL Profile Link] device graph.

## 推荐 {#recommendations}

Consider the [!UICONTROL Profile Link] device graph for campaigns that:

* 在其数字资产中具有高级别的身份验证。Use an [external device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a small amount of authenticated users.
* 需要准确定位已知受众。The [!UICONTROL Profile Link device graph] is built using first-party, authenticated data.
* 实时定位经过身份验证和未验证状态的已知受众。

![](assets/merge-rule-triangle2.png)

## Retargeting Use Case and Profile Merge Rule Configuration {#retargeting-use-cases}

重新定位之前在多个设备上通过现场和/或应用程序进行身份验证的受众。区段可以由以下配置文件组成：

* 上一个已知的已验证设备配置文件。
* 跨设备配置文件的匿名活动。

>[!NOTE]
>
>个人资料类型的特征信息可用于创建区段。

### 重定向示例

让我们来看看如何与示例信用卡公司一起工作。此示例使用从个设备配置文件中的匿名活动收集的特征信息。

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
   <td colname="col2"> <p>此用例假设下列条件： </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">一个用户有个设备，并且是在所有设备上验证信用卡公司网站/应用程序的最后一个人。 </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">在第一台设备上，未身份验证状态的用户将显示高级信用卡的选件。 </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">在第二台设备上，未身份验证状态的用户查看高级信用卡优势页面。 </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">在第三台设备上，未身份验证状态的用户将查看高级信用卡费用和费率页。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">使用当前设备上的上次身份验证配置文件合并从所有设备收集的匿名、未验证活动。 </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">根据以下情况评估匿名用户的细分资格： 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">在所有设备上的匿名活动的组合。 </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">当前设备上的上次身份验证配置文件。 </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">将区段发送到任何可跨全部设备重定向的实时目标。 </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 重定向配置文件合并规则示例

To set up retargeting with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] 这些选项将与此示例不同，因为这些设置使用跨设备数据源的名称。

![配置文件合并规则设置](assets/merge-rules-internal3.png)

## Personalization Use Case and Profile Merge Rule Configuration {#personalization-use-case}

根据跨多种设备的活动，为现场和/或应用程序中的身份验证受众个性化体验。区段可以由以下配置文件组成：

* 当前已验证的设备配置文件。
* 匿名设备配置文件。

>[!NOTE]
>
>用户必须处于经身份验证的状态才能获得区段。

### 个性化示例

让我们来看看如何与示例信用卡公司一起工作。

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
   <td colname="col2"> <p>我们的使用案例假设下列条件： </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">一个用户有个设备，并且是在所有设备上验证信用卡公司网站/应用程序的最后一个人。 </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">在第一台设备上，未身份验证状态的用户将显示高级信用卡的选件。 </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">在第二台设备上，未身份验证状态的用户查看高级信用卡优势页面。 </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">在第三台设备上，未身份验证状态的用户将查看高级信用卡费用和费率页。 </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">在任何这些设备上，客户都会验证(通过登录)以检查其余额。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>结果</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">使用当前已验证的配置文件合并从所有设备收集的匿名、未验证活动。经过身份验证的配置文件在每台设备上提供通用标识符。 </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">根据以下情况评估经过认证的用户进行细分资格评估： 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">在所有设备上的匿名活动的组合。 </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">其当前身份验证配置文件。 </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">将区段发送到任何实时目标，以便为用户在其当前设备上进行身份验证时创建个性化的浏览体验。 <p>注意：这将使区段的所有设备符合条件，无论身份验证状态如何。如果共享设备，此结果可能会引起隐私问题。 </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### 个性化配置文件合并规则示例

To set up personalization with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] 这些选项将与此示例不同，因为这些设置使用跨设备数据源的名称。

![](assets/merge-rules-internal4.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ This]
>
>* [外部设备图形使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [个人资料合并规则的一般使用案例](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

