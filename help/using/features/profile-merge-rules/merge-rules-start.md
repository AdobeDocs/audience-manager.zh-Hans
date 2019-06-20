---
description: 要创建配置文件合并规则，请查看并完成本节所述的各个步骤中的步骤。
seo-description: 要创建配置文件合并规则，请查看并完成本节所述的各个步骤中的步骤。
seo-title: 个人资料合并规则入门
solution: Audience Manager
title: 个人资料合并规则入门
uuid: 7d32c60f-467c-42dd-afa9-437fd7 c473 c5
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Getting Started with Profile Merge Rules {#getting-started-with-profile-merge-rules}

To create [!UICONTROL Profile Merge Rules], review and complete the steps in each of the procedures described in this section.

<!-- merge-rules-start.xml -->

## Create a Cross-Device Data Source {#create-data-source}

To create a cross-device data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. 需要管理员权限才能创建或编辑跨设备数据源。

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. 命名数据源。
1. *(可选)* 描述数据源。简明的描述可帮助您定义数据源的角色或目的。
1. 提供集成代码。集成代码是此数据源的唯一ID。
1. In the **[!UICONTROL ID Type]** list, select **[!UICONTROL Cross Device]**.
1. In the **[!UICONTROL ID Definition]** list, select an option that defines the data source type. 选项包括：
   * **[!UICONTROL Person]**：定义单个人的ID。This ID can be mapped to multiple [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**：定义一组人员的ID。This ID can be mapped to multiple [!DNL Audience Manager] IDs.

## 数据导出控制 {#export-controls}

[数据导出控件](../../features/data-export-controls.md) 是可选的分类规则，您可以应用于数据源和目标。当该操作违反了数据隐私或使用协议时，它们会阻止您向目标发送数据。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

[!UICONTROL Data Source Settings] 部分提供多个选项，但这对于创建跨设备数据源很重要：

* **[!UICONTROL Use as Authenticated Profile]**：默认情况下，此设置允许您 [!UICONTROL Profile Merge Rule] 使用自己的已验证数据构建一个。

* **[!UICONTROL Use as a Device Graph]**：此控制仅适用于作为数据提供程序列出的帐户。Selecting this check box creates your data source as a device graph and lets you share it with other [!DNL Audience Manager] customers. Work with your [!DNL Audience Manager] consultant to get set up as a data provider and to specify which customers this [!UICONTROL Data Source] should be shared with. 您的顾问将通过内部供应流程设置您的帐户和设备图表共享。

* **[!UICONTROL Data retention for inactive Customer IDs]**：此控制允许您设置非活动客户ID的数据保留期限。这决定Audience Manager在Audience Manager平台上最后一次看到时，在我们的数据库中保留客户ID的时间。默认值为24个月(720天)。您可以设置的最小值为个月，最大值为年。请注意，我们将所有月份计为30天。Audience Manager会根据您为非活动客户ID设置的数据保留，每周删除一次不活动的客户ID。

The text fields associated with these settings let you rename the [!UICONTROL Data Source] with an alias that appears in the [Profile Merge Rule options](../../features/profile-merge-rules/merge-rule-definitions.md). For example, if you add an alias to **[!UICONTROL Use as Authenticated Profile]**, that name appears in the [!UICONTROL Authenticated Profile Options] list. If you add an alias to **[!UICONTROL Use as a Device Graph]**, that name appears in the [!UICONTROL Device Options] list.

>[!MORE_ LIKE_ This]
>
>* [创建数据源](../../features/manage-datasources.md#create-data-source)


## Create a Profile Merge Rule {#create-profile-merge-rule}

To create a [!UICONTROL Profile Merge Rule], go to **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** and complete the steps for each section described here. 设置跨设备数据源后，您可以创建最多个合并规则。需要管理员权限才能创建、编辑或删除规则。All users can view and use existing [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**先决条件：** 构建一 [!UICONTROL Profile Merge Rule]个跨设备数据源是必需的。See [Create a Data Source](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md) for descriptions of these different controls.

## 基本信息 {#basic-info}

To complete the [!UICONTROL Basic Information] section:

1. Name the [!UICONTROL Profile Merge Rule].
2. *(可选)* 描述。[!UICONTROL Profile Merge Rule]简洁的描述可帮助您定义规则的角色或目的。
3. *(可选)* 选择 **[!UICONTROL Set as default]** 是否要将此默认值设为默认 [!UICONTROL Profile Merge Rule]值。新区段会自动与默认规则关联。

## 数据导出控制 {#data-export-controls}

[数据导出控制](../../features/data-export-controls.md) 是可选的分类规则 [!UICONTROL Profile Merge Rule]，您可以对其应用。当该操作违反了数据隐私或使用协议时，它们会阻止您向目标发送数据。Skip this section if you do not use [!UICONTROL Data Export Controls].

## Profile Merge Rule Setup {#profile-merge-rule-setup}

To complete the [!UICONTROL Proflie Merge Rule Setup] section:

1. Select an **[!UICONTROL Authenticated Option]**. 选项包括：
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Select an **[!UICONTROL Authenticated Profile Option]** (up to 3, maximum). These are the [cross-device data sources](../../features/profile-merge-rules/merge-rules-start.md) you have created previously.
3. 选择 **[!UICONTROL Device Option]**. 选项包括：
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. 单击 **[!UICONTROL Save]**.

## Configure Merge Rule Code {#configure-merge-rule-code}

Follow these instructions to set up the [!UICONTROL Experience Cloud ID Service], [!UICONTROL DIL], and mobile [!DNL SDK] code to work with your merge rules.

<!-- merge-rules-configure-code.xml -->

### 先决条件

You must set up a [cross-device data source](#create-data-source) and [profile merge rules](#create-profile-merge-rule) *before* completing these procedures.

## For Experience Cloud ID Service Customers {#id-service-customers}

[!UICONTROL Experience Cloud ID Service] 使用时建议使用 [DIL的最新](../../dil/dil-overview.md) 版本 [!UICONTROL Profile Merge Rules]。However, you don&#39;t have to use the [!UICONTROL Experience Cloud ID Service] to work with this feature. If you&#39;re just using [!UICONTROL DIL], see the [legacy DIL section](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) below.

### 配置设置客户ID函数

When working with the [!UICONTROL Experience Cloud ID Service], the `setCustomerIDs` function passes declared IDs to [!DNL Audience Manager]. To use a profile merge rule, you must modify `setCustomerIDs` to use the integration code specified when you created a cross-device data source. For example, say you&#39;ve created a cross-device data source with the integration code `my_datasource_ic`. 要传入声明的ID，您需要将集成代码添加到访客ID函数中，如下面修改的代码示例所示。

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

For more information, see [Create a Cross-Device Data Source](#create-data-source) and [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### Configure `DIL.create` function

The latest versions of [!UICONTROL DIL] now automatically pick up the [!UICONTROL declared ID] from the `visitorService` function in `DIL.create` (see [Declared ID Variables](../../features/declared-ids.md#declared-id-variables)). Check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>var VDil= DIL. create({合作伙伴：“合作伙伴名称”、“visi服务”：{namespace：“<i>INSERT-MCORG-ID-HERE</i>”}})；</code>
</pre>

In the namespace key-value pair, the `*`MCORG`*` variable is your [!DNL Experience Cloud] Organization ID. If you don&#39;t have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. 您需要管理员权限才能查看此控制板。See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### 配置SDK

See the [Configure SDKs](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) section below.

## Legacy DIL {#legacy-dil}

[!DNL Experience Cloud ID Service] 如果您还没有使用，您真的应该做到。但我们理解，转向新代码需要仔细思考和测试。In these cases, check your `DIL.create` function to make sure this is set up properly as shown in the code sample below.

<pre class="js"><code>DIL. create({合作伙伴：“合作伙伴姓名”，声明ID：{dpuuid：<i>dpuid</i>，dpid：<i>dpid</i>}})；</code>
</pre>

For more information, see the legacy [!UICONTROL DIL] section in [Declared ID Variables](../../features/declared-ids.md#declared-id-variables).

### Configure SDKs {#configure-sdks-legacy-dil}

Check the methods in your [!DNL SDK] code that let you pass [!UICONTROL declared IDs] from [!DNL Android] and [!DNL iOS] mobile devices. The variable names for the [!DNL Android] and [!DNL iOS] code libraries are the same:

* `dpid`：跨设备数据源ID。
* `dpuuid`：( [!UICONTROL declared ID] 即用户ID)。

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>语法：</b> </p> <p> <pre> public static void setdpIDAndPuUID(String dpd，String dpuid)； </pre> </p> <p> <b>示例：</b> </p> <p> <pre> AudienceManager. setDpIDAndPuUI(“myDPID”、“myDpuuID”)； </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> AudienceSetdID：dpuid </code> </p> <p> <b>语法：</b> </p><p>
    <code class="javascript">+(void) audienceSettID：(nSString*) dpid
dpuid：(nSString*) dpuid； </code>
 </p>
    <p> <b>示例：</b> </p><p>
    <code class="javascript">[AdbMobile AudienceSettID：@“290”dpuid：@“99301393923940”]； </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

See also, [Audience Manager Methods for Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) and [Audience Manager Methods for iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).
