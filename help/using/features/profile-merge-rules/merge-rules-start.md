---
description: 要创建配置文件合并规则，请查看并完成本节中介绍的每个步骤中的步骤。
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: 开始使用配置文件合并规则
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1263'
ht-degree: 1%

---

# 开始使用配置文件合并规则 {#getting-started-with-profile-merge-rules}

要创建[!UICONTROL Profile Merge Rules]，请查看并完成本节中介绍的每个过程中的步骤。

<!-- merge-rules-start.xml -->

## 创建跨设备数据Source {#create-data-source}

要创建跨设备数据源，请转到&#x200B;**[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;并完成此处描述的每个部分的步骤。 创建或编辑跨设备数据源需要管理员权限。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>有关这些不同控件的说明，请参阅[数据Source设置和菜单选项](../datasources-list-and-settings.md#settings-menu-options)。

## 数据Source详细信息 {#details}

要完成[!UICONTROL Data Source Details]部分，请执行以下操作：

1. 命名数据源。
2. *（可选）*&#x200B;描述数据源。 简洁的描述可帮助您定义数据源的角色或用途。
3. 提供集成代码。 集成代码是您自己的此数据源唯一ID。
4. 在&#x200B;**[!UICONTROL ID Type]**&#x200B;列表中，选择&#x200B;**[!UICONTROL Cross Device]**。
5. 在&#x200B;**[!UICONTROL ID Definition]**&#x200B;列表中，选择用于定义数据源类型的选项。 选项包括：
   * **[!UICONTROL Person]**：定义单个人员的ID。 此ID可以映射到多个[!DNL Audience Manager] ID。
   * **[!UICONTROL Household]**：定义一组人员的ID。 此ID可以映射到多个[!DNL Audience Manager] ID。

## 数据导出控制 {#export-controls}

[数据导出控件](../data-export-controls.md)是可选的分类规则，您可以将其应用于数据源和目标。 当操作违反数据隐私或使用协议时，它们会阻止您向目标发送数据。 如果您不使用[!UICONTROL Data Export Controls]，请跳过此部分。

## 数据Source设置 {#settings}

[!UICONTROL Data Source Settings]部分提供了多个选项，但这2个选项对于创建跨设备数据源很重要：

* **[!UICONTROL Use as Authenticated Profile]**：默认选中，此设置允许您使用自己的经过身份验证的数据生成[!UICONTROL Profile Merge Rule]。

* **[!UICONTROL Use as a Device Graph]**：此控件仅适用于列为数据提供程序的帐户。 选中此复选框会将您的数据源创建为设备图，并允许您与其他[!DNL Audience Manager]客户共享。 与您的[!DNL Audience Manager]顾问合作，将其设置为数据提供程序，并指定应将此[!UICONTROL Data Source]共享给哪些客户。 您的顾问将通过内部配置过程配置您的帐户和设备图共享。

* **[!UICONTROL Data retention for inactive Customer IDs]**：此控件允许您为非活动客户ID设置数据保留期限。 这会决定Audience Manager将客户ID在Audience Manager平台上最后一次看到后，保留在我们的数据库中的时间。 默认值为24个月（720天）。 您可以设置的最小值为1个月，最大值为5年。 请注意，我们将所有月份都计为30天。 Audience Manager会根据您为非活动客户ID设置的数据保留时间，运行每周删除一次非活动客户ID的流程。

与这些设置关联的文本字段允许您使用在[配置文件合并规则选项](merge-rule-definitions.md)中显示的别名重命名[!UICONTROL Data Source]。 例如，如果您向&#x200B;**[!UICONTROL Use as Authenticated Profile]**&#x200B;添加别名，则该名称会显示在[!UICONTROL Authenticated Profile Options]列表中。 如果您向&#x200B;**[!UICONTROL Use as a Device Graph]**&#x200B;添加别名，则该名称会显示在[!UICONTROL Device Options]列表中。

## 创建配置文件合并规则 {#create-profile-merge-rule}

要创建[!UICONTROL Profile Merge Rule]，请转到&#x200B;**[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]**&#x200B;并完成此处描述的每个部分的步骤。

设置跨设备数据源后，您最多可以创建3个合并规则。 如果您注册[基于人员的目标](../destinations/people-based-destinations-overview.md)，则可以访问第4个配置文件合并规则([!UICONTROL All Cross-Device Profiles])。

创建、编辑或删除规则需要管理员权限。 所有用户都可以查看和使用现有[!UICONTROL Profile Merge Rules]。

<!-- create-profile-merge-rule.xml -->

**先决条件：**&#x200B;需要跨设备数据源才能生成[!UICONTROL Profile Merge Rule]。 请参阅[创建数据Source](../manage-datasources.md#create-data-source)。

>[!TIP]
>
>有关这些不同控件的说明，请参阅[定义的配置文件合并规则选项](merge-rule-definitions.md)。

## 基本信息 {#basic-info}

要完成[!UICONTROL Basic Information]部分，请执行以下操作：

1. 为[!UICONTROL Profile Merge Rule]命名。
2. *（可选）*&#x200B;描述[!UICONTROL Profile Merge Rule]。 简洁的描述可帮助您定义规则的角色或用途。
3. *（可选）*&#x200B;如果要使其成为默认[!UICONTROL Profile Merge Rule]，请选择&#x200B;**[!UICONTROL Set as default]**。 新区段会自动与默认规则关联。

## 数据导出控制 {#data-export-controls}

[数据导出控件](../data-export-controls.md)是可选的分类规则，可应用于[!UICONTROL Profile Merge Rule]。 当操作违反数据隐私或使用协议时，它们会阻止您向目标发送数据。 如果您不使用[!UICONTROL Data Export Controls]，请跳过此部分。

