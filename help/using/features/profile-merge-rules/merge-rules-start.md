---
description: 要创建用户档案合并规则，请查看并完成本节中介绍的每个过程中的步骤。
seo-description: 要创建用户档案合并规则，请查看并完成本节中介绍的每个过程中的步骤。
seo-title: 用户档案合并规则入门
solution: Audience Manager
title: 用户档案合并规则入门
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
translation-type: tm+mt
source-git-commit: 56a9626b1fa77926bdc31ef72b058d2aa9b58f43
workflow-type: tm+mt
source-wordcount: '1327'
ht-degree: 1%

---


# 用户档案合并规则入门 {#getting-started-with-profile-merge-rules}

要创建、 [!UICONTROL Profile Merge Rules]查看并完成本节中介绍的每个过程中的步骤，请执行以下操作。

<!-- merge-rules-start.xml -->

## 创建跨设备数据源 {#create-data-source}

要创建跨设备数据源，请转到并完 **[!UICONTROL Audience Data > Data Sources > Add New]** 成此处介绍的每个部分的步骤。 创建或编辑跨设备数据源需要管理员权限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>有关 [这些不同控件的说明](../datasources-list-and-settings.md#settings-menu-options) ，请参阅数据源设置和菜单选项。

## 数据源详细信息 {#details}

要完成该部 [!UICONTROL Data Source Details] 分：

1. 命名数据源。
2. *(可选* )描述数据源。 简洁的描述可帮助您定义数据源的角色或用途。
3. 提供集成代码。 集成代码是您自己的、此数据源的唯一ID。
4. 在列表 **[!UICONTROL ID Type]** 中，选择 **[!UICONTROL Cross Device]**。
5. 在列表 **[!UICONTROL ID Definition]** 中，选择定义数据源类型的选项。 选项包括：
   * **[!UICONTROL Person]**: 定义单个人员的ID。 此ID可以映射到多个 [!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**: 定义一组人员的ID。 此ID可以映射到多个 [!DNL Audience Manager] ID。

## 数据导出控制 {#export-controls}

[数据导出控件](../data-export-controls.md) (Data Export Controls)是可应用于数据源和目标的可选分类规则。 它们可防止您在数据隐私或使用协议违反数据隐私或使用协议时向目标发送数据。 如果不使用，请跳过此部 [!UICONTROL Data Export Controls]分。

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] 部分提供了多个选项，但这2个选项对于创建跨设备数据源很重要：

* **[!UICONTROL Use as Authenticated Profile]**: 默认情况下，此设置允许您使用自己的 [!UICONTROL Profile Merge Rule] 已验证数据构建一个。

* **[!UICONTROL Use as a Device Graph]**: 此控件仅对作为数据提供者列出的帐户可用。 选中此复选框将创建设备图形形式的数据源，并允许您与其他客户共 [!DNL Audience Manager] 享它。 与顾问 [!DNL Audience Manager] 合作，将其设置为数据提供者并指定应与哪 [!UICONTROL Data Source] 些客户共享。 您的顾问将通过内部配置流程配置您的帐户和设备图形共享。

* **[!UICONTROL Data retention for inactive Customer IDs]**: 此控件允许您为非活动的客户ID设置数据保留期。 这决定了受众管理器在受众管理器平台上最后一次看到客户ID后，客户ID在我们的数据库中保留多长时间。 默认值为24个月（720天）。 您可以设置的最小值为1个月，最大值为5年。 请注意，我们把所有月份都算作30天。 受众经理会根据您为非活动客户ID设置的数据保留情况，每周删除不活动客户ID一次的流程。

通过与这些设置关联的文本字段，您可以使 [!UICONTROL Data Source] 用“用户档案合并规则”选项中显 [示的别名重命名](merge-rule-definitions.md)。 例如，如果向添加别名， **[!UICONTROL Use as Authenticated Profile]**&#x200B;该名称将显示在列表 [!UICONTROL Authenticated Profile Options] 中。 如果向中添加别名， **[!UICONTROL Use as a Device Graph]**&#x200B;则该名称会显示在 [!UICONTROL Device Options] 列表中。

## 创建用户档案合并规则 {#create-profile-merge-rule}

要创建 [!UICONTROL Profile Merge Rule]，请转 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** 到并完成此处描述的每个部分的步骤。

在设置跨设备数据源后，最多可创建3个合并规则。 如果您注册了基于人员的目标，您[!UICONTROL All Cross-Device Profiles]可以访问第4个用户档案 [合并规则()](../destinations/people-based-destinations-overview.md)。

创建、编辑或删除规则需要管理员权限。 所有用户都可以视图和使用现有 [!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**先决条件：** 需要跨设备数据源才能构建 [!UICONTROL Profile Merge Rule]。 请参 [阅创建数据源](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>有关 [这些不同控件的说明](merge-rule-definitions.md) ，请参阅定义的用户档案合并规则选项。

## 基本信息 {#basic-info}

要完成该部 [!UICONTROL Basic Information] 分：

1. 命名 [!UICONTROL Profile Merge Rule]。
2. *(可选* )描述 [!UICONTROL Profile Merge Rule]。 简洁的描述可帮助您定义规则的角色或用途。
3. *(可选* )如 **[!UICONTROL Set as default]** 果要将其设为默认值，请选择 [!UICONTROL Profile Merge Rule]。 新区段会自动与默认规则关联。

## 数据导出控制 {#data-export-controls}

[数据导出控件](../data-export-controls.md) (Data Export Controls)是可应用于您的可选分类规 [!UICONTROL Profile Merge Rule]则。 它们可防止您在数据隐私或使用协议违反数据隐私或使用协议时向目标发送数据。 如果不使用，请跳过此部 [!UICONTROL Data Export Controls]分。

## 用户档案合并规则设置 {#profile-merge-rule-setup}

要完成该部 [!UICONTROL Proflie Merge Rule Setup] 分：

1. 选择一个 **[!UICONTROL Authenticated Option]**。 选项包括：
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 选择 **[!UICONTROL Authenticated Profile Option]** （最多3，最大值）。 这些是您 [之前创建的](merge-rules-start.md) 跨设备数据源。
3. 选择 **[!UICONTROL Device Option]**. 选项包括：
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 单击 **[!UICONTROL Save]**.

### 使用跨设备ID作为用户ID密钥的Adobe Campaign目标的注意事项 {#considerations}

在2019年末，我们发布了一系列用户档案合并规则增强功能，以提高使用跨设备ID生成的批处理文件的准确性。 从2020年3月16日星期一开始，您的受众管理器实例将严格遵循这些增强功能。 通常，使用跨设备ID映射到目标的区段将停止在某些用户档案合并规则配置中生成导出。

要确保使用跨设备ID(如受众)在Adobe Campaign管理器实例与目标之间正确集成，请确保满足以下要求：

1. 查看映射到您的用户档案声明ID目标的Adobe Campaign段使用的合并规则。 用户档案合并规则必须使用该选 [!UICONTROL Last Authenticated Profile] 项，因此所有经过身份验证的用户档案都可以包含在导出中。 如果您的用户档案合并规则使用其他选项，请将其切换为 [!UICONTROL Last Authenticated Profile]。
2. 在“Adobe Campaign合并规则”设置中选择用户档案声明ID数据源。

>[!NOTE]
>
> 我们已将用户档案合并规则限制为1，以便您为映射到Adobe Campaign声明ID目标的段创建专用的用户档案合并规则，而不更改其他用例的用户档案合并规则。

## 配置合并规则代码 {#configure-merge-rule-code}

按照以下说明设置 [!UICONTROL Adobe Experience Platform Identity Service]、 [!UICONTROL DIL]和移动 [!DNL SDK] 代码以使用合并规则。

<!-- merge-rules-configure-code.xml -->

### 先决条件

在完成这些过 [程之前，必须设置](#create-data-source)[跨设备数据源](#create-profile-merge-rule)*和用户档案合* 并规则。

## 对于Adobe Experience Platform Identity Service客户 {#id-service-customers}

使 [!UICONTROL Adobe Experience Platform Identity Service] 用DIL时，建 [议使用](../../dil/dil-overview.md) DIL和最新版本 [!UICONTROL Profile Merge Rules]。 但是，您不必使用该 [!UICONTROL Adobe Experience Platform Identity Service] 功能即可使用。 如果您只是在使 [!UICONTROL DIL]用，请参 [阅下面的旧DIL](#legacy-dil) 部分。

### 配置设置客户ID功能

使用时，函 [!UICONTROL Adobe Experience Platform Identity Service]数将 `setCustomerIDs` 声明的ID传递给 [!DNL Audience Manager]。 要使用用户档案合并规则，您必须修改以 `setCustomerIDs` 使用创建跨设备数据源时指定的集成代码。 例如，假设您已使用集成代码创建了跨设备数据源 `my_datasource_ic`。 要传递声明的ID，您应将集成代码添加到访客ID函数，如以下修改的代码示例所示。

#### 通用代码示例

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 修改代码示例

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

有关详细信息， [请参阅创建跨设备数据源](#create-data-source) 、 [客户ID和身份验证状态](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)。

### 配置函 `DIL.create` 数

现在，最新版本 [!UICONTROL DIL] 自动从中的 [!UICONTROL declared ID] 函 `visitorService` 数中选取 `DIL.create` (请参阅 [声明的ID变量](../declared-ids.md#declared-id-variables))。 检查您 `DIL.create` 的函数，确保正确设置，如下面的代码示例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在命名空间键值对中，MCORG `*`变量`*` 是您的组 [!DNL Experience Cloud] 织ID。 如果您没有此ID，您可以在仪表板的 [!UICONTROL Administration] 部分找到 [!DNL Experience Cloud] 它。 您需要管理员权限才能视图此仪表板。 See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

### 配置SDK

请参阅下 [面的配置](#configure-sdks-legacy-dil) SDK部分。

## 传统DIL {#legacy-dil}

如果你还没用， [!DNL Adobe Experience Platform Identity Service] 你真的应该用。 但是，我们理解，转到新代码需要仔细思考和测试。 在这些情况下，请检 `DIL.create` 查您的函数，确保正确设置，如下面的代码示例所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

有关详细信息，请参阅Declared ID [!UICONTROL DIL] Variables中 [的旧版部分](../declared-ids.md#declared-id-variables)。

### 配置SDK {#configure-sdks-legacy-dil}

检查代码中的 [!DNL SDK] 方法，让您从移动 [!UICONTROL declared IDs] 设备 [!DNL Android] 和移动设备 [!DNL iOS] 传递。 库和代码库 [!DNL Android] 的 [!DNL iOS] 变量名称相同：

* `dpid`: 跨设备数据源ID。
* `dpuuid`: ( [!UICONTROL declared ID] 即用户ID)。

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>语法：</b> </p> <p> <pre> 公共静态void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>示例：</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
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

另请参阅Android [的受众管理器方法和iOS](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html)[的受众管理器方法](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html)。

>[!MORELIKETHIS]
>
>* [创建数据源](../manage-datasources.md#create-data-source)

