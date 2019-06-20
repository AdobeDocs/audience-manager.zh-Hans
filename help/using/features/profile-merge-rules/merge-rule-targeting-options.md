---
description: 个人资料合并规则选项可让您根据业务需求或目标扩展或收紧受众关注特定受众。这些一般使用案例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。目前，配置文件合并规则只能与实时目标配合使用。
seo-description: 个人资料合并规则选项可让您根据业务需求或目标扩展或收紧受众关注特定受众。这些一般使用案例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。目前，配置文件合并规则只能与实时目标配合使用。
seo-title: 个人资料合并规则的一般使用案例
solution: Audience Manager
title: 个人资料合并规则的一般使用案例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11 ef08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# General Use Cases for Profile Merge Rules {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 选项允许您根据业务需求或目标扩展或收紧受众关注特定受众。这些一般使用案例探讨如何使用可用选项并为个人、家庭和跨设备定位创建合并规则。Currently, [!UICONTROL Profile Merge Rules] work with real-time destinations only.

![](assets/merge-rules-options.png)

>[!TIP]
>
>For definitions and descriptions of these [!UICONTROL Merge Rule] settings, see [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md).

## Focused targeting {#focused-targeting}

User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. After this event, [!DNL Audience Manager] writes trait data to (and reads from) an authenticated profile. The authenticated profile lets [!DNL Audience Manager]:

* 将特征写入特定用户特定的身份验证配置文件。
* 识别并区分多个设备用户以进行细分。

### 接触经过身份验证的用户

经过身份验证的配置文件选项可创建规则，允许您定位基于脱机属性登录到网站或应用程序的用户。例如，金融服务公司可使用此选项根据有针对性的信用卡升级提供目标信用卡升级，或根据收入或线下活动提供专门的服务推广信息。另一个示例是航空公司通过基于累计里程的交易来验证经常的传单。

To create a rule that reaches only authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. 此选项将仅使用经过身份验证的配置文件数据来评估区段。此规则将忽略匿名设备配置文件中的数据。

To also include data in the anonymous device profile, use the **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** rule.

### 根据之前的身份验证状态触及用户

这些选项在用户浏览但未登录时到达特定用户。您可以使用依赖推断用户级定位的选项进行此操作。推断定位可帮助您触及未明确身份验证您的网站但可能在线浏览的人员。它通过从上一个经过验证的配置文件读取(但不是写入)数据工作。And, to help keep the authenticated profile clean, [!DNL Audience Manager] writes new trait qualifications to the device profile instead of the authenticated profile. 例如，您是一名营销人员，希望与未登录您的网站或应用程序的现有客户测试不同的优惠。作为营销人员，您可以与当前未经身份验证的客户测试这些广告，以了解哪些推广信息最能得到响应。

一个根据匿名身份验证触及用户的规则示例是：

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Expanded targeting {#expanded-targeting}

除了有助于触及特定客户的规则之外，营销人员还需要规则，以增加可用于定位的数据集规模。[!UICONTROL Profile Merge Rules] 让您使用设备配置文件选项进行操作。设备选项扩展有资格获得分段的数据集，因为在一个或多个设备上用户处于匿名状态时，他们可以绘制出所需的特征。当您尝试在家用设备图中使用真人设备图或所有设备接触用户时，这可能会非常有用。此选项的使用案例包括宣传家庭度假套餐。在这种情况下，如果任何设备上的某个用户已经对该选件感兴趣，您将希望通过选件触及某个家用设备。

To create a rule that expands the targeting data set, select the **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** rule.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Device Graph Options {#device-graph-options}

Choosing a [!UICONTROL device graph] option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. 这些一般指导方针可以帮助您了解何时使用一种图形。Note, you must be a member of the [!DNL Adobe Experience Cloud Device Co-op] or have a contractual relationship with an external device graph to use these options. 有关何时选择设备图表选项的一般指导，请参阅下表。For specific use cases, see [Profile Link Device Graph Use Cases](../../features/profile-merge-rules/profile-link-use-case.md) and [External Device Graph Use Cases](../../features/profile-merge-rules/external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图表类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 配置文件链接</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用</span><span class="wintitle"> 配置文件链接</span> 选项构建的配置文件合并规则非常适合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高客户身份验证级别的数字属性。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">专注于低营销活动的营销活动。<span class="wintitle"> 配置文件链接</span> 设备图表仅基于确定的数据构建。此设备配置文件池相对于未经过身份验证的用户和设备的池总是更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">使用客户处于身份验证状态才能获得细分资格的情形。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部设备图表选项 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用Experience Cloud Device Co-op构建的个人资料合并</span><a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> 规则</a> 或与 <span class="keyword"> Audience Manager集成的任何外部设备图表</span> 非常适合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有较低客户身份验证级别的数字资产。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">广泛的高范围品牌营销活动。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">使用客户不必处于身份验证状态才能获得细分资格的情形。 </li> 
     </ul> </p> <p> <p>Tip: The <span class="keyword"> Device Co-op</span> is your best option if you're a <span class="keyword"> Experience Cloud</span> customer with low authentication and no relationship with any device graph provider. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [个人资料链接设备图表使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [外部设备图形使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

