---
description: 构建和管理算法建模中使用的特征或区段，也称为相似建模。模型功能位于Audience Data> Model中。
keywords: 相对权重，相似度
seo-description: 构建和管理算法建模中使用的特征或区段，也称为相似建模。模型功能位于Audience Data> Model中。
seo-title: 关于算法模型
solution: Audience Manager
title: 关于算法模型
topic: DIL API
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# 关于算法模型 {#about-algorithmic-models}

构建和管理算法建模中使用的特征或区段，也称为相似建模。模型功能 **[!UICONTROL Audience Data > Models]**&#x200B;位于中。

<!-- c_models.xml -->

## 了解算法模型 {#understanding-models}

以下部分介绍了算法建模的审阅 [!DNL Audience Manager]。它们描述了建模的工作原理、优点和工作流。

<!-- understanding-models.xml -->

## 使用算法建模查找新用户 {#find-new-users}

算法建模可帮助您通过自动数据分析发现新的、独特的受众。该过程在您选择特征或区段、时间间隔以及第一方和第三方数据源时开始。您的选择为算法模型提供了输入。在分析过程运行时，它会根据选定人群的共享特征查找符合条件的用户。完成后，该数据可在 [Travientity Builder中使用，](../../features/traits/about-trait-builder.md) 您可以在这里使用它来根据 [准确性和触及范围创建特征](../../features/traits/trait-accuracy-reach.md)。此外，您还可以构建将算法特征与基于规则的特征相结合的细分，并通过Boolean表达式和比较运算符添加其他资质要求。算法建模可为您提供一种从所有可用特征数据中提取值的动态方法。

## 优势 {#advantages}

[!DNL Audience Manager] 使用建模的主要益处包括：

* **数据准确性：** 算法会定期运行，有助于保持结果的相关性和相关性。
* **自动化：** 您不必管理大量的静态规则。算法会为您找到受众。
* **节省时间并减少工作量：** 通过我们的建模过程，您无需猜测哪些特征/细分可以在营销活动上使用时间资源来发掘新受众。模型可以为您完成此操作。
* **可靠性：** 建模可与服务器端发现和资格处理功能配合使用，这些流程评估您自己的数据以及您有权访问的选定第三方数据。这意味着您不必在您的网站上看到访客才能获得特征。

## 工作流 {#workflow}

您可以管理模型 **[!UICONTROL Audience Data > Models]**。在较高级别，工作流程流程涉及：

* 选择您希望算法评估的基准数据。这包括特征或区段、时间范围和数据源(您自己拥有访问的数据和第三方数据 [!DNL Audience Manager])。在创建工作流中，您可以排除不想干扰模型的特征。
* 保存模型。保存后，算法评估过程将自动运行。但是请注意，完成此过程可能需要长达天的时间。[!DNL Audience Manager] 算法已完成并结果可用于特征创建时向您发送电子邮件。
* 构建算法特征 [!UICONTROL Trait Builder]。
* 将特征整合到细分中 [!UICONTROL Segment Builder]。
* 创建区段数据并将其发送到目标。

## 疑难解答 {#troubleshooting}

我们会取消激活无法生成三个连续运行数据的任何算法模型。请注意，以后您不能将模型的状态重新设置为活动状态。为了确保模型生成数据，我们建议您从数据源构建模型，具有足够的特征来积累数据。

>[!MORE_ LIKE_ This]
>
>* [目标](../../features/destinations/destinations.md)
>* [特征](../../features/traits/trait-details-page.md)
>* [区段](../../features/segments/segments-purpose.md)


## 了解Tritweight {#understanding-traitweight}

[!UICONTROL TraitWeight] 是专门用于自动发现新特征的专有算法。它会将当前特征和细分中的特征与您有权访问的所有其他和第三方数据进行对比 [!DNL Audience Manager]。有关 [!UICONTROL TraitWeight] 算法发现过程的说明，请参阅本节。

<!-- traitweight.xml -->

![](assets/algo_model.png)

以下步骤介绍 [!UICONTROL TraitWeight] 了评估过程。

### 步骤1：为特征对比构建基线

要构建基准， [!UICONTROL TraitWeight] 请测量与受众相关的所有特征(30、60或90天间隔)。接下来，它根据特征及其相关性对特征进行排名。频率计数衡量共性。相关性衡量特征仅在基准受众中存在的可能性。经常出现的特征通常被称为高共同性，这是一个重要特性，用于组合在选定数据源中发现的特征时设置加权得分。

### 步骤2：在数据源中查找相同的特征

在构建基准比较后，算法会在选定的数据源中查找相同的特征。在此步骤中， [!UICONTROL TraitWeight] 对所有发现的特征执行频率计数，并将它们与基线进行比较。但是，与基线不同，不常见特征的排名高于显示频率更高的特征。稀有特征表示表现力很高。[!UICONTROL TraitWeight] 检查常见基线特征和不常见(高度特定)数据源特征的组合，它们比两个数据集通用的特征更具影响力或更理想。事实上，我们的模型识别了这些大的常见特征，并不会为高度相关的数据集分配多余的优先级。稀有特征获得了更高的优先级，因为它们比展示板中具有高通用性的特征代表新的独特用户。

### 步骤3：指定粗细

在此步骤中， [!UICONTROL TraitWeight] 按影响或可伸缩性排列新发现的特征。粗细比例是从0%到100%的百分比。接近100%的特征意味着它们更类似于基线人群中的受众。而且，大量加权特征非常重要，因为它们代表的是新的、独特的用户，其行为可能与现有的基线受众相似。请记住， [!UICONTROL TraitWeight] 在比较数据源中，在基准和高特异性方面具有高共通性，比每个数据集中常用的特征更有价值。

