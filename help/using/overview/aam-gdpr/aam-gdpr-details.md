---
description: 本文档涵盖与Audience manager的一般数据保护规定(GDPR)相关的技术细节，并向您展示如何向Audience manager提交GDPR请求。
seo-description: 本文档涵盖与Audience manager的一般数据保护规定(GDPR)相关的技术细节，并向您展示如何向Audience manager提交GDPR请求。
seo-title: Audience Manager 中的 GDPR
solution: Audience Manager
keywords: GDPR UI, GDPR API
title: Audience Manager 中的 GDPR
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 5661bcef9816b6646ee63ebc6c19b730c1ccadc9

---


# Audience Manager 中的 GDPR{#gdpr-in-audience-manager}

This document covers the technicalities related to the General Data Protection Regulation (GDPR) for Audience Manager and shows you how to submit GDPR requests to Audience Manager.

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

Before reading the Audience Manager specifics, we advise you go through the Experience Cloud material for the European General Data Protection Regulation (GDPR), linked below:

* [GDPR与您的业务](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [GDPR Whitepaper](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [GDPR 术语](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

以下各节将说明GDPR对Audience manager的意义，以及您如何向Audience manager提交GDPR请求。

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the Privacy Service UI (UI link here and documentation here) or by calling the Privacy Service API (documentation here and API reference here). ****[](https://gdprui.cloud.adobe.io/)[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)****[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). If you have questions, please reach out to Customer Care at gdprsupport@adobe.com.

## 访问数据 {#access-data}

我们理解您承诺在接收后30天内履行您的GDPR客户请求。 因此，我们会尽快处理您的数据访问请求。

**请求**

您可以通过 **Service SERVICE** ([LINK and](https://gdprui.cloud.adobe.io/) here [)或通过调用](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)****[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)Privacy Service API(Here Privacy Service API)（此处为隐私服务文档）和在此引用隐私API（此处为引用API）来记录数据访问请求。 无论哪种情况，您都必须上传包含Audience Manager标识符的JSON，您为其提交数据访问请求。 要查看格式良好的JSON的外观，您可以下 **[载示例JSON](assets/access_request.json)**。

**响应**

对访问数据请求的响应包含特征和区段总数、特征类型、特征和区段的描述以及相应的数据源名称的摘要。 访问响应还将包括可由数据控制器访问的第二方和第三方数据以及第一方数据。 当在 [!UICONTROL declared IDs] GDPR请求中发送跨设备CRM ID或客户Cookie ID时，Audience manager将包括来自所有链接设备的访问响应（每个声明的ID最多100台设备）。

**响应状态**

如果响应中有来自Audience manager的任何错误，则这些错误会作为错误代码在响应中显示。 We have a list of error codes, where you can find more information about the returned errors.[](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

**示例响应**

示例访问响应可能与下面的响应类似。 在本例中，数据主体的ID是cookie ID。 它们符合几个特征，属于几个细分。 cookie ID链接到移动ID。 该示例还包含他们使用的电话的元数据。

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

下表按数据访问响应中返回的所有字段的显示顺序，包含这些字段的说明。

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>字段 </p> </th> 
   <th colname="col2" class="entry"> <p>描述 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>随后的数据的用户ID。 这是您在GDPR数据访问请求中提供的ID，或者链接到您提供的声明ID之一的ID。 Audience Manager标识符部分介绍了ID <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> 类型</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>也称为数据源。请参阅Audience <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Manager标识符部分</a> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>命名空间/数据源 ID。请参 <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> 阅Audience Manager标识符(ID)</a> ，了解所有已接受的值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 集成代码 </code> </p> </td> 
   <td colname="col2"> <p>集成代码是数据源的易记名称，与使用数据源ID相比，它可以帮助您更轻松地跟踪数据源。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据提供程序名称 </code> </p> </td> 
   <td colname="col2"> <p>数据源所有者的名称。 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">对于第一方数据，这是客户自己的公司名称。 </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">对于第二方数据，这是合作伙伴公司的名称。 </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">对于第三方数据，这是数据合作伙伴的名称。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>您请求访问 GDPR 数据的 ID 类型。Accepted types are listed in the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 警告</code> </p> </td> 
   <td colname="col2"> <p>Warnings return further information related to the data access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>Brief information about the warning. </p> <p>The two warnings you may receive are: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Device Data </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Incomplete request </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>A more detailed description of the warning you received: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">设备数据——包含来自此设备所有用户的数据 </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">请求不完整——未完成Audience manager数据的检索。 某些信息可能缺失。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据 </code> </p> </td> 
   <td colname="col2"> <p>The traits and segments associated with this user ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>与用户ID关联的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>The name of the trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>The trait type. 可能的值包括： </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>First party for your own traits.</i> </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Second party for traits that belong to your partners. </i>Read our  Second Party Data article for more information.<a href="../../overview/data-types-collected.md#second-party-data"></a> </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>第三方</i> ，用于通过Audience Marketplace从数据合作伙伴获取 <a href="../../features/audience-marketplace/audience-marketplace.md"> 的特征</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>用几个词来描述特质的目的或功能。 This is an optional field. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据导出控件</code> </p> </td> 
   <td colname="col2"> <p>应用 <a href="../../features/data-export-controls.md"> 于此特征的数据源</a> ，数据导出控件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据提供程序名称</code> </p> </td> 
   <td colname="col2"> <p>此特征所属的数据源所有者的名称。 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">对于第一方数据，这是客户自己的公司名称。 </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">对于第二方数据，这是合作伙伴公司的名称。 </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">对于第三方数据，这是数据合作伙伴的名称。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 最后实现</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this trait. 日期格式为YYYY-MM-DD。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 区段 </code> </p> </td> 
   <td colname="col2"> <p>此用户所属的区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>区段的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>用几个词帮助描述此部分。 这是一个可选字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据导出控件</code> </p> </td> 
   <td colname="col2"> <p>应用 <a href="../../features/data-export-controls.md"> 于此段数据源</a> 的数据导出控件。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据提供程序名称</code> </p> </td> 
   <td colname="col2"> <p>此区段所属的数据源所有者的名称。 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">对于第一方数据，这是客户自己的公司名称。 </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">对于第二方数据，这是合作伙伴公司的名称。 </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">对于第三方数据，这是数据合作伙伴的名称。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 最后实现</code> </p> </td> 
   <td colname="col2"> <p>数据主体上次限定此区段的准确时间。 日期格式为YYYY-MM-DD。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active</code> </p> </td> 
   <td colname="col2"> <p>指示数据主体当前是否符合此区段的条件。 Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 链接 </code> </p> </td> 
   <td colname="col2"> <p>此ID已链接到的其他ID。 信息返回于： </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace（数据源） </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">集成代码 </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">数据提供程序名称 </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>此表的前几行中介绍了所有这些字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>The exact time that an ID sync event made the link between IDs. The date format is YYYY-MM-DD. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> device metadata </code> </p> </td> 
   <td colname="col2"> <p>有关设备的信息。 此信息包括以下字段。 Note that not all fields are returned for all device types. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Hardware information </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>设备制造商 </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>设备的营销名称 </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>The device model </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>The name of the device's Operating System (OS) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>The version of the OS </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>设备供应商 </p> </li> 
     </ul> </p> <p> <p>注意： We only return device metadata when you submit either one of: 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">移动ID </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager ID </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 删除数据 {#delete-data}

我们理解您承诺在接收后30天内履行您的GDPR客户请求。 因此，我们会尽快处理您的数据删除请求。

**请求**

您可以通过 **Service SERVICE** ([LINK and](https://gdprui.cloud.adobe.io/) here [)或通过调用Privacy Service API(Here Innext Service Api)（隐私服务API）(此处为](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)****[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)Privacy Service Api，此处为删除和在此引用API)来记录数据请求。 无论哪种情况，您都必须上传包含Audience Manager标识符的JSON，您为其提交数据访问请求。 要查看格式良好的JSON的外观，您可以下 **[载示例JSON](assets/delete_request.json)**。

**响应**

为响应数据删除请求，我们会删除与相应Audience manager标识符关联的特征和区段。 此外，Audience manager将永久选择不再收集更多数据，并删除相应的Id映射。 When declared IDs such as cross device CRM Ids or customer cookie ids are sent in GDPR requests, Audience Manager will perform the necessary Delete actions on all the linked devices (up to 100 devices per declared ID).

## 退出请求 {#opt-out-request}

有关退出请求，请参阅我们关于退出管 [理的文档](../../overview/data-security-and-privacy/opt-out-management.md)。

## Audience manager标识符(ID) {#aam-ids}

在向Adobe Audience manager提交GDPR请求时，您必须包括以下列出的一个标识符(ID)。 您可以在我们的Audience Manager ID索引中找到有关ID [格式的更多信息](../../reference/ids-in-aam.md)。

### Adobe Audience Manager唯一用户ID

**用户ID**:aam_uuid

**定义**:Adobe Audience Manager唯一用户ID

**命名空间ID**:0

>[!NOTE]
>
>您还可以使用CORE命名空间。 请参阅第二个JSON示例。

**JSON中的示例**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**用户ID**:mid

**定义**:Adobe Experience Cloud ID，以前称为访客ID或Marketing Cloud ID

**Namespace ID**: 4

>[!NOTE]
>
>您还可以使用ECID命名空间。 请参阅第二个JSON示例。

**Example in JSON:**

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**User ID: cid**

**Definition: Customer ID, such as a cookie you set for anonymous site visitors or a CRM ID from an offline system or a hashed username**

**Namespace ID: Customer-specific.** Please find it from your Audience Manager instance.

**Example in JSON:**

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### 移动广告ID

**用户ID**:d_cid

**定义**:移动广告ID。
>[!IMPORTANT]
>
> 如果您使用的是Mobile SDK，则还应发送Experience Cloud ID(MID)和移动广告ID，以获得完整的GDPR访问和删除响应。

**命名空间 ID**:

* IDFA: 20915
* GAID:二〇九一四年

**JSON中的示例**:

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### Integration code

**User ID: d_cid_ic**

**定义**:数据源的集成代码。 在向Adobe Experience Cloud隐私核心服务发出的API请求中，可以使用它代替数据源ID /命名空间ID。

**命名空间ID**:不适用

JSON中的示例：

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
