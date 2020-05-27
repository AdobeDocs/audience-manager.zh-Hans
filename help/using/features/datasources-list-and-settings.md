---
description: 视图当前配置的数据源的列表，添加新数据源，并编辑现有源。
seo-description: 视图当前配置的数据源的列表，添加新数据源，并编辑现有源。
seo-title: 数据源列表和设置
solution: Audience Manager
title: 数据源列表和设置
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
translation-type: tm+mt
source-git-commit: 6b55441c2bdde6cf2333852fd59fbe87f4e531eb
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---


# 数据源列表和设置 {#data-sources-list-and-settings}

视图当前配置的数据源的列表，添加新数据源，并编辑现有源。

<!-- c_datasources.xml -->

您还可以使用方法管理数 [!DNL API] 据源。 有关详细信息，请 [参阅数据源API方法](../api/rest-api-main/aam-api-data-sources.md)。

## 数据源列表视图 {#list-view}

仪表板 [!UICONTROL Data Sources] 是用于管理数据源的集中工作区。

<!-- c_datasources_list.xml -->

该 [!UICONTROL Data Sources] 仪表板&#x200B;**[!UICONTROL Audience Data]** ( **[!UICONTROL Data Sources]**>)包含可帮助您：

* 查看所有现有数据源，包括每个数据源的描述、状态，以及它 [!UICONTROL Inbound]是 [!UICONTROL Outbound]、两者还是 [!UICONTROL Shared Provider]。
* 按名称搜索数据源。
* 创建、编辑和删除数据源。

## 数据源设置和菜单选项 {#settings-menu-options}

管理界面不同部分中的设 [!UICONTROL Data Source] 置可识别您的数据源，确定数据源的使用或共享方式，并允许您为启用错误报告 [!UICONTROL Onboarding Status Report]。

## 数据源详细信息 {#details}

<!-- datasource-settings-definitions.xml -->

