---
description: 檢視目前設定的資料來源清單、新增資料來源，以及編輯現有來源。
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: 数据源列表和设置
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---

# [!UICONTROL Data Sources] 清單與設定 {#data-sources-list-and-settings}

檢視您目前設定的清單 [!UICONTROL data sources]，新增 [!UICONTROL data sources]，並編輯現有 [!UICONTROL data sources].

您也可以管理 [!UICONTROL data sources] 使用 [!DNL API] 方法。 有关详细信息，请参阅 [ Data 来源 API 方法 ](../api/rest-api-main/aam-api-data-sources.md) 。

## [!UICONTROL Data Sources] 列表视图 {#list-view}

[!UICONTROL Data Sources]功能板是用于管理数据源的集中工作区。

[!UICONTROL Data Sources]控制面板（ **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** ）包含一些功能和工具，可帮助您：

* 查看所有现有 [!UICONTROL data sources] 的，包括每个数据源的描述、状态以及是否为 [!UICONTROL Inbound] 、 [!UICONTROL Outbound] 、两者或 a [!UICONTROL Shared Provider] 。
* [!UICONTROL data sources]按名称 Search。
* 创建、编辑和删除 [!UICONTROL data sources] 。

## [!DNL Data Source] 设置和菜单选项 {#settings-menu-options}

