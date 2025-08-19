---
description: 构建和管理在相似人群拓展建模中使用的特征或区段。
keywords: 相对权重，相似程度
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: 关于相似人群拓展建模
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# 了解[!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 查找具有[!UICONTROL Look-Alike Modeling]的新用户 {#find-new-users}

[!UICONTROL Look-Alike Modeling]可帮助您通过自动数据分析发现新的独特受众。 当您选择[!UICONTROL trait]或[!UICONTROL segment]、时间间隔以及第一方和第三方[!UICONTROL data sources]时，该进程将开始。 您的选择为算法模型提供输入。 Analytics流程运行时，会根据选定群体的共享特征查找符合条件的用户。 完成后，此数据将在[特征生成器](../../features/traits/about-trait-builder.md)中可用，您可以在其中使用它根据[精度和范围](../../features/traits/trait-accuracy-reach.md)创建特征。 此外，您可以生成将算法特征与[!UICONTROL rules-based traits]相结合的区段，并添加其他包含[!DNL Boolean]表达式和比较运算符的资格要求。 [!UICONTROL Look-Alike Modeling]为您提供了一种从所有可用特征数据中提取值的动态方法。

## 优势 {#advantages}

使用[!UICONTROL Look-Alike Modeling]的主要优势包括：

* **数据准确性：**&#x200B;算法定期运行，这有助于使结果保持最新和相关。
* **自动化：**&#x200B;您不必管理大量静态规则。 算法将为您查找受众。
* **节省时间，减少工作量：**&#x200B;在我们的建模过程中，您不必猜想哪些[!UICONTROL traits]/[!UICONTROL segments]可能会工作或花费时间在营销活动上以发现新受众。 模型可以为您执行此操作。
* **可靠性：**&#x200B;建模适用于评估您自己的数据和您有权访问的所选第三方数据的服务器端发现和鉴定流程。 这意味着您无需在网站上看到访客，即可授予他们使用某个特征的资格。

## 工作流 {#workflow}

您在&#x200B;**[!UICONTROL Audience Data > Models]**&#x200B;中管理模型。 从较高层面来看，工作流过程涉及以下方面：

* 选择您希望算法评估的基线数据。 这包括[!UICONTROL trait]或[!UICONTROL segment]、时间范围和[!UICONTROL data sources]（您自己的数据和您通过[!DNL Audience Manager]已有权访问的第三方数据）。 在模型创建工作流中，您可以排除不想干扰模型的[!UICONTROL traits]。
* 保存模型。 保存后，算法评估过程将自动运行。 但请注意，此过程可能需要7天才能完成。 当算法完成并且结果可用于创建[!DNL Audience Manager]时，[!UICONTROL trait]会向您发送电子邮件。
* 在[!UICONTROL traits]中生成算法[!UICONTROL Trait Builder]。
* 在[!UICONTROL traits]中将[!UICONTROL segments]合并为[!UICONTROL Segment Builder]。
* 创建[!UICONTROL segment]数据并将其发送到[!UICONTROL destination]。

## 故障排除 {#troubleshooting}

我们将取消激活任何无法连续三次生成数据的[!UICONTROL Look-Alike Model]。 请注意，以后不能将模型的状态恢复为“活动”。 为确保您的模型生成数据，我们建议您从数据源构建模型，并使用足够的[!UICONTROL traits]来从中累积数据。

## 了解[!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight]是专用于自动发现新[!UICONTROL traits]的算法。 它将来自您当前[!UICONTROL trait]和[!UICONTROL traits]的[!UICONTROL segments]数据与您通过[!DNL Audience Manager]有权访问的所有其他第一方和第三方数据进行比较。 有关[!UICONTROL TraitWeight]算法发现过程的描述，请参阅此部分。

![](assets/algo_model.png)

以下步骤描述了[!UICONTROL TraitWeight]评估过程。

### 步骤1：构建[!UICONTROL Trait]比较的基线

