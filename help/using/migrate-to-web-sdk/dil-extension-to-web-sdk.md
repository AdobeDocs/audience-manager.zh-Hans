---
title: 从Audience Manager标记扩展迁移到Web SDK标记扩展
description: 了解将数据收集库从Audience Manager标记扩展更新为Web SDK标记扩展以进行Audience Manager的步骤
source-git-commit: c80f39c4001d2bcfa94012b9f4ffa720806487d4
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---


# 将用于Audience Manager的数据收集库从Audience Manager标记扩展更新为Web SDK标记扩展

## 目标受众

Audience Manager本页面向使用 [Audience Manager标记扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) 将Web收集数据引入Audience Manager。 对于使用AppMeasurementJavaScript库的客户，请阅读有关如何更新用于Audience Manager的数据收集库的指南 [从AppMeasurementJavaScript库到Web SDK JavaScript库](appmeasurement-to-web-sdk.md).

## 此实施路径的优缺点

使用此迁移方法既有优点，也有缺点。 仔细权衡每个选项，以确定哪种方法最适合您的组织。

| 优势 | 缺点 |
| --- | --- |
| <ul><li>**您的网站上无代码更改**：由于您的实施已安装标记，因此可以在标记界面中进行所有迁移更新。</li><li>**使用您现有的实施**：此方法不需要全新实施。 虽然它确实需要新的规则操作，但您可以以最小的更改重复使用现有数据元素和规则条件。</li><li>**不需要架构**：对于迁移到Web SDK的这一阶段，您不需要XDM架构。 相反，您可以填充 `data` 对象，可直接将数据发送到Adobe Audience Manager。 迁移到Web SDK完成后，您可以为组织创建架构，并使用数据流映射填充适用的XDM字段。 如果在迁移过程的此阶段需要架构，则贵组织将被强制使用Adobe Audience Manager XDM架构。 使用此架构会使贵组织将来更难以使用自己的架构。</li></ul> | <ul><li>**执行技术债务**：由于此方法使用现有实施的修改形式，因此可能更难跟踪实施逻辑并在需要时执行更改。 自定义代码可能特别难以调试。</li><li>**需要映射才能将数据发送到Platform**：当您的组织准备好使用Real-Time CDP时，您必须将数据发送到Adobe Experience Platform中的数据集。 该操作要求 `data` 对象是数据流映射工具中的一个条目，可将其分配给XDM架构字段。 此工作流的映射只需执行一次，并且不涉及对实施进行更改。 但是，这是一个额外的步骤，在XDM对象中发送数据时不需要执行此步骤。</li></ul> |

Adobe建议，如果现有实施使用Adobe Audience Manager标记扩展，则遵循此实施路径。

## 迁移到Web SDK所需的步骤

以下步骤包含要努力实现的具体目标。 选择每个步骤以获取有关如何完成它的详细说明。

+++**1. 创建和配置数据流**

按照以下说明在Adobe Experience Platform数据收集中创建数据流。 当您将数据发送到此数据流时，它会将数据转发到Audience Manager。 将来，同一数据流会将数据转发到Real-Time CDP。

