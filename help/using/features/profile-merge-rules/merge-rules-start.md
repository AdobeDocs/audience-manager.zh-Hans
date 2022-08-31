---
description: 要创建配置文件合并规则，请查看并完成本节中描述的每个步骤中的步骤。
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

创建 [!UICONTROL Profile Merge Rules]，查看并完成本节所述每个步骤中的步骤。

<!-- merge-rules-start.xml -->

## 创建跨设备数据源 {#create-data-source}

要创建跨设备数据源，请转到 **[!UICONTROL Audience Data > Data Sources > Add New]** 并完成此处介绍的每个部分的步骤。 创建或编辑跨设备数据源需要管理员权限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>请参阅 [数据源设置和菜单选项](../datasources-list-and-settings.md#settings-menu-options) 以了解这些不同控件的描述。

## 数据源详细信息 {#details}

完成 [!UICONTROL Data Source Details] 部分：

1. 命名数据源。
2. *（可选）* 描述数据源。 简要描述可帮助您定义数据源的角色或用途。
3. 提供集成代码。 集成代码是您自己的此数据源唯一ID。
4. 在 **[!UICONTROL ID Type]** 列表，选择 **[!UICONTROL Cross Device]**.
5. 在 **[!UICONTROL ID Definition]** 列表中，选择一个用于定义数据源类型的选项。 选项包括：
   * **[!UICONTROL Person]**:定义单个人员的ID。 此ID可映射到多个 [!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**:定义一组人员的ID。 此ID可映射到多个 [!DNL Audience Manager] ID。

## 数据导出控制 {#export-controls}

[数据导出控制](../data-export-controls.md) 是可选的分类规则，您可以将其应用于数据源和目标。 当该操作违反数据隐私或使用协议时，它们会阻止您将数据发送到目标。 如果您不使用 [!UICONTROL Data Export Controls].

## 数据源设置 {#settings}

[!UICONTROL Data Source Settings] 部分提供了多个选项，但是这两个选项对于创建跨设备数据源非常重要：

* **[!UICONTROL Use as Authenticated Profile]**:默认情况下，此设置允许您生成 [!UICONTROL Profile Merge Rule] 使用您自己的经过身份验证的数据。

* **[!UICONTROL Use as a Device Graph]**:此控件仅适用于列为数据提供程序的帐户。 选中此复选框会将您的数据源创建为设备图，并允许您与其他设备共享该数据源 [!DNL Audience Manager] 客户。 使用 [!DNL Audience Manager] 顾问，以设置为数据提供商，并指定此 [!UICONTROL Data Source] 应与共享。 您的顾问将通过内部配置流程来配置您的帐户和设备图共享。

* **[!UICONTROL Data retention for inactive Customer IDs]**:此控件允许您为不活动的客户ID设置数据保留期限。 这可确定Audience Manager在客户ID最后一次在Audience Manager平台上看到后，将其保留在我们的数据库中多长时间。 默认值为24个月（720天）。 您可设置的最小值为1个月，最大值为5年。 请注意，我们把所有月份都算作30天。 Audience Manager会根据您为不活动客户ID设置的数据保留，每周运行一次删除不活动客户ID的流程。

通过与这些设置关联的文本字段，您可以重命名 [!UICONTROL Data Source] 的别名 [配置文件合并规则选项](merge-rule-definitions.md). 例如，如果向 **[!UICONTROL Use as Authenticated Profile]**，则该名称会显示在 [!UICONTROL Authenticated Profile Options] 列表。 如果向 **[!UICONTROL Use as a Device Graph]**，则该名称会显示在 [!UICONTROL Device Options] 列表。

## 创建配置文件合并规则 {#create-profile-merge-rule}

创建 [!UICONTROL Profile Merge Rule]，转到 **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** 并完成此处介绍的每个部分的步骤。

在设置跨设备数据源后，最多可以创建3个合并规则。 您可以访问第4个配置文件合并规则([!UICONTROL All Cross-Device Profiles]) [基于人员的目标](../destinations/people-based-destinations-overview.md).

创建、编辑或删除规则时需要管理员权限。 所有用户都可以查看和使用现有 [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**先决条件：** 需要跨设备数据源才能构建 [!UICONTROL Profile Merge Rule]. 请参阅 [创建数据源](../manage-datasources.md#create-data-source).

>[!TIP]
>
>请参阅 [定义的配置文件合并规则选项](merge-rule-definitions.md) 以了解这些不同控件的描述。

## 基本信息 {#basic-info}

完成 [!UICONTROL Basic Information] 部分：

1. 将 [!UICONTROL Profile Merge Rule].
2. *（可选）* 描述 [!UICONTROL Profile Merge Rule]. 简要描述可帮助您定义规则的角色或用途。
3. *（可选）* 选择 **[!UICONTROL Set as default]** 如果要将其设为默认值 [!UICONTROL Profile Merge Rule]. 新区段会自动与默认规则关联。

## 数据导出控制 {#data-export-controls}

[数据导出控制](../data-export-controls.md) 是可选的分类规则，您可以将 [!UICONTROL Profile Merge Rule]. 当该操作违反数据隐私或使用协议时，它们会阻止您将数据发送到目标。 如果您不使用 [!UICONTROL Data Export Controls].

## 配置文件合并规则设置 {#profile-merge-rule-setup}

完成 [!UICONTROL Proflie Merge Rule Setup] 部分：

1. 选择 **[!UICONTROL Authenticated Option]**. 选项包括：
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 选择 **[!UICONTROL Authenticated Profile Option]** （最多3个，最多3个）。 这些是 [跨设备数据源](merge-rules-start.md) 您之前已创建。
3. 选择 **[!UICONTROL Device Option]**. 选项包括：
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. 单击 **[!UICONTROL Save]**.

### 有关使用跨设备ID作为用户ID键的Adobe Campaign目标的注意事项 {#considerations}

2019年末，我们发布了一系列配置文件合并规则增强功能，以提高使用跨设备ID生成的批处理文件的准确性。 从2020年3月16日星期一开始，您的Audience Manager实例将严格遵循这些增强功能。 通常，在某些配置文件合并规则配置中，使用跨设备ID映射到目标的区段将停止生成导出。

要确保使用跨设备ID(如Adobe Campaign)在Audience Manager实例与目标之间进行正确集成，请确保满足以下要求：

1. 查看映射到Adobe Campaign声明的ID目标的区段所使用的配置文件合并规则。 配置文件合并规则必须使用 [!UICONTROL Last Authenticated Profile] 选项，以便导出中可以包含所有经过身份验证的用户档案。 如果您的配置文件合并规则使用了其他选项，请将其切换为 [!UICONTROL Last Authenticated Profile].
2. 在配置文件合并规则设置中选择Adobe Campaign声明的ID数据源。

>[!NOTE]
>
> 如果已达到 [!UICONTROL Profile Merge Rules] 并且需要根据上述说明配置这些组件的帮助，请联系客户关怀团队。

## 配置合并规则代码 {#configure-merge-rule-code}

按照以下说明设置 [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL]和移动设备 [!DNL SDK] 用于与合并规则一起使用的代码。

<!-- merge-rules-configure-code.xml -->

### 先决条件

您必须设置 [跨设备数据源](#create-data-source) 和 [配置文件合并规则](#create-profile-merge-rule) *之前* 完成这些步骤。

## 对于Adobe Experience Platform Identity Service客户 {#id-service-customers}

的 [!UICONTROL Adobe Experience Platform Identity Service] 和 [DIL](../../dil/dil-overview.md) 在使用时建议使用 [!UICONTROL Profile Merge Rules]. 但是，您不必使用 [!UICONTROL Adobe Experience Platform Identity Service] 来使用此功能。 如果你只是使用 [!UICONTROL DIL]，请参阅 [旧版DIL部分](#legacy-dil) 下。

### 配置Set Customer ID函数

使用 [!UICONTROL Adobe Experience Platform Identity Service], `setCustomerIDs` 函数将声明的ID传递到 [!DNL Audience Manager]. 要使用配置文件合并规则，您必须修改 `setCustomerIDs` 使用在创建跨设备数据源时指定的集成代码。 例如，假设您已使用集成代码创建了跨设备数据源 `my_datasource_ic`. 要传入声明的ID，您需要将集成代码添加到访客ID函数，如下面修改的代码示例中所示。

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

有关更多信息，请参阅 [创建跨设备数据源](#create-data-source) 和 [客户ID和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### 配置 `DIL.create` 函数

的最新版本 [!UICONTROL DIL] 现在自动地 [!UICONTROL declared ID] 从 `visitorService` 函数 `DIL.create` (请参阅 [声明的ID变量](../declared-ids.md#declared-id-variables))。 检查 `DIL.create` 函数，以确保正确设置此设置，如以下代码示例中所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在命名空间键值对中， `*`MCORG`*` 变量 [!DNL Experience Cloud] 组织ID。 如果您没有此ID，可以在 [!UICONTROL Administration] 部分 [!DNL Experience Cloud] 功能板。 您需要管理员权限才能查看此功能板。 请参阅 [管理：核心服务](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### 配置SDK

请参阅 [配置SDK](#configure-sdks-legacy-dil) 部分。

## 旧版DIL {#legacy-dil}

如果您没有使用 [!DNL Adobe Experience Platform Identity Service] 但你真的应该。 但是，我们明白迁移到新代码需要仔细思考和测试。 在这些情况下，请检查 `DIL.create` 函数，以确保正确设置此设置，如以下代码示例中所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

有关更多信息，请参阅旧版 [!UICONTROL DIL] 部分 [声明的ID变量](../declared-ids.md#declared-id-variables).

### 配置SDK {#configure-sdks-legacy-dil}

检查 [!DNL SDK] 通过 [!UICONTROL declared IDs] 从 [!DNL Android] 和 [!DNL iOS] 移动设备。 的变量名称 [!DNL Android] 和 [!DNL iOS] 代码库是相同的：

* `dpid`:跨设备数据源ID。
* `dpuuid`:的 [!UICONTROL declared ID] （即用户ID）。

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>语法：</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid， String dpuuid); </pre> </p> <p> <b>示例:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
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

另请参阅 [适用于Android的Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) 和 [适用于iOS的Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [创建数据源](../manage-datasources.md#create-data-source)

