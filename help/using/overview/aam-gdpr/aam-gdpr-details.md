---
description: 本文档涵盖Audience Manager的一般数据保护规定(GDPR)的相关技术，并向您展示如何向Audience Manager提交GDPR请求。
seo-description: 本文档涵盖Audience Manager的一般数据保护规定(GDPR)的相关技术，并向您展示如何向Audience Manager提交GDPR请求。
seo-title: Audience Manager 中的 GDPR
solution: Audience Manager
title: Audience Manager 中的 GDPR
uuid: ed23a478-32be-460d-bb03-a735317 f7 c0 f
translation-type: tm+mt
source-git-commit: b791e22e9c8c848a8fc14c6d6494f77c9e7335dc

---


# Audience Manager 中的 GDPR{#gdpr-in-audience-manager}

本文档涵盖Audience Manager的一般数据保护规定(GDPR)的相关技术，并向您展示如何向Audience Manager提交GDPR请求。

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

在阅读Audience Manager特定信息之前，我们建议您浏览Experience Cloud的欧洲一般数据保护规定(GDPR)材料，如下链接：

* [GDPR与您的业务](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [GDPR白皮书](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [GDPR 术语](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

以下部分介绍了GDPR对Audience Manager的意义，以及如何向Audience Manager提交GDPR请求。

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). 如果您有疑问，请联系客户关怀部门，网址为gdprsupport@adobe.com。

## 访问数据 {#access-data}

我们理解您承诺在收到的30天内尊重GDPR客户请求。因此，我们尽量尽快处理您的数据访问请求。

**请求**

You can log data access requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `access` action). 无论哪种情况，您都必须将JSON与提交数据访问请求的Audience Manager标识符上传。See what a well-formed JSON looks like in the **[Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/access_request.json)**.

**响应**

对访问数据请求的答复包含特征和区段总数、特征类型、特征和区段描述以及各自的数据源名称。访问响应还将包括由数据管理者访问的第二方数据和第三方数据，以及第一方数据。When [!UICONTROL declared IDs] such as cross device CRM IDs or customer cookie IDs are sent in GDPR requests, Audience Manager will include the Access response from all the linked devices (up to 100 devices per declared ID).

**响应状态**

如果响应中存在Audience Manager中的任何错误，则会作为响应出现在响应中的错误代码。We have a [list of error codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), where you can find more information about the returned errors.

**示例响应**

示例访问响应的外观可能如下所示。在此示例中，数据主体的ID为cookie ID。他们符合几个特征，属于几个细分。cookie ID链接到移动ID。该示例还包含他们使用的电话的元数据。

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

下表包含数据访问响应中所有返回字段的描述(按它们显示的顺序)。

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
   <td colname="col2"> <p>随后的数据的用户ID。这是您在GDPR数据访问请求中提供的id或链接到其中某个已声明ID的ID。<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager标识符</a> 部分介绍了ID类型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>也称为数据源。See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>命名空间/数据源 ID。See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 集成代码 </code> </p> </td> 
   <td colname="col2"> <p>集成代码是数据源的友好名称，可帮助您比使用数据源ID更轻松地跟踪数据源。 </p> </td> 
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
   <td colname="col2"> <p>您请求访问 GDPR 数据的 ID 类型。Accepted types are listed in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 警告</code> </p> </td> 
   <td colname="col2"> <p>警告返回与数据访问请求相关的更多信息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> title </code> </p> </td> 
   <td colname="col2"> <p>有关警告的简要信息。 </p> <p>您可能收到的两个警告是： </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">设备数据 </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">不完整请求 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>接收到的警告的更详细描述： </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">设备数据-包含此设备所有用户的数据 </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">不完整请求- Audience Manager数据检索未完成。可能缺少一些信息。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>与此用户ID关联的特征和区段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>与用户ID关联的特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>特征的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>特征类型。可能的值包括： </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>适用于您自己特征的第一方</i> 。 </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>属于您的合作伙伴的特征的第二方</i> 。Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>第三方</i> 通过 <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace获取从数据合作伙伴获得的特征</a>。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>帮助描述特征的目的或功能。这是可选字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据导出控件</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this trait's data source. </p> </td> 
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
   <td colname="col1"> <p> <code> 上次实现</code> </p> </td> 
   <td colname="col2"> <p>数据主体上次符合此特征的确切时间。日期格式为YYYY-MM-DD。 </p> </td> 
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
   <td colname="col2"> <p>帮助描述此区段的几个词语。这是可选字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 数据导出控件</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this segment's data source. </p> </td> 
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
   <td colname="col1"> <p> <code> 上次实现</code> </p> </td> 
   <td colname="col2"> <p>数据主体上次符合此区段资格的确切时间。日期格式为YYYY-MM-DD。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> active活动</code> </p> </td> 
   <td colname="col2"> <p>指示数据主体当前是否符合此区段资格。Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 链接 </code> </p> </td> 
   <td colname="col2"> <p>此ID已链接到的其他ID。信息在以下位置返回： </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">命名空间(数据源) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">集成代码 </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">数据提供程序名称 </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">ID type </li> 
     </ul> </p> <p>此表的第一行将介绍所有这些字段。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 链接数据时间</code> </p> </td> 
   <td colname="col2"> <p>ID同步事件在ID之间建立链接的确切时间。日期格式为YYYY-MM-DD。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 设备元数据 </code> </p> </td> 
   <td colname="col2"> <p>有关设备的信息。此信息包括以下字段。请注意，并非所有设备类型都返回所有字段。 </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>硬件信息 </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>设备制造商 </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>设备的营销名称 </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>设备模型 </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>设备操作系统的名称(操作系统) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>操作系统的版本 </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>设备供应商 </p> </li> 
     </ul> </p> <p> <p>注意：当您提交以下任一内容时，我们只返回设备元数据： 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">移动ID </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager ID </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud ID </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 删除数据 {#delete-data}

我们理解您承诺在收到的30天内尊重GDPR客户请求。因此，我们尽量尽快处理您的数据删除请求。

**请求**

You can log data deletion requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `delete` action). 无论哪种情况，您都必须将JSON与提交数据访问请求的Audience Manager标识符上传。See what a well-formed JSON looks like in the [Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) (specifically, search in page for "POST request format"). Or, you can **[download a sample JSON](assets/delete_request.json)**.