1. 导航到 [experience.adobe.com](https://experience.adobe.com) 并使用您的凭据登录。
1. 使用右上角的主页或产品选择器可导航至 **[!UICONTROL Data Collection]**.
1. 在左侧导航中，选择 **[!UICONTROL Datastreams]**.
1. 选择 **[!UICONTROL New Datastream]**.
1. 输入所需的名称，然后选择 **[!UICONTROL Save]**.
1. 创建数据流后，选择 **[!UICONTROL Add Service]**.
1. 在服务下拉菜单中，选择 **[!UICONTROL Adobe Audience Manager]**.
1. 确保 **[!UICONTROL Enable XDM Flattened Fields]** 选项未选中。

   ![添加Audience Manager服务](assets/add-service.png) {style="border:1px solid lightslategray"}

您的数据流现在已准备好接收数据并将数据传递给Audience Manager。

+++

+++**2. 将Web SDK扩展添加到您的标记属性中**

此部分将为您准备标记，以便进行下一步中的大量迁移工作。

1. 选择Adobe Experience Platform界面左上角的汉堡图标，然后选择 **[!UICONTROL Tags]**.
1. 选择所需的标记属性。
1. 在标记属性的左侧导航中，选择 **[!UICONTROL Extensions]**.
1. 选择 **[!UICONTROL Catalog]** 在顶部附近，可查看所有可用扩展的列表。
1. 搜索并选择 **[!UICONTROL Adobe Experience Platform Web SDK]** 扩展，然后选择 **[!UICONTROL Install]** 在右边。

   ![目录](assets/catalog.png) {style="border:1px solid lightslategray"}

1. 此时会显示扩展配置设置。 找到 **[!UICONTROL Datastreams]** 部分，然后选择您使用的沙盒以及您在上一步中创建的数据流。

   ![数据流选择](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. 选择 **[!UICONTROL Save]**.

您的标记资产现在已安装Web SDK。

+++

+++**3. 创建数据对象数据元素**

数据对象数据元素提供了一个直观的框架，用于配置Web SDK用于发送到数据流的负载。 您在以下步骤中更新的大多数规则都会与此数据元素交互。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL Data Elements]**.
1. 选择 **[!UICONTROL Add Data Element]**
1. 为数据元素指定以下设置：
   * **[!UICONTROL Name]**：您想要的任何内容，例如“数据层”或“数据对象”
   * **[!UICONTROL Extension]**： [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**： [!UICONTROL Variable]
   * 复选框可以保持原样。
1. 在右侧，选择以下设置：
   * “属性”单选按钮： **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**： [!UICONTROL Adobe Audience Manager]
1. 选择 **[!UICONTROL Save]**.

   ![创建数据元素](assets/create-data-element.png) {style="border:1px solid lightslategray"}

标记资产现在具有更新每个规则所需的一切。

+++

+++**4. 更新规则以使用Web SDK扩展而不是Audience Manager扩展**

此步骤包含迁移到Web SDK所需的大部分工作，并且需要了解您的实施的工作方式。 下面提供了有关如何编辑典型标记规则的示例。 更新实施中的所有标记规则，将对Audience Manager扩展的所有引用替换为Web SDK扩展。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL Rules]**.
1. 选择要编辑的规则。
1. 选择操作 **[!UICONTROL Audience Manager - Set Variables]**
1. 请注意在此规则中设置的所有Audience Manager变量。 包含下拉菜单中设置的变量和自定义代码中设置的变量。
1. 更改 [!UICONTROL Action Configuration] 到以下设置：
   * **[!UICONTROL Extension]**： [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**：更新变量
1. 确保在右侧下拉菜单中的第3步中创建的数据对象。 **[!UICONTROL Data element]** 字段。
1. 将Audience Manager键值对设置为与在Audience Manager扩展中配置的相同的各个值。
1. 使用Web SDK扩展复制所有规则逻辑后，选择 **[!UICONTROL Keep Changes]**.
1. 对使用Audience Manager标记扩展设置值的每个操作配置重复这些步骤。

上述步骤仅适用于设置值的规则。 以下步骤将替换使用 [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. 选择发送Web SDK事件的规则。
1. 选择操作类型 **[!UICONTROL Send Event]**.
1. 更改 [!UICONTROL Action Configuration] 到以下设置：
   * **[!UICONTROL Extension]**： [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**： [!UICONTROL Send event]
1. 在右侧，将操作设置更改为以下内容：
   * **[!UICONTROL Type]**：使用 **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**：选择您在步骤3中创建的数据对象。
1. 选择 **[!UICONTROL Keep Changes]**.
1. 对使用Audience Manager发送事件的每个操作配置重复这些步骤。

+++

+++**5. 发布更新的规则**

发布更新规则的工作流程与对标记配置进行的任何其他更改相同。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL Publishing Flow]**.
1. 选择 **[!UICONTROL Add Library]**.
1. 为此标记提交一个名称，如“升级到Web SDK”。
1. 选择 **[!UICONTROL Add All Changed Resources]**.
1. 选择 **[!UICONTROL Save]**.
1. 发布工作流程会显示一个橙色点，指示它正在构建。 一旦圆点变为绿色，您的更改即可在开发环境中使用。
1. 在开发环境中测试您所做的更改，以确保所有规则均正确触发，并且数据对象已使用预期值填充。
1. 准备就绪后，提交库以供审批，构建到暂存，最终审批并发布到生产环境。

   ![发布流](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. 禁用Audience Manager扩展**

将标记实施完全迁移到Web SDK后，您可以禁用Audience Manager扩展。

1. 在标记界面的左侧导航中，选择 **[!UICONTROL Extensions]**.
1. 找到并选择 [!UICONTROL Audience Manager] 扩展。 在右侧，选择 **[!UICONTROL Disable]**.
1. 按照上面的相同发布工作流程发布删除的 [!UICONTROL Audience Manager] 扩展。
1. 在生产环境中禁用该扩展后，您可以将其完全卸载。 选择扩展，选择右侧的三个圆点菜单，然后选择 **[!UICONTROL Uninstall]**.
1. 按照上面的同一发布工作流程将这些更改发布到生产环境。

+++

此时，您的Audience Manager实施已完全迁移到Web SDK，并准备好将来迁移到Real-Time CDP。