不同區段中的設定 [!UICONTROL Data Source] 管理介面識別您的 [!DNL data source]，決定如何使用或共用它，並讓您為啟用錯誤報告 [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] 详细信息 {#details}

除了文字欄位外， [!UICONTROL Data Source Details] 區段包含下列控制項和選項。

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie </span></b> ：用于识别设备的 COOKIE ID。 当您的数据源是 web 浏览器或无法与单个人员关联的匿名数据或数据时，可以选择此操作。 </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> 设备广告 ID </span></b> ：移动设备标识符。 如果您的数据源已启用移动设备或 Internet 设备，请选择此选项。 </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> 交叉设备 </span></b> ：客户提供的、经过身份验证的 ID。 當您想要建立以下專案時，請選取此選項： 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">跨裝置資料來源並建置 <span class="wintitle"> 設定檔合併規則</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">使用整合至的協力廠商裝置圖表所提供連結的資料來源 <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID定義</span></b> </p> </td> 
   <td colname="col2"> <p>此 <b><span class="uicontrol"> ID定義</span></b> 選項定義資料來源與 <span class="keyword"> Audience Manager</span> 使用者ID (UUID)和由整合至的協力廠商裝置圖表連結的相關裝置 <span class="keyword"> Audience Manager</span>. 选项包括： </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> 人员： </span></b> 用于定义单个人员的 ID。 此 ID 可以映射到多个 <span class="keyword"> Audience Manager </span> id。 </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> 家庭： </span></b> 用于定义人员群组的 ID。 此 ID 可以映射到多个 Audience Manager Id。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[数据导出控件 ](../features/data-export-controls.md) 是可应用于和 [!UICONTROL destination] 的 [!UICONTROL data source] 可选分类规则。当该操作违反数据隐私或使用协议时，它们会阻止您将数据发送到 [!UICONTROL destination] 。 如果您不使用 [!UICONTROL Data Export Controls] ，请跳过此部分。

>[!IMPORTANT]
>
>除非您在中设置匹配的 [!UICONTROL destination] 导出标签，否则导出限制将不起作用。

选项包括：

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] 设置 {#data-source-settings}

此 [!UICONTROL Data Source Settings] 包含下列控制項和選項。 其中一些設定具有其他子選項和功能表專案，您可以選取它們來修改資料來源。

### [!UICONTROL Inbound Data Source] 设置

選取 **[!UICONTROL Inbound]** 核取方塊。 选中此 **[!UICONTROL Inbound]** 复选框会公开2个其他控件组，如下所述。

>[!NOTE]
>
>此 **[!UICONTROL Inbound]** 复选框仅用于显示或隐藏以下所述的 [!UICONTROL data source] 控件。 取消选中该 **[!UICONTROL Inbound]** 选项不会对数据摄取产生任何影响。 无论选中此选项，都将处理您的载入数据。

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
   <td colname="col2"> <p>此 <b><span class="uicontrol"> 傳入</span></b> 選項需要ID型別。 选项包括： </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> 客戶ID</span></b>：使用客戶ID識別傳入資料。 </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> AUDIENCE MANAGERID</span></b>：識別傳入資料，使用 <span class="keyword"> Audience Manager</span> ID。 </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud ID </span></b> ：使用 <span class="keyword"> Experience Cloud </span> id 识别入站数据。 另請參閱 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookie和Experience CloudID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 檔案格式疑難排解</span></b> </p> </td> 
   <td colname="col2"> <p>選取 <b><span class="uicontrol"> 啟用檔案錯誤取樣</span></b> 適用於需要疑難排解傳入檔案處理問題的情況。 此功能會產生錯誤範例報告，顯示檔案格式和語法錯誤。 </p> <p>另請參閱 <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> 上線狀態報表：關於</a> 以取得有關錯誤報告和錯誤取樣的相關資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### 其他 [!UICONTROL Data Source] 設定

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设置 </th> 
   <th colname="col2" class="entry"> 选择时间 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 出境</span></b> </p> </td> 
   <td colname="col2"> <p>您的数据源将数据发送到目标。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 已启用共享</span></b> </p> </td> 
   <td colname="col2"> <p>您的数据源可以与其他合作伙伴共享。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作经过身份验证的配置文件</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含已驗證的ID。 已驗證的ID會加以收集並同步至 <span class="keyword"> Audience Manager</span> 驗證事件期間的ID （例如，使用者登入網站、應用程式內等）。 已驗證的ID可用於來自儲存此ID之其他來源的主機板內資料。 它也可用來連結中的多個裝置ID <span class="wintitle"> 設定檔連結</span>. </p> <p>此選項會顯示文字欄位，讓您以別名重新命名資料來源。 如果使用别名，则此新名称会覆盖数据源名称，并会在您 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 创建配置文件合并规则 </a> 时显示在已验证的 <span class="wintitle"> 配置文件选项 </span> 中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 用作设备图表</span></b> </p> </td> 
   <td colname="col2"> <p>创建数据源作为可提供给其他 <span class="keyword"> Audience Manager </span> 客户的设备图。 在选择此选项之前，请告知您 <span class="keyword"> 的 Audience Manager </span> 顾问应与哪些客户共享此 <span class="wintitle"> 数据来源 </span> 。 您的顾问将必须通过我们的内部流程来配置这些公司。 </p> <p>此选项会公开一个文本字段，可让您使用别名重命名数据源。 如果使用别名，则此新名称会覆盖数据源名称，并会在创建配置文件合并规则 </a> 时 <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> 显示在设备选项 </span> 中 <span class="wintitle"> 。 </span></a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 与特定的 Audience Manager 客户共享关联的访客或设备 Id</span></b> </p> </td> 
   <td colname="col2"> <p>您的跨裝置資料來源包含來自裝置圖表的ID。 设备图是一个 Id 收藏集，可映射到群集的一个或多个 <span class="keyword"> Audience Manager </span> id。 此叢集通常代表個人或較大的家庭群組。 僅適用於列為「資料提供者」的帳戶。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 在整個Audience Manager平台中共用相關聯的訪客或裝置ID</span></b> </p> </td> 
   <td colname="col2"> <p>您的資料來源包含可以與其他人共用的訪客或裝置ID <span class="keyword"> Experience Cloud</span> 解決方案。 </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 非作用中客戶ID的資料保留</span></b> </p> </td> 
   <td colname="col2"> <p>允许您设置非活动客户 Id 的数据保留期限。 這會決定Audience Manager將客戶ID保留在資料庫中的時間，之前一次在Audience Manager平台上看到這些客戶ID之後。</p> <p>默认值为24个月（720天）。 您可以设置的最小值为1个月，最大值为5年。 请注意，我们将所有月份计算为30天。</p> <p>Audience Manager 会根据您为非活动客户 Id 设置的数据保留，运行一周删除非活动客户 Id 一次的过程。</p> <p>Audience Manager 会根据您为非活动客户 Id 设置的数据保留，运行一周删除非活动客户 Id 一次的过程。</p> <p><b>注意</b>：此控制項僅適用於跨裝置資料來源。 <a href="../features/profile-merge-rules/merge-rules-start.md#settings">另请参阅创建跨设备数据来源 </a> 。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 唯一特徵整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您想要強制實施來自相同資料來源的兩個特徵沒有相同的整合程式碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 不重複區段整合代碼</span></b> </p> </td> 
   <td colname="col2"> <p>您希望强制同一数据源中的两个区段没有相同的集成代码。 </p> </td> 
  </tr>
 </tbody>
</table>
