---
title: 将要进行Audience Manager的数据收集库从AppMeasurementJavaScript库更新为Web SDK JavaScript库。
description: 了解将数据收集库从AppMeasurementJavaScript库更新到Web SDK JavaScript库以进行Audience Manager的步骤。
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# 将您的用于Audience Manager的数据收集库从AppMeasurementJavaScript库更新为Web SDK JavaScript库

## 目标受众 {#intended-audience}

本页面向使用AppMeasurement将Web收集数据引入Audience Manager的Audience Manager客户。 对于使用[Audience Manager标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview)的客户，请阅读有关如何将Audience Manager[的数据收集库从Audience Manager标记扩展更新为Web SDK标记扩展](dil-extension-to-web-sdk.md)的指南。

## 此实施路径的优缺点

使用此迁移方法既有优点，也有缺点。 仔细权衡每个选项，以确定哪种方法最适合您的组织。

| 优势 | 缺点 |
| --- | --- |
| <ul><li>**使用您现有的实施**：虽然此方法需要一些实施更改，但它不需要从头开始的全新实施。 您可以使用现有的数据层和代码，只需对实施逻辑进行最低限度的更改即可。</li><li>**不需要架构**：对于迁移到Web SDK的这一阶段，您不需要XDM架构。 相反，您可以填充`data`对象，这会将数据直接发送到Audience Manager。 迁移到Web SDK完成后，您可以为组织创建架构，并使用数据流映射填充适用的XDM字段。 如果在迁移过程的此阶段需要架构，则贵组织将被强制使用Audience Manager的XDM架构。 使用此架构会使贵组织将来更难以使用自己的架构。</li></ul> | <ul><li>**实施技术债务**：由于此方法使用现有实施的修改形式，因此将来需要跟踪实施逻辑和执行更改会更加困难。</li><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Real-Time CDP时，您必须将数据发送到Adobe Experience Platform中的数据集。 此操作要求`data`对象中的每个字段都必须是数据流映射工具中的条目，以便将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li></ul> |

Adobe建议在以下情况下遵循此实施路径：

* 您已有使用Adobe AnalyticsAppMeasurementJavaScript库的实施。 如果您的实现使用Audience Manager标记扩展，请改为遵循[从Audience Manager标记扩展迁移到Web SDK标记扩展](dil-extension-to-web-sdk.md)。
* 您打算在将来使用Real-Time CDP，但不希望从头开始使用Web SDK实施来替换Audience Manager实施。 在Web SDK上从头开始替代实施需要做出最大努力，但同时需要提供最可行的长期实施架构。 如果您的组织愿意进行干净的Web SDK实施，请参阅[Web SDK文档](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)以了解更多详细信息。

## 迁移到Web SDK所需的步骤

以下步骤包含要努力实现的具体目标。 单击每个步骤以了解完成该操作的详细说明。

+++**1. 创建和配置数据流**

在Adobe Experience Platform数据收集中创建数据流。 当您将数据发送到此数据流时，它会将数据转发到Audience Manager。 将来，同一数据流会将数据转发到Real-Time CDP。

1. 导航到[experience.adobe.com](https://experience.adobe.com)并使用您的凭据登录。
1. 使用右上角的主页或产品选择器导航到&#x200B;**[!UICONTROL Data Collection]**。
1. 在左侧导航中，选择&#x200B;**[!UICONTROL Datastreams]**。
1. 选择&#x200B;**[!UICONTROL New Datastream]**。
1. 输入所需的名称，然后选择&#x200B;**[!UICONTROL Save]**。
1. 创建数据流后，选择&#x200B;**[!UICONTROL Add Service]**。
1. 在服务下拉菜单中，选择&#x200B;**[!UICONTROL Audience Manager]**。

   ![添加Audience Manager服务](assets/add-service.png) {style="border:1px solid lightslategray"}

您的数据流现在已准备好接收数据并将数据传递给Audience Manager。 请记下数据流ID，因为在代码中配置Web SDK时需要此ID。

+++

+++**2. 安装Web SDK JavaScript库**

有关详细信息和要使用的代码块，请参阅[使用JavaScript库安装Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library)。 引用`alloy.js`的最新版本，以便使用其方法调用。

+++

+++**3. 配置Web SDK**

使用Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview)命令将您的实施设置为指向在步骤1中创建的数据流。 必须在每个页面上设置`configure`命令，以便您可以将其与库安装代码一起包含。

在Web SDK `configure`命令中使用[`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid)和[`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid)属性：

* 将`edgeConfigId`设置为从上一步检索到的数据流ID。
* 将`orgId`设置为您组织的IMS组织ID。

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

您可以选择在[`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview)命令中设置其他属性，具体取决于贵组织的实施要求。

+++

+++**4. 更新代码逻辑以使用JSON有效负载**

更改您的Audience Manager实现，使其不依赖于`AppMeasurement.js`或`s`对象。 相反，应将变量设置为格式正确的JavaScript对象，该对象在发送到Adobe时会被转换为JSON对象。 在网站上设置[数据层](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer)在设置值时非常有用，因为您可以继续引用这些相同的值。

若要将数据发送到Audience Manager，Web SDK有效负载必须将`data.__adobe.audiencemanager`与此对象中设置的所有Analytics变量一起使用。 此对象中的变量与其对应的AppMeasurement变量具有相同的名称和格式。 例如，如果设置`products`变量，请勿像使用XDM时那样将其拆分为单独的对象。 相反，如果设置`s.products`变量，请完全将其作为字符串包含：

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

最终，此有效负载包含所有所需的值，并且实施中对`s`对象的所有引用都将被删除。 您可以使用JavaScript提供的任何资源来设置此有效负载对象，包括点表示法来设置各个值。

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. 更新方法调用以使用Web SDK**

更新调用[`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method)和[`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method)的所有实例，将它们替换为[`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview)命令。 需要考虑三种情况：

* **页面查看跟踪**：将页面查看跟踪调用替换为Web SDK `sendEvent`命令：

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **自动链接跟踪**：默认情况下启用[`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled)配置属性。 它会自动设置正确的链接跟踪变量，以将数据发送到Audience Manager。 如果要禁用自动链接跟踪，请在[`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview)命令中将此属性设置为`false`。

* **手动链接跟踪**： Web SDK在pageview调用与非页面视图调用之间没有单独的命令。 在有效负荷对象中提供该区别。

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. 验证和发布更改**

删除对AppMeasurement和`s`对象的所有引用后，将更改发布到开发环境以验证新实施是否有效。 在验证所有组件均可正确工作后，您可以将更新发布到生产环境。

如果迁移正确，则您的网站上不再需要`AppMeasurement.js`，并且可以删除对此脚本的所有引用。

+++

此时，您的Audience Manager实施已完全迁移到Web SDK，并准备好将来迁移到Real-Time CDP。
