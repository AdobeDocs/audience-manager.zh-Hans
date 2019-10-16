---
description: 要创建配置文件合并规则，请查看并完成本节中介绍的每个步骤。
seo-description: 要创建配置文件合并规则，请查看并完成本节中介绍的每个步骤。
seo-title: 个人资料合并规则入门
solution: Audience Manager
title: 个人资料合并规则入门
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 个人资料合并规则入门 {#getting-started-with-profile-merge-rules}

要创建、 [!UICONTROL Profile Merge Rules]查看并完成本节所述每个步骤中的步骤，请执行以下操作。

<!-- merge-rules-start.xml -->

## 创建跨设备数据源 {#create-data-source}

要创建跨设备数据源，请转到并完 **[!UICONTROL Audience Data > Data Sources > Add New]** 成此处描述的每个部分的步骤。 创建或编辑跨设备数据源需要管理员权限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>有关 [这些不同控件的说明，请参阅数据源设置和菜单选项](../datasources-list-and-settings.md#settings-menu-options) 。

## 数据源详细信息 {#details}

要完成此部 [!UICONTROL Data Source Details] 分，请执行以下操作：

1. 命名数据源。
2. *（可选）* ，描述数据源。 简明的描述可帮助您定义数据源的角色或用途。
3. 提供集成代码。 集成代码是您自己的、此数据源的唯一ID。
4. 在列表 **[!UICONTROL ID Type]** 中，选择 **[!UICONTROL Cross Device]**。
5. 在列表 **[!UICONTROL ID Definition]** 中，选择定义数据源类型的选项。 选项包括：
   * **[!UICONTROL Person]**:定义单个人的ID。 此ID可以映射到多个 [!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**:定义一组人员的ID。 此ID可以映射到多个 [!DNL Audience Manager] ID。

## 数据导出控制 {#export-controls}

[数据导出控件](../data-export-controls.md) (Data Export Controls)是可应用于数据源和目标的可选分类规则。 当该操作违反数据隐私或使用协议时，它们会阻止您将数据发送到目标。 如果不使用，请跳过此部分 [!UICONTROL Data Export Controls]。

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] 部分提供了多个选项，但这两个选项对于创建跨设备数据源很重要：

* **[!UICONTROL Use as Authenticated Profile]**:默认情况下，此设置允许您使用您自己的实 [!UICONTROL Profile Merge Rule] 名数据构建一个。

* **[!UICONTROL Use as a Device Graph]**:此控件仅对作为数据提供者列出的帐户可用。 选中此复选框将创建设备图形形式的数据源，并允许您与其他客户共 [!DNL Audience Manager] 享它。 与您的顾 [!DNL Audience Manager] 问一起设置为数据提供者，并指定应与哪些客 [!UICONTROL Data Source] 户共享此信息。 您的顾问将通过内部配置流程配置您的帐户和设备图形共享。

* **[!UICONTROL Data retention for inactive Customer IDs]**:此控件允许您为不活动的客户ID设置数据保留期。 这决定了Audience manager在Audience manager平台上上次查看客户ID后，在我们的数据库中保留这些ID的时间。 默认值为24个月（720天）。 您可以设置的最小值为1个月，最大值为5年。 请注意，我们将所有月份计为30天。 Audience manager会根据您为非活动客户ID设置的数据保留情况，运行一个每周删除不活动客户ID一次的流程。

通过与这些设置关联的文本字段，您可以使用在“配置文 [!UICONTROL Data Source] 件合并规则”选项中显示 [的别名重命名](merge-rule-definitions.md)。 例如，如果向添加别名， **[!UICONTROL Use as Authenticated Profile]**&#x200B;则该名称会显示在列 [!UICONTROL Authenticated Profile Options] 表中。 如果向中添加别名， **[!UICONTROL Use as a Device Graph]**&#x200B;则该名称会显示在列 [!UICONTROL Device Options] 表中。

>[!MORE_LIKE_THIS]
>
>* [创建数据源](../manage-datasources.md#create-data-source)


## 创建配置文件合并规则 {#create-profile-merge-rule}

要创建 [!UICONTROL Profile Merge Rule]，请转到并 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** 完成此处描述的每个部分的步骤。 在设置跨设备数据源后，最多可创建3个合并规则。 创建、编辑或删除规则需要管理员权限。 所有用户都可以查看和使用现有 [!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**** 先决条件：需要跨设备数据源才能构建 [!UICONTROL Profile Merge Rule]。 请参 [阅创建数据源](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>有关这 [些不同控件的说明，请参阅](merge-rule-definitions.md) “配置文件合并规则选项定义”。

## 基本信息 {#basic-info}

要完成此部 [!UICONTROL Basic Information] 分，请执行以下操作：

1. 命名 [!UICONTROL Profile Merge Rule]。
2. *（可选）* ，请描述 [!UICONTROL Profile Merge Rule]。 简明的描述可帮助您定义规则的角色或用途。
3. *（可选）* ，如果 **[!UICONTROL Set as default]** 要将其设为默认值，请选择此选项 [!UICONTROL Profile Merge Rule]。 新区段会自动与默认规则关联。

## 数据导出控制 {#data-export-controls}

[数据导出控件](../data-export-controls.md) (Data Export Controls)是可应用于您的可选分类规则 [!UICONTROL Profile Merge Rule]。 当该操作违反数据隐私或使用协议时，它们会阻止您将数据发送到目标。 如果不使用，请跳过此部分 [!UICONTROL Data Export Controls]。

## 配置文件合并规则设置 {#profile-merge-rule-setup}

要完成此部 [!UICONTROL Proflie Merge Rule Setup] 分，请执行以下操作：

1. 选择 **[!UICONTROL Authenticated Option]**。 选项包括：
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 选择 **[!UICONTROL Authenticated Profile Option]** （最多3，最大值）。 这些是您 [之前创建的跨设备](merge-rules-start.md) 数据源。
3. 选择 **[!UICONTROL Device Option]**. 选项包括：
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 单击 **[!UICONTROL Save]**.

## 配置合并规则代码 {#configure-merge-rule-code}

按照以下说明设置 [!UICONTROL Experience Cloud ID Service]、 [!UICONTROL DIL]和移动 [!DNL SDK] 代码以使用合并规则。

<!-- merge-rules-configure-code.xml -->

### 先决条件

完成这些过程之 [前，必须设置跨设备数据源](#create-data-source)[和配置文](#create-profile-merge-rule) 件合并规则 ** 。

## 对于Experience Cloud ID服务客户 {#id-service-customers}

使 [!UICONTROL Experience Cloud ID Service] 用时建议使用 [DIL](../../dil/dil-overview.md) 和最新版本 [!UICONTROL Profile Merge Rules]。 但是，您不必使用该 [!UICONTROL Experience Cloud ID Service] 功能即可使用。 如果您只是在使用，请 [!UICONTROL DIL]参阅下面的 [传统DIL部分](#legacy-dil) 。

### 配置“设置客户ID”功能

使用时，函 [!UICONTROL Experience Cloud ID Service]数将声 `setCustomerIDs` 明的ID传递给 [!DNL Audience Manager]。 要使用配置文件合并规则，您必须进行修 `setCustomerIDs` 改以使用在创建跨设备数据源时指定的集成代码。 例如，假设您使用集成代码创建了一个跨设备数据源 `my_datasource_ic`。 要传递已声明的ID，您应将集成代码添加到访客ID函数，如下面修改的代码示例所示。

#### 通用代码示例

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 修改的代码示例

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

有关详细信息，请 [参阅创建跨设备数据源](#create-data-source) 、客 [户ID和身份验证状态](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html)。

### 配置函 `DIL.create` 数

现在，最新版本 [!UICONTROL DIL] 会自动从中的 [!UICONTROL declared ID] 函数 `visitorService` 中选取( `DIL.create` 请参阅 [Declared ID Variables](../declared-ids.md#declared-id-variables))。 检查您 `DIL.create` 的函数，确保正确设置，如下面的代码示例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在命名空间键值对中， `*`MCORG`*` 变量是您的组 [!DNL Experience Cloud] 织ID。 如果您没有此ID，则可以在仪表板的部分 [!UICONTROL Administration] 找到该 [!DNL Experience Cloud] ID。 您需要管理员权限才能查看此功能板。 See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### 配置SDK

请参阅下 [面的配置](#configure-sdks-legacy-dil) SDK部分。

## 传统DIL {#legacy-dil}

如果你还没用， [!DNL Experience Cloud ID Service] 你真的应该用。 但是，我们理解，要转到新代码，需要仔细思考和测试。 在这些情况下，请检查 `DIL.create` 您的函数，以确保正确设置，如下面的代码示例中所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

有关详细信息，请参阅“声明的ID变 [!UICONTROL DIL] 量”中的 [旧版部分](../declared-ids.md#declared-id-variables)。

### 配置SDK {#configure-sdks-legacy-dil}

检查代码中允许 [!DNL SDK] 您从移动设备传递 [!UICONTROL declared IDs] 的 [!DNL Android] 方法和 [!DNL iOS] 移动设备。 与代码库的变 [!DNL Android] 量名 [!DNL iOS] 称相同：

* `dpid`:跨设备数据源ID。
* `dpuuid`:( [!UICONTROL declared ID] 即用户ID)。

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>语法：</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>示例：</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>语法：</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>示例：</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

另请参阅适 [用于Android的Audience Manager方法](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) ，以 [及适用于iOS的Audience Manager方法](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html)。