**响应**

为了响应数据删除请求，我们删除与各个Audience Manager标识符相关的特征和区段。此外，数据主体对应的Audience Manager标识符将从Audience Manager中永久选择退出数据收集，并将删除各自的ID映射。如果在GDPR请求中发送了跨设备CRM ID或客户cookie ID等声明的ID，Audience Manager将对所有链接设备执行必要的删除操作(每个声明ID最多可为100台设备)。

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager Identifiers (IDs) {#aam-ids}

向Adobe Audience Manager提交GDPR请求时，您必须包含以下列出的标识符(ID)。You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

### Adobe Audience Manager唯一用户ID

**用户ID**：aam_ uuid

**定义**：Adobe Audience Manager唯一用户ID

**命名空间ID**：0

>[!NOTE]
>
>您还可以使用核心命名空间。请参阅第二个JSON示例。

**JSON**&#x200B;中的示例：

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

**用户ID**：中间版本

**定义**：Adobe Experience Cloud ID，以前称为访客ID或Marketing Cloud ID

**命名空间ID**：个

>[!NOTE]
>
>您还可以使用EID命名空间。请参阅第二个JSON示例。

**JSON**&#x200B;中的示例：

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

**用户ID**：cid

**定义**：客户ID，例如您为匿名站点访问者设置的Cookie或来自脱机系统或哈希用户名的CRM ID

**命名空间ID**：客户特定。请从Audience Manager实例中找到它。

**JSON**&#x200B;中的示例：

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

**用户ID**：d_ cid

**定义**：移动广告ID。
>[!IMPORTANT]
>
> 如果您使用的是Mobile SDK，则还应将Experience Cloud ID(MID)和移动广告ID一起发送，以获得完整的GDPR访问和删除答复。

**命名空间 ID**:

* IDFA：20915
* GUID：20914

**JSON**&#x200B;中的示例：

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

### 集成代码

**用户ID**：d_ cid_ ic

**定义**：数据源的集成代码。它可以代替API请求中的数据源ID/命名空间ID来使用Adobe Experience Cloud隐私核心服务。

**命名空间ID**：不适用

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