### 第步：评分用户

选定数据源中的每个用户获得的用户分数等于该用户个人资料上具有影响特征的所有权重的总和。用户得分随后将标准化到100%之间。

### 第步：显示和使用结果

Audience Manager [!UICONTROL Trait Builder]会显示您的加权模型。当您希望构建算法特征时， [!UICONTROL Trait Builder] 可根据数据运行过程中算法生成的加权分数创建特征。您可以选择更高的准确性，以仅符合具有非常高用户得分的用户的资格，因此与基准受众而非其他受众非常相似。如果您希望触及更大的受众(触及范围)，您可以降低准确性。

### 步骤6：重新评估跨处理周期特征的重要性

根据 [!UICONTROL TraitWeight] 特征的大小和变化，定期重新评估特征的重要性。这是因为随着时间的推移，符合特征的用户数会增加或减少。在特征变得非常大的特征中，这种行为最为明显。例如，假设算法使用特征A进行建模。特征A的人口增加， [!UICONTROL TraitWeight] 重新评估该特征的重要性，并可能分配较低得分或忽略分数。在这种情况下，特征A太常见或太大，对其人口有重要意义。在 [!UICONTROL TraitWeight] 降低Travientity A值(或忽略模型中的值)后，算法特征的人口会减少。具有影响力的特征列表反映了基线群体的发展。使用具有影响力的特征列表了解这些更改的发生原因。

相关链接：

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [准确性和触及力](../../features/traits/trait-accuracy-reach.md)

## 算法模型和特征的更新计划 {#update-schedule}

创建和更新新的或现有算法模型和特征的计划。

<!-- c_model_update_schedule.xml -->

### 算法模型创建和更新计划

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> 活动类型 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>创建或仿制模型</b> </td>
   <td colname="col2"> <p>对于新的或仿制的算法模型，创建过程每天运行一次： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> EST EST(11月-三月) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 太平洋时间下午点(月-十一月) </li> 
     </ul> </p> <p>在创建截止日期后构建或仿制的模型将在第二天进行处理。 </p> <p>如果第一次运行模型不生成数据，第二次运行时将再次运行。如果第二次尝试还没有生成任何数据，则第二次尝试将在第三天尝试。如果第三次尝试也不生成任何数据，则模型将停止运行。在这种情况下，我们将停用该模型。请参阅解决算法模型 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"></a>疑难解答。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想情况下，现有模型在工作日运行，每天至少一次。例如，如果您在星期一创建了一个模型(截止日期)，则会在星期一更新以下内容。 </p> <p>如果某个模型满足下列任一条件，则将重新运行该模型： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">其上次运行失败。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它之前成功运行，但过去天没有运行，并且模型至少附加了一个活动特征。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 算法特征创建和更新计划

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 活动类型 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>创建特征</b> </td> 
   <td colname="col2"> <p>特征创建过程将在星期一至星期五之间运行。通常，在48小时内UI中会出现新的算法特征。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特征</b> </td> 
   <td colname="col2"> <p>现有特征至少每天更新一次，并按照模型更新计划进行更新。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型列表视图 {#models-list-view}

列表视图是一个中央工作区，可帮助您创建、审阅和管理模型。

<!-- c_models_list_view.xml -->

“模型”列表页面包含可帮助您：

* 创建新模型。
* 管理现有模型(编辑、暂停、删除或克隆)。
* 按名称搜索模型。
* 使用任何给定的模型创建算法特征。

## 模型摘要视图 {#models-summary-view}

摘要页面显示模型详细信息，如名称、范围/准确性、处理历史记录以及从模型创建的特征。该页面还包含允许您创建和管理模型的设置。单击摘要列表中的模型名称以查看其详细信息。

<!-- c_models_summary.xml -->

模型摘要页面包括以下部分。

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 区域 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> 基本信息</span> </p> </td>
   <td colname="col2"> <p>包括有关模型的基本信息，如名称和上次运行时的名称。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型范围和准确性</span> </p> </td> 
   <td colname="col2"> <p>显示 <a href="../../features/traits/trait-accuracy-reach.md"> 上一模型运行的准确性和触及</a> 范围。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型处理历史</span> </p> </td> 
   <td colname="col2"> <p>显示最后10运行的处理日期和时间，以及是否生成这些运行的数据。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 具有影响力的特征</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 具有影响力的特征</span> 表： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出在模型的基线人群中表现最好的50个具有影响力的特征。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">按 <span class="wintitle"> 相对权重</span> 排名排列每个特征。<span class="wintitle"> 相对权重</span> 按影响或可伸缩性排序新发现的特征。粗细比例是从0%到100%的百分比。接近100%的特征意味着它们更类似于基线人群中的受众。请参阅 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> 了解Tritweight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">显示每个特征的30天统一和特征总数。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 使用模型的特征</span> </p> </td>
   <td colname="col2"> <p>显示基于选定模型的算法特征列表。单击特征名称或特征ID以了解有关特征的更多信息。选择 <b><span class="uicontrol"> “使用模型</span></b> 创建新特征”可转到算法特征创建流程。 </p> <p>章节标签根据您的模型名称进行更改。例如，假设您创建一个模型并将其命名为A Model A。加载摘要页面时，此部分的名称会更改为 <span class="wintitle"> 使用模型A</span>的属性。 </p> </td>
  </tr>
 </tbody>
</table>