要构建基线，[!UICONTROL TraitWeight]在30、60或90天间隔内测量与受众关联的所有[!UICONTROL traits]。 接下来，它根据[!UICONTROL traits]的频度和相关性对其进行排名。 频率计数测量通用性。 关联测量[!UICONTROL trait]仅存在于基线受众中的可能性。 经常出现的[!UICONTROL Traits]据说具有高通用性，这是与选定[!UICONTROL traits]中发现的[!UICONTROL data sources]结合使用时用于设置加权得分的重要特性。

### 步骤2：在[!UICONTROL Traits]中找到相同的[!UICONTROL Data Source]

在构建基线以进行比较后，算法会在您选定的[!UICONTROL traits]中查找相同的[!UICONTROL data sources]。 在此步骤中，[!UICONTROL TraitWeight]对所有发现的[!UICONTROL traits]执行频率计数，并将它们与基线进行比较。 但是，与基线不同，不常见的[!UICONTROL traits]的排名高于出现更频繁的。 稀有[!UICONTROL traits]被认为具有高度的特异性。 [!UICONTROL TraitWeight]评估公用基线[!UICONTROL traits]和不公用（高度特定） [!UICONTROL data source] [!UICONTROL traits]的组合比两个数据集公用[!UICONTROL traits]更有影响或更可取。 事实上，我们的模型识别这些大而通用的[!UICONTROL traits]，并且不会为具有高关联性的数据集分配超额优先级。 极少数情况下[!UICONTROL traits]获得更高的优先级，因为它们更有可能代表新的独特用户，而不是[!UICONTROL traits]，这些用户在所有方面具有高通用性。

### 步骤3：分配权重

在此步骤中，[!UICONTROL TraitWeight]按影响或期望的顺序为新发现的[!UICONTROL traits]排名。 重量刻度是从0%到100%的百分比。 [!UICONTROL Traits]的排名更接近100%，这意味着他们在您的基线群体中更像受众。 此外，重权重[!UICONTROL traits]很有价值，因为它们代表新的独特用户，这些用户的行为可能与您建立的基线受众类似。 请记住，[!UICONTROL TraitWeight]认为在基线中具有高通用性和在比较的数据源中具有高特定性的[!UICONTROL traits]比在每个数据集中通用的[!UICONTROL traits]更有价值。

### 步骤4：对用户进行评分

所选[!UICONTROL data sources]中的每个用户都获得了用户得分，该得分等于该用户配置文件上具有影响力的[!UICONTROL traits]的所有权重之和。 然后，用户分数被标准化为0到100%。

### 步骤5：显示和处理结果

[!DNL Audience Manager]在[!UICONTROL Trait Builder]中显示您的加权模型结果。 当您要生成[!UICONTROL algorithmic trait]时，[!UICONTROL Trait Builder]允许您根据算法在数据运行期间生成的加权分数创建[!UICONTROL traits]。 您可以选择更高的准确性，以便仅授予用户得分非常高，因此与基线受众非常相似的合格用户，而不是其余受众。 如果您希望联系更大的受众（范围），则可以降低准确性。

### 步骤6：重新评估[!UICONTROL Trait]在处理周期中的重要性

[!UICONTROL TraitWeight]会定期根据该[!UICONTROL trait]群体的大小和变化重新评估[!UICONTROL trait]的重要性。 当符合该[!UICONTROL trait]资格的用户数量随时间增加或减少时，会发生这种情况。 这种行为在变得非常大的特征中表现得最为明显。 例如，假设算法使用[!UICONTROL trait A]进行建模。 随着[!UICONTROL trait A]的群体增加，[!UICONTROL TraitWeight]重新评估该[!UICONTROL trait]的重要性，可能会分配较低的得分或忽略该分数。 在这种情况下，[!UICONTROL trait A]太常见或太大，无法对其群体提供任何重要信息。 在[!UICONTROL TraitWeight]减少[!UICONTROL trait A]的值（或在模型中忽略该值）后，算法特征的填充量会减少。 具有影响力的[!UICONTROL traits]列表反映了基线群体的演变。 使用具有影响力的[!UICONTROL traits]列表了解这些更改发生的原因。

相关链接：

* [模型生成器](../../features/algorithmic-models/create-model.md)
* [精度和范围](../../features/traits/trait-accuracy-reach.md)

## 更新[!UICONTROL Look-Alike Models]和[!UICONTROL Traits]的计划 {#update-schedule}

