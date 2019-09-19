---
description: 个人资料合并规则选项允许您根据业务需求或目标扩大或加强受众对特定受众的关注。 这些一般用例探讨如何使用可用选项并为单个、家庭和跨设备定位创建合并规则。 目前，“配置文件合并规则”仅适用于实时目标。
seo-description: 个人资料合并规则选项允许您根据业务需求或目标扩大或加强受众对特定受众的关注。 这些一般用例探讨如何使用可用选项并为单个、家庭和跨设备定位创建合并规则。 目前，“配置文件合并规则”仅适用于实时目标。
seo-title: 配置文件合并规则的一般用例
solution: Audience Manager
title: 配置文件合并规则的一般用例
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 配置文件合并规则的一般用例 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 通过这些选项，您可以根据业务需求或目标扩大或收紧对特定受众的关注。 这些一般用例探讨如何使用可用选项并为单个、家庭和跨设备定位创建合并规则。 目前， [!UICONTROL Profile Merge Rules] 仅可处理实时目标。

![](assets/merge-rules-options.png)

>[!TIP]
>
>有关这些设置的定义和说明，请 [!UICONTROL Merge Rule] 参阅配置 [文件合并规则选项定义](../../features/profile-merge-rules/merge-rule-definitions.md)。

## 重点定位 {#focused-targeting}

对网站的用户身份验证应触发对的声明ID调用 [!DNL Audience Manager]。 在此事件之后， [!DNL Audience Manager] 将特征数据写入经过身份验证的配置文件（并从中读取）。 通过身份验证的配置文件， [!DNL Audience Manager]您可以：

* 将特征写入特定于特定用户的认证配置文件。
* 识别多个设备用户，并区分其细分。

### 触及经过身份验证的用户

通过身份验证的配置文件选项可创建规则，使您能够根据脱机属性定位登录到网站或应用程序的用户。 例如，金融服务公司将使用此选项，根据收入或离线活动，以具有针对性信用卡升级优惠或专用服务优惠的认证用户为目标。 另一个例子是，航空公司以经过认证的常客为目标，根据累计里程进行交易。

要创建只能到达已验证用户的规则，请选择 **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**。 此选项将仅使用经过身份验证的配置文件数据来评估区段。 此规则将忽略匿名设备配置文件中的数据。

要将数据包含在匿名设备配置文件中，请使用 **[!UICONTROL Current Authenticated Profile]** +规 **[!UICONTROL Current Device Profile]** 则。

### 根据先前的身份验证状态向用户发送

这些选项在特定用户浏览但未登录时触及用户。 您可以使用依赖推断的用户级别定位的选项执行此操作。 推断出的定位可帮助您联系未对您的网站进行明确身份验证但可能正在在线浏览的用户。 它的工作方式是从上一个经过身份验证的配置文件读取（但不写入）数据。 此外，为了帮助保持已验证的配置文件干净，请将 [!DNL Audience Manager] 新的特征资格写入设备配置文件而不是已验证的配置文件。 例如，假设您是营销人员，希望针对未登录您的网站或应用程序的现有客户测试不同的推广信息。 作为营销人员，您可以使用当前未验证的客户测试这些广告，以查看哪些优惠获得最多响应。

基于预先身份验证的触及用户的规则示例如下：

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## 扩展的定位 {#expanded-targeting}

除了有助于触及特定客户的规则外，营销人员还需要增加可用于定位的数据集大小的规则。 [!UICONTROL Profile Merge Rules] 让您使用设备配置文件选项执行此操作。 设备选项扩展了符合分段条件的数据集，因为这些数据集利用了用户在一个或多个设备上处于匿名状态时实现的特征。 当您尝试使用个人设备图表触及所有设备上的用户或使用家庭设备图表的家庭中的所有设备时，这可能很有用。 此选项的用例可能包括为家庭度假优惠做广告。 在这种情况下，如果任何设备上的用户都对该选件感兴趣，您将希望使用该选件访问家庭中的每台设备。

要创建扩展定位数据集的规则，请选择 **[!UICONTROL Last Authenticated Profiles]** +规 **[!UICONTROL Device Graph]** 则。

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

## 设备图形选项 {#device-graph-options}

选择规 [!UICONTROL device graph] 则的选项 [!UICONTROL Profile Merge] 取决于数字资产和业务目标所特有的条件。 这些一般准则可以帮助您了解何时使用一种图形与另一种图形。 请注意，您必须是外部设备图 [!DNL Adobe Experience Cloud Device Co-op] 形的成员或与外部设备图形有合同关系才能使用这些选项。 有关何时选择设备图形选项的一般指导，请参阅下表。 有关特定用例，请参阅配置 [文件链接设备图形用例](../../features/profile-merge-rules/profile-link-use-case.md) 和外 [部设备图形用例](../../features/profile-merge-rules/external-graph-use-cases.md)。

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备图形类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 配置文件链接</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用“配置文件</span> ”链接选项构建的 <span class="wintitle"> “配置文件合并规则</span> ”非常适合： </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">具有高级客户身份验证的数字资产。 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">专注、触及面低的营销活动。 Profile Link <span class="wintitle"></span> device graph only built on deterministic data. 相对于未验证的用户和设备池，此设备配置文件池始终会更小。 </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">客户需要处于身份验证状态才能获得分段资格的用例。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>外部设备图形选项 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 使用Experience Cloud</span> Device Co-op构建的配置文件合并规则或与 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Audience Manager集成的任何外部设备图</a> 形 <span class="keyword"></span> ，非常适合： </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">具有低级客户身份验证的数字属性。 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">广泛、触及面广的品牌营销活动。 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">客户无需处于已验证状态即可获得分段资格的用例。 </li> 
     </ul> </p> <p> <p>提示：如果 <span class="keyword"></span><span class="keyword"></span> 您是Experience Cloud客户，且身份验证低，且与任何设备图形提供商没有关系，则Device Co-op是您的最佳选择。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [配置文件链接设备图形使用案例](../../features/profile-merge-rules/profile-link-use-case.md)
>* [外部设备图形使用案例](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [个人资料合并规则常见问题解答](../../faq/faq-profile-merge.md)