## 配置文件合并规则设置 {#profile-merge-rule-setup}

要完成[!UICONTROL Proflie Merge Rule Setup]部分，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL Authenticated Option]**。 选项包括：
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. 选择&#x200B;**[!UICONTROL Authenticated Profile Option]**（最多3个，最多）。 这些是您之前创建的[跨设备数据源](merge-rules-start.md)。
3. 选择&#x200B;**[!UICONTROL Device Option]**。 选项包括：
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. 单击 **[!UICONTROL Save]**。

### 有关使用跨设备ID作为用户ID密钥的Adobe Campaign目标的注意事项 {#considerations}

2019年末，我们发布了一系列配置文件合并规则增强功能，以提高使用跨设备ID生成的批处理文件的准确性。 从2020年3月16日星期一开始，您的Audience Manager实例将严格遵循这些增强功能。 因此，使用跨设备ID映射到目标的区段将停止在某些配置文件合并规则配置中生成导出。

要确保使用跨设备ID(如Adobe Campaign)的Audience Manager实例和目标之间正确集成，请确保您满足以下要求：

1. 查看映射到您的Adobe Campaign Declared ID目标的区段所使用的配置文件合并规则。 配置文件合并规则必须使用[!UICONTROL Last Authenticated Profile]选项，以便所有经过身份验证的配置文件都可以包含在导出中。 如果您的配置文件合并规则使用其他选项，请将其切换到[!UICONTROL Last Authenticated Profile]。
2. 在配置文件合并规则设置中选择Adobe Campaign Declared ID数据源。

>[!NOTE]
>
> 如果您已达到[!UICONTROL Profile Merge Rules]的最大数量，并根据上述说明在配置过程中需要帮助，请联系客户关怀团队。

## 配置合并规则代码 {#configure-merge-rule-code}

按照这些说明设置[!UICONTROL Adobe Experience Platform Identity Service]、[!UICONTROL DIL]和移动设备[!DNL SDK]代码以使用合并规则。

<!-- merge-rules-configure-code.xml -->

### 先决条件

在完成这些步骤之前，您必须设置[跨设备数据源](#create-data-source)和[配置文件合并规则](#create-profile-merge-rule) **。

## 对于Adobe Experience Platform Identity服务客户 {#id-service-customers}

在使用[!UICONTROL Profile Merge Rules]时，建议使用[!UICONTROL Adobe Experience Platform Identity Service]和最新版本的[DIL](../../dil/dil-overview.md)。 但是，您不必使用[!UICONTROL Adobe Experience Platform Identity Service]即可使用此功能。 如果您只使用[!UICONTROL DIL]，请参阅下面的[旧版DIL部分](#legacy-dil)。

### 配置Set Customer ID函数

使用[!UICONTROL Adobe Experience Platform Identity Service]时，`setCustomerIDs`函数将声明的ID传递给[!DNL Audience Manager]。 要使用配置文件合并规则，必须修改`setCustomerIDs`以使用在创建跨设备数据源时指定的集成代码。 例如，假设您已使用集成代码`my_datasource_ic`创建跨设备数据源。 要传入声明的ID，您需要将集成代码添加到访客ID函数中，如下面的修改后代码示例所示。

#### 常规代码示例

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### 修改后的代码示例

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

有关详细信息，请参阅[创建跨设备数据Source](#create-data-source)和[客户ID和身份验证状态](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)。

### 配置`DIL.create`函数

最新版本的[!UICONTROL DIL]现在自动从`DIL.create`中的`visitorService`函数提取[!UICONTROL declared ID]（请参阅[声明的ID变量](../declared-ids.md#declared-id-variables)）。 检查您的`DIL.create`函数，确保正确设置此函数，如下面的代码示例所示。

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

在命名空间键值对中，`*`MCORG`*`变量是您的[!DNL Experience Cloud]组织ID。 如果您没有此ID，则可以在[!DNL Experience Cloud]仪表板的[!UICONTROL Administration]部分中找到它。 您需要管理员权限才能查看此仪表板。 请参阅[管理：核心服务](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)。

### 配置SDK

请参阅下面的[配置SDK](#configure-sdks-legacy-dil)部分。

## 旧版DIL {#legacy-dil}

如果您尚未使用[!DNL Adobe Experience Platform Identity Service]，则确实应该使用。 但是，我们理解，迁移到新代码需要仔细的思考和测试。 在这些情况下，请检查您的`DIL.create`函数，以确保正确设置了它，如下面的代码示例所示。

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

有关详细信息，请参阅[声明的ID变量](../declared-ids.md#declared-id-variables)中的旧版[!UICONTROL DIL]部分。

### 配置SDK {#configure-sdks-legacy-dil}

检查您的[!DNL SDK]代码中允许您从[!DNL Android]和[!DNL iOS]移动设备传递[!UICONTROL declared IDs]的方法。 [!DNL Android]和[!DNL iOS]代码库的变量名称相同：

* `dpid`：跨设备数据源标识。
* `dpuuid`： [!UICONTROL declared ID]（即用户ID）。

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>语法：</b> </p> <p> <pre> 公共静态void setDpidAndDpuuid(String dpid， String dpuuid)； </pre> </p> <p> <b>示例：</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid"，"myDpuuid")； </pre> </p> </td> 
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

另请参阅[Android的Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html)和[iOS的Audience Manager方法](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html)。

>[!MORELIKETHIS]
>
>* [创建数据源](../manage-datasources.md#create-data-source)