为新的或现有的[!UICONTROL algorithmic models]和[!UICONTROL traits]创建和更新计划。

### [!UICONTROL Look-Alike Model]创建和更新计划

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> 活动类型 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>创建或克隆模型</b> </td>
   <td colname="col2"> <p>对于新的或克隆的[!UICONTROL Look-Alike Models]，创建过程每天运行一次，时间为： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 东部时间下午5点（11月至3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 东部夏令时间下午6点（3月至11月） </li> 
     </ul> </p> <p>在创建截止日期之后构建或克隆的模型将在第二天进行处理。 </p> <p>如果第一次运行模型时没有生成任何数据，它将于次日（即第二天）再次运行。 如果第二次尝试也未生成任何数据，则会在次日进行第三次尝试。 如果第三次尝试也未生成任何数据，则模型将停止运行。 在这种情况下，我们将取消激活模型。 在<a href="../../features/algorithmic-models/understanding-models.md#troubleshooting">中查看更多相似模型疑难解答</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想情况下，现有模型在工作日运行，至少每7天运行一次。 例如，如果您在星期一创建模型（截止日期），则它最晚会更新下一星期一。 </p> <p>如果模型满足以下任一条件，则会重新运行： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">上次运行未成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它以前已成功运行，但在过去7天内根本没有运行，并且模型至少附加了一个活动特征。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait]创建和更新计划

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
   <td colname="col2"> <p>特征创建过程每天运行，从星期一到星期五。 通常，新的算法特征会在48小时内出现在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特征</b> </td> 
   <td colname="col2"> <p>现有特征至少每7天更新一次，并遵循模型更新计划。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型列表视图 {#models-list-view}

列表视图是一个中央工作区，可帮助您创建、查看和管理模型。

[!UICONTROL Models]列表页面包含可帮助您：

* 创建新模型。
* 管理现有模型（编辑、暂停、删除或克隆）。
* 按名称搜索模型。
* 使用任何给定模型创建[!UICONTROL algorithmic traits]。

## 模型摘要视图 {#models-summary-view}

摘要页面显示模型详细信息，例如名称、范围/精度、处理历史记录以及从模型创建的[!UICONTROL traits]。 该页面还包括允许您创建和管理模型的设置。 单击摘要列表中的模型名称可查看其详细信息。

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
   <td colname="col1"> <p> <span class="wintitle">基本信息</span> </p> </td>
   <td colname="col2"> <p>包括有关模型的基本信息，如模型名称和上次运行时间。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">模型访问范围和准确性</span> </p> </td> 
   <td colname="col2"> <p>显示上次模型运行的<a href="../../features/traits/trait-accuracy-reach.md">精度和范围</a>数据。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">模型处理历史记录</span> </p> </td> 
   <td colname="col2"> <p>显示最后10次运行的处理日期和时间，以及这些运行中是否生成了数据。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">个具有影响力的特征</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">具影响力的特征</span>表： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列出在模型的基线群体中表现最好的前50个具有影响力的特征。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">按每个特征的<span class="wintitle">相对权重</span>排名对其排名。 <span class="wintitle">相对权重</span>按影响或期望的顺序对新发现的特征进行排序。 重量刻度是从0%到100%的百分比。 特征排名更接近100%，这意味着它们更像是基线人口中的受众。 请参阅<a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight">了解TraitWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">显示30天独特性以及每个特征的总特征人口。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 使用模型<span class="wintitle">的</span>特征 </p> </td>
   <td colname="col2"> <p>显示基于所选模型的算法特征列表。 单击特征名称或特征ID，以了解有关该特征的更多信息。 选择<b><span class="uicontrol">使用模型</span></b>创建新特征以转到算法特征创建过程。 </p> <p>部分标签会根据模型的名称而更改。 例如，假设您创建了一个模型并将其命名为“模型A”。加载摘要页面时，此部分的名称将使用模型A<span class="wintitle">更改为</span>个特征。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目标](../../features/destinations/destinations.md)
>* [特征](../../features/traits/trait-details-page.md)
>* [区段](../../features/segments/segments-purpose.md)
