---
description: 查看当前配置的数据源列表、添加新数据源和编辑现有源。
seo-description: 查看当前配置的数据源列表、添加新数据源和编辑现有源。
seo-title: 数据源列表和设置
solution: Audience Manager
title: 数据源列表和设置
uuid: 280a6acd-fef0-4737-a96 d-9e22 fbc8 bfaf
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Data Sources List and Settings {#data-sources-list-and-settings}

查看当前配置的数据源列表、添加新数据源和编辑现有源。

<!-- c_datasources.xml -->

You can also manage data sources using [!DNL API] methods. For more information, see [Data Source API Methods](../api/rest-api-main/aam-api-data-sources.md).

## Data Sources List View {#list-view}

[!UICONTROL Data Sources] 仪表板是用于管理数据源的中央工作区。

<!-- c_datasources_list.xml -->

[!UICONTROL Data Sources] 仪表板(**[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**)包含可帮助您：

* See all your existing data sources, including each data source&#39;s description, status, and whether it is [!UICONTROL Inbound], [!UICONTROL Outbound], both, or a [!UICONTROL Shared Provider].
* 按名称搜索数据源。
* 创建、编辑和删除数据源。

## Data Source Settings and Menu Options {#settings-menu-options}

[!UICONTROL Data Source] 管理界面的不同部分中的设置可识别数据源，确定使用或共享的数据源，并允许您启用错误报告 [!UICONTROL Onboarding Status Report]。

## Data Source Details {#details}

<!-- datasource-settings-definitions.xml -->

In addition to text fields, the [!UICONTROL Data Source Details] section contains the controls and options listed below.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> 菜单选项 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 类型</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>：标识设备的cookie ID。当数据源是Web浏览器或处理不能与单个人关联的匿名数据或数据时，您可以选择此选项。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 设备广告ID</span></b>：移动设备标识符。当数据源是支持移动设备或支持Internet的设备时，请选择此选项。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 跨设备</span></b>：客户提供的经过验证的ID。在要创建时，请选择此选项： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">A cross-device data source and build a <span class="wintitle"> Profile Merge Rule</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">A data source that uses links provided by the <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> or another, third-party device graph that is integrated with <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定义</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> ID定义</span></b> 选项定义数据源与 <span class="keyword"> Audience Manager</span> 用户ID(UUID)及由 <span class="keyword"> Adobe Experience Cloud Device Co-op</span> 或与 <span class="keyword"> Audience Manager集成的另一个第三方设备图关联的关联设备所建立的关系</span>。选项包括： </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 人：</span></b> 用于定义单个人的ID。This ID can be mapped to multiple <span class="keyword"> Audience Manager</span> IDs. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 家庭：</span></b> 用于定义一组人员的ID。此ID可映射到多个Audience Manager ID。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 数据导出控制 {#export-controls}

[数据导出控件](../features/data-export-controls.md) 是可选的分类规则，您可以应用于数据源和目标。当该操作违反了数据隐私或使用协议时，它们会阻止您向目标发送数据。Skip this section if you do not use [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>除非在目标上设置了匹配的导出标签，否则导出限制将不起作用。

选项包括：

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

[!UICONTROL Data Source Settings] 其中包含以下列出的控件和选项。其中一些设置具有其他子选项和菜单项，您可以选择这些选项来修改数据源。

### 入站数据源设置

Select the **[!UICONTROL Inbound]** check box when your data source is designed to receive inbound data. Selecting the **[!UICONTROL Inbound]** check box exposes 2 additional groups of controls described below.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> 菜单选项 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID 类型</span></b> </p> </td> 
   <td colname="col2"> <p><b><span class="uicontrol"> “入站”</span></b> 选项需要ID类型。选项包括： </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 客户ID</span></b>：使用客户ID识别入站数据。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager ID</span></b>：使用 <span class="keyword"> Audience Manager</span> ID识别入站数据。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>：使用 <span class="keyword"> Experience Cloud</span> ID识别入站数据。See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 文件格式疑难解答</span></b> </p> </td> 
   <td colname="col2"> <p>Select <b><span class="uicontrol"> Enable file error sampling</span></b> when you need to troubleshoot problems with inbound file processing. 此功能会生成一个错误示例报告，其中显示文件格式和语法错误。 </p> <p>See <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Onboarding Status Report: About</a> for information about error reporting and error sampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他数据源设置

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> 选择时间 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 出站</span></b> </p> </td> 
   <td colname="col2"> <p>数据源将数据发送到目标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已启用共享</span></b> </p> </td> 
   <td colname="col2"> <p>您的数据源可与其他合作伙伴共享。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作身份验证配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨设备数据源包含身份验证ID。An Authenticated ID is collected and synced to an <span class="keyword"> Audience Manager</span> ID during an authentication event (e.g, a user logs in on-site, in-app, etc.). 身份验证ID可用于存储此ID的其他来源的展示板数据。It can also be used to link multiple device IDs in <span class="wintitle"> Profile Link</span>. </p> <p>此选项显示一个文本字段，它允许您使用别名重命名数据源。If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Authenticated Profile Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作设备图表</span></b> </p> </td> 
   <td colname="col2"> <p>Creates a data source as a device graph which you can provide to other <span class="keyword"> Audience Manager</span> customers. Before you select this option, tell with your <span class="keyword"> Audience Manager</span> consultant which customers this <span class="wintitle"> Data Source</span> should be shared with. 您的顾问必须通过我们的内部流程提供这些公司。 </p> <p>此选项显示一个文本字段，它允许您使用别名重命名数据源。If you use an alias, this new name overrides the data source name and appears in the <span class="wintitle"> Device Options</span> when you <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> create a Profile Merge rule</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 与特定Audience Manager客户共享关联的访客或设备ID</span></b> </p> </td> 
   <td colname="col2"> <p>跨设备数据源包含设备图表中的ID。A device graph is a collection of IDs which map to one or more <span class="keyword"> Audience Manager</span> IDs to a cluster. 此群集通常代表一个人或大型用户组。仅可用于列为“数据提供程序”的帐户。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 跨Audience Manager平台共享关联访客或设备ID</span></b> </p> </td> 
   <td colname="col2"> <p>Your data source contains visitor or device IDs that can be shared across other <span class="keyword"> Experience Cloud</span> solutions. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非活动客户ID的数据保留</span></b> </p> </td> 
   <td colname="col2"> <p>允许您设置非活动客户ID的数据保留期限。这决定Audience Manager在Audience Manager平台上最后一次看到时，在我们的数据库中保留客户ID的时间。</p> <p>默认值为24个月(720天)。您可以设置的最小值为个月，最大值为年。请注意，我们将所有月份计为30天。</p> <p>Audience Manager会根据您为非活动客户ID设置的数据保留，每周删除一次不活动的客户ID。</p> <p>Audience Manager会根据您为非活动客户ID设置的数据保留，每周删除一次不活动的客户ID。</p> <p><b>注意</b>：此控制仅适用于跨设备数据源。See also, <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 独特特征集成代码</span></b> </p> </td> 
   <td colname="col2"> <p>您希望强制来自同一数据源的两个特征没有相同的集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一细分集成代码</span></b> </p> </td> 
   <td colname="col2"> <p>您希望强制同一数据源中的两个区段没有相同的集成代码。 </p> </td> 
  </tr>
 </tbody>
</table>