除文本字段外，该部 [!UICONTROL Data Source Details] 分还包含下面列出的控件和选项。

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: 标识设备的Cookie ID。 当您的数据源是Web浏览器，或者处理不能与单个人关联的匿名数据或数据时，您应选择此选项。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 设备广告ID</span></b>: 移动设备标识符。 当数据源是移动设备或启用Internet的设备时，请选择此选项。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 跨设备</span></b>: 客户提供的、经过身份验证的ID。 当您要创建时，请选择此选项： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">跨设备数据源并构建 <span class="wintitle"> 用户档案合并规则</span>。 </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">一个数据源，它使用Adobe Experience Cloud <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Device Co-op提供的链接</a> ，或与受众管理器集成的其他第三方设备 <span class="keyword"> 图形</span>。 </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定义</span></b> </p> </td> 
   <td colname="col2"> <p>ID定 <b><span class="uicontrol"> 义选项</span></b> ，用于定义数据源与Adobe Experience Cloud Device Co-op或与Adobe Experience Cloud设备协作(Adobe Experience Cloud Device Co <span class="keyword"> -op)链接的Adobe Manager用户ID(UUID)和关联设备的关</span><span class="keyword"></span><span class="keyword"></span>系。 选项包括： </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 人员：</span></b> 用于定义单个人员的ID。 此ID可以映射到多个 <span class="keyword"> 受众管理器</span> ID。 </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 家庭：</span></b> 用于定义一组人员的ID。 此ID可以映射到多个受众管理器ID。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 数据导出控制 {#export-controls}

[数据导出控件](../features/data-export-controls.md) (Data Export Controls)是可应用于数据源和目标的可选分类规则。 它们可防止您在数据隐私或使用协议违反数据隐私或使用协议时向目标发送数据。 如果不使用，请跳过此部 [!UICONTROL Data Export Controls]分。

>[!IMPORTANT]
>
>除非在目标上设置匹配的导出标签，否则导出限制将无效。

选项包括：

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## Data Source Settings {#data-source-settings}

其中 [!UICONTROL Data Source Settings] 包含下面列出的控件和选项。 其中一些设置具有其他子选项和菜单项，您可以选择这些子选项和菜单项来修改数据源。

### 入站数据源设置

当您的 **[!UICONTROL Inbound]** 数据源设计为接收入站数据时，请选中此复选框。 选中该复 **[!UICONTROL Inbound]** 选框将显示下面描述的另外两组控件。

>[!NOTE]
>
>该 **[!UICONTROL Inbound]** 复选框仅用于显示或隐藏下面描述的数据源控件。 取消选中 **[!UICONTROL Inbound]** 此选项不会以任何方式影响数据获取。 无论选中此选项，载入的数据都将被处理。

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
   <td colname="col2"> <p>入站 <b><span class="uicontrol"> 选项</span></b> 需要ID类型。 选项包括： </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 客户ID</span></b>: 使用客户ID标识入站数据。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> 受众管理器ID</span></b>: 使用受众管理器ID标 <span class="keyword"> 识入站</span> 。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID</span></b>: 使用Experience Cloud ID标识 <span class="keyword"> 入站数据</span> 。 See <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 文件格式疑难解答</span></b> </p> </td> 
   <td colname="col2"> <p>当您需要 <b><span class="uicontrol"> 对入站文件处理问题进行疑难解答</span></b> 时，请选择“启用文件错误采样”。 此功能会生成一个错误示例报告，其中显示文件格式和语法错误。 </p> <p>请参 <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 阅入门状态报告： 关于</a> ，以了解有关错误报告和错误采样的信息。 </p> </td> 
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
   <td colname="col2"> <p>您的数据源可以与其他合作伙伴共享。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作已验证的用户档案</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨设备数据源包含已验证的ID。 在身份验证受众(例如，用 <span class="keyword"> 户登录现场、应用程序内等)期间，会收集已验证的ID并同步到事件管理器</span> ID。 已验证ID可用于存储此ID的其他源的板载数据。 它还可用于链接用户档案链接中的多个设 <span class="wintitle"> 备ID</span>。 </p> <p>此选项显示一个文本字段，它允许您使用别名重命名数据源。 如果您使用别名，则此新名称将覆盖数据源名称，并在创建用户档案合并规则 <span class="wintitle"> 时显示在</span> “已验证 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 用户档案选项”中</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作设备图</span></b> </p> </td> 
   <td colname="col2"> <p>创建一个数据源作为设备图形，您可以将其提供给其他 <span class="keyword"> 受众管理</span> 器客户。 在选择此选项之前，请咨询 <span class="keyword"> 受众经理</span> ，咨询应 <span class="wintitle"> 与哪些客户共享此</span> 数据源。 您的顾问必须通过我们的内部流程配置这些公司。 </p> <p>此选项显示一个文本字段，它允许您使用别名重命名数据源。 如果您使用别名，则此新名称将覆盖数据源名称，并在创建用户档案合 <span class="wintitle"> 并规则时</span><a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 显示在设备选项中</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 与特定访客管理器客户共享关联的受众或设备ID</span></b> </p> </td> 
   <td colname="col2"> <p>跨设备数据源包含设备图形中的ID。 设备图是映射到一个或多个受众管理器ID <span class="keyword"> 的ID</span> 的集合。 这一群通常代表一个或更大的家庭群体。 仅对作为“数据提供程序”列出的帐户可用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 跨访客管理器平台共享关联的受众或设备ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的数据源包含可在其他Experience Cloud解决方案间共享的访客 <span class="keyword"> 或设备</span> ID。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非活动客户ID的数据保留</span></b> </p> </td> 
   <td colname="col2"> <p>允许您为非活动的客户ID设置数据保留期。 这决定了受众管理器在受众管理器平台上最后一次看到客户ID后，客户ID在我们的数据库中保留多长时间。</p> <p>默认值为24个月（720天）。 您可以设置的最小值为1个月，最大值为5年。 请注意，我们把所有月份都算作30天。</p> <p>受众经理会根据您为非活动客户ID设置的数据保留情况，每周删除不活动客户ID一次的流程。</p> <p>受众经理会根据您为非活动客户ID设置的数据保留情况，每周删除不活动客户ID一次的流程。</p> <p><b>注意</b>: 此控件仅适用于跨设备数据源。 另请参阅 <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> 创建跨设备数据源 </a>。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一特征集成代码</span></b> </p> </td> 
   <td colname="col2"> <p>您希望强制同一数据源中的两个特征没有相同的集成代码。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一细分集成代码</span></b> </p> </td> 
   <td colname="col2"> <p>您希望强制同一数据源中的两个区段没有相同的集成代码。 </p> </td> 
  </tr>
 </tbody>
</table>
