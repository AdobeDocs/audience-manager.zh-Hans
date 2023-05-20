---
description: 若要建立「設定檔合併規則」，請檢閱並完成本節所述每個程式中的步驟。
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: 开始使用配置文件合并规则
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---

# 开始使用配置文件合并规则 {#getting-started-with-profile-merge-rules}

建立 [!UICONTROL Profile Merge Rules]，檢閱並完成本節所述每個程式中的步驟。

<!-- merge-rules-start.xml -->

## 建立跨裝置資料來源 {#create-data-source}

若要建立跨裝置資料來源，請前往 **[!UICONTROL Audience Data > Data Sources > Add New]** 並完成此處所述每個區段的步驟。 需要管理員許可權才能建立或編輯跨裝置資料來源。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>另請參閱 [資料來源設定和功能表選項](../datasources-list-and-settings.md#settings-menu-options) 這些不同控制項的說明。

## 資料來源詳細資料 {#details}

若要完成 [!UICONTROL Data Source Details] 區段：

1. 為資料來源命名。
2. *（可選）* 說明資料來源。 簡潔的說明可協助您定義資料來源的角色或用途。
3. 提供整合程式碼。 整合程式碼是您為此資料來源擁有的唯一ID。
4. 在 **[!UICONTROL ID Type]** 清單，選取 **[!UICONTROL Cross Device]**.
5. 在 **[!UICONTROL ID Definition]** 清單中，選取定義資料來源型別的選項。 选项包括：
   * **[!UICONTROL Person]**：定義單一人員的ID。 此ID可對應至多個 [!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**：定義一組人員的ID。 此ID可對應至多個 [!DNL Audience Manager] ID。

## 数据导出控制 {#export-controls}

[資料匯出控制](../data-export-controls.md) 是選擇性分類規則，可套用至資料來源和目的地。 当该操作违反数据隐私或使用协议时，它们会阻止您将数据发送到目标。 如果您不使用，請略過本節 [!UICONTROL Data Export Controls].

## 数据来源设置 {#settings}

[!UICONTROL Data Source Settings] 區段提供多個選項，但這2個選項對於建立跨裝置資料來源很重要：

* **[!UICONTROL Use as Authenticated Profile]**：預設為選取，此設定可讓您建置 [!UICONTROL Profile Merge Rule] 使用您自己的已驗證資料。

* **[!UICONTROL Use as a Device Graph]**：此控制項僅適用於列為資料提供者的帳戶。 選取此核取方塊會將您的資料來源建立為裝置圖表，並讓您與其他人共用 [!DNL Audience Manager] 客戶。 使用您的 [!DNL Audience Manager] 諮詢程式，以設定為資料提供者，並指定哪些客戶可使用 [!UICONTROL Data Source] 應該與共用。 您的顧問將透過內部布建程式布建您的帳戶和裝置圖表共用。

* **[!UICONTROL Data retention for inactive Customer IDs]**：此控制項可讓您設定非作用中客戶ID的資料保留期間。 这可确定在上次查看 Audience Manager 平台上的客户 Id 后，Audience Manager 将其保留在数据库中的时间。 默认值为24个月（720天）。 您可以设置的最小值为1个月，最大值为5年。 请注意，我们将所有月份计算为30天。 Audience Manager會根據您為非作用中客戶ID設定的資料保留，執行每週刪除一次非作用中客戶ID的程式。

與這些設定相關聯的文字欄位可讓您重新命名 [!UICONTROL Data Source] 別名為，出現在 [設定檔合併規則選項](merge-rule-definitions.md). 例如，如果您將別名新增至 **[!UICONTROL Use as Authenticated Profile]**，該名稱會出現在 [!UICONTROL Authenticated Profile Options] 清單。 如果您將別名新增至 **[!UICONTROL Use as a Device Graph]**，該名稱會出現在 [!UICONTROL Device Options] 清單。

## 建立設定檔合併規則 {#create-profile-merge-rule}

若要创建 [!UICONTROL Profile Merge Rule] ，请转到 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** 并完成此处所述的每个部分的步骤。

设置跨设备数据源后，您最多可以创建3个合并规则。 如果您注册基于人员的目标 ](../destinations/people-based-destinations-overview.md) ，则可以访问第四个 [ 配置文件合并规则（ [!UICONTROL All Cross-Device Profiles] ）。

创建、编辑或删除规则需要管理员权限。 所有用户都可以视图和使用现有 [!UICONTROL Profile Merge Rules] 的。

<!-- create-profile-merge-rule.xml -->

**先决条件：** 版本 a [!UICONTROL Profile Merge Rule] 需要跨设备数据源。 请参阅 [ 创建数据来源 ](../manage-datasources.md#create-data-source) 。

>[!TIP]
>
>另請參閱 [定義的設定檔合併規則選項](merge-rule-definitions.md) 這些不同控制項的說明。

## 基本信息 {#basic-info}

若要完成 [!UICONTROL Basic Information] 區段：

1. 為命名 [!UICONTROL Profile Merge Rule].
2. *（可選）* 說明 [!UICONTROL Profile Merge Rule]. 簡潔的說明可協助您定義規則的角色或用途。
3. *（可选）* 选择 **[!UICONTROL Set as default]** 是否要将其设为默认值 [!UICONTROL Profile Merge Rule] 。 新区段会自动与默认规则关联。

## 数据导出控制 {#data-export-controls}

[資料匯出控制](../data-export-controls.md) 是選擇性分類規則，可套用至 [!UICONTROL Profile Merge Rule]. 當該動作違反資料隱私權或使用協定時，它們會阻止您傳送資料至目的地。 如果您不使用，請略過本節 [!UICONTROL Data Export Controls].

## 設定檔合併規則設定 {#profile-merge-rule-setup}

要完成 [!UICONTROL Proflie Merge Rule Setup] 章节，请执行以下操作：

1. **[!UICONTROL Authenticated Option]**&#x200B;选择。选项包括：
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 选择一个 **[!UICONTROL Authenticated Profile Option]** （最多3个）。 这些是以前创建的 [ 跨设备数据源 ](merge-rules-start.md) 。
3. 选择 **[!UICONTROL Device Option]**. 选项包括：
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. 单击 **[!UICONTROL Save]**.

### 使用跨裝置ID作為使用者ID金鑰的Adobe Campaign目的地考量事項 {#considerations}

2019年底，我們發佈了一系列設定檔合併規則增強功能，以提高使用跨裝置ID產生批次檔案的準確性。 從2020年3月16日星期一開始，您的Audience Manager執行個體將嚴格遵循這些增強功能。 因此，使用跨裝置ID對應至目的地的區段，在某些設定檔合併規則設定中將停止產生匯出。

為確保您的Audience Manager執行個體與使用跨裝置ID的目的地(例如Adobe Campaign)之間正確整合，請確保您符合以下要求：

1. 檢閱對應至您Adobe Campaign宣告ID目的地的區段所使用的設定檔合併規則。 設定檔合併規則必須使用 [!UICONTROL Last Authenticated Profile] 選項，以便所有已驗證的設定檔都可以包含在匯出中。 如果您的設定檔合併規則使用其他選項，請將其切換為 [!UICONTROL Last Authenticated Profile].
2. 在「設定檔合併規則」設定中選取「Adobe Campaign宣告ID」資料來源。

>[!NOTE]
>
> 如果您已達到數量上限，請 [!UICONTROL Profile Merge Rules] 如需根據上述指示進行設定的協助，請聯絡客戶服務。

## 設定合併規則程式碼 {#configure-merge-rule-code}

請依照下列指示設定 [!UICONTROL Adobe Experience Platform Identity Service]， [!UICONTROL DIL]，和行動裝置 [!DNL SDK] 用於合併規則的程式碼。

<!-- merge-rules-configure-code.xml -->

### 先决条件

您必須設定 [跨裝置資料來源](#create-data-source) 和 [設定檔合併規則](#create-profile-merge-rule) *早於* 完成這些程式。

## 適用於Adobe Experience Platform Identity Service客戶 {#id-service-customers}

此 [!UICONTROL Adobe Experience Platform Identity Service] 和最新版本的 [DIL](../../dil/dil-overview.md) 使用時建議使用 [!UICONTROL Profile Merge Rules]. 不過，您不必使用 [!UICONTROL Adobe Experience Platform Identity Service] 以使用此功能。 如果您只使用 [!UICONTROL DIL]，請參閱 [舊版DIL區段](#legacy-dil) 下方的。

### 設定Set Customer ID函式

使用時 [!UICONTROL Adobe Experience Platform Identity Service]，則 `setCustomerIDs` 函式將宣告ID傳遞至 [!DNL Audience Manager]. 若要使用設定檔合併規則，您必須修改 `setCustomerIDs` 以使用建立跨裝置資料來源時指定的整合代碼。 例如，假設您已使用整合代碼建立跨裝置資料來源 `my_datasource_ic`. 若要傳入宣告的ID，您可以將整合程式碼新增至訪客ID函式，如下列修改後的程式碼範例所示。

#### 一般程式碼範例

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 修改後的程式碼範例

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

如需詳細資訊，請參閱 [建立跨裝置資料來源](#create-data-source) 和 [客戶ID和驗證狀態](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### 設定 `DIL.create` 函式

最新版本的 [!UICONTROL DIL] 現在自動選取 [!UICONTROL declared ID] 從 `visitorService` 函式於 `DIL.create` (請參閱 [宣告ID變數](../declared-ids.md#declared-id-variables))。 檢查您的 `DIL.create` 函式來確定已正確設定，如下列程式碼範例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在命名空间键值对中， `*` MCORG `*` 变量是您 [!DNL Experience Cloud] 的组织 ID。 如果您沒有此ID，可以在 [!UICONTROL Administration] 部分 [!DNL Experience Cloud] 儀表板。 您需要管理员权限才能视图此功能板。 请参阅 [ 管理：核心服务 ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 。

### 設定SDK

請參閱 [設定SDK](#configure-sdks-legacy-dil) 區段底下。

## 舊版DIL {#legacy-dil}

如果您沒有使用 [!DNL Adobe Experience Platform Identity Service] 然而，您確實應該這麼做。 但是，我們瞭解移轉至新程式碼需要審慎的思考和測試。 在這些情況下，請檢視您的 `DIL.create` 函式來確定已正確設定，如下列程式碼範例所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

有关更多信息，请参阅声明的 ID 变量 ](../declared-ids.md#declared-id-variables) 中 [ 的旧版 [!UICONTROL DIL] 部分。

### 配置 Sdk {#configure-sdks-legacy-dil}

檢查以下專案的方法： [!DNL SDK] 可讓您傳遞的程式碼 [!UICONTROL declared IDs] 從 [!DNL Android] 和 [!DNL iOS] 行動裝置。 的變數名稱 [!DNL Android] 和 [!DNL iOS] 程式碼程式庫是相同的：

* `dpid`：跨裝置資料來源識別碼。
* `dpuuid`：此 [!UICONTROL declared ID] （即使用者ID）。

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 设备类型 </th> 
   <th colname="col2" class="entry"> 方法 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>语法：</b> </p> <p> <pre> 公用靜態void setDpidAndDpuuid（字串dpid，字串dpuuid）； </pre> </p> <p> <b>示例:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid"，"myDpuuid")； </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>语法：</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>示例:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

另請參閱 [適用於Android的Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) 和 [適用於iOS的Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [创建数据源](../manage-datasources.md#create-data-source)

