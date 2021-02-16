---
description: 构建和管理相似建模中使用的特征或细分。
keywords: 相对权重，相似
seo-description: 构建和管理相似建模中使用的特征或细分。
seo-title: 关于相似建模
solution: Audience Manager
title: 关于相似建模
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1593'
ht-degree: 1%

---


# 了解[!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 查找[!UICONTROL Look-Alike Modeling] {#find-new-users}的新用户

[!UICONTROL Look-Alike Modeling] 帮助您通过自动化数据分析发现新的独特受众。当您选择[!UICONTROL trait]或[!UICONTROL segment]、时间间隔以及第一方和第三方[!UICONTROL data sources]时，进程开始。 您的选择为算法模型提供输入。 当分析过程运行时，它会根据所选人群的共享特征来查找符合条件的用户。 完成后，此数据在[特征生成器](../../features/traits/about-trait-builder.md)中可用，您可以使用它根据[准确性创建特征并到达](../../features/traits/trait-accuracy-reach.md)。 此外，您还可以构建将算法特征与[!UICONTROL rules-based traits]结合在一起的细分，并通过[!DNL Boolean]表达式和比较运算符添加其他资格要求。 [!UICONTROL Look-Alike Modeling] 为您提供了从所有可用特征数据中提取值的动态方式。

## 优势 {#advantages}

使用[!UICONTROL Look-Alike Modeling]的主要益处包括：

* **数据准确性：** 算法定期运行，有助于使结果保持最新且相关。
* **自动** 化：您不必管理大量静态规则。算法将为您找到受众。
* **节省时间并减少工作量：** 通过我们的建模过程，您不必猜测哪些功 [!UICONTROL traits]能可[!UICONTROL segments] 能有效或将时间资源花在活动上即可发现新受众。模型可以为您执行此操作。
* **可靠性：** 建模可与服务器端发现和鉴定流程结合使用，这些流程可评估您自己的数据和您有权访问的选定第三方数据。这意味着您不必查看网站上的访客即可确定其是否具有某个特征。

## 工作流 {#workflow}

在&#x200B;**[!UICONTROL Audience Data > Models]**&#x200B;中管理模型。 从高层来说，工作流过程涉及以下方面：

* 选择要算法评估的基线数据。 这包括[!UICONTROL trait]或[!UICONTROL segment]、时间范围和[!UICONTROL data sources]（您已通过[!DNL Audience Manager]访问过自己的数据和第三方数据）。 在模型创建工作流中，可以排除不想与模型相干的[!UICONTROL traits]。
* 保存模型。 一旦保存，算法评估过程将自动运行。 但是，请注意，完成此过程最多可能需要7天。 [!DNL Audience Manager] 当算法完成且结果可供创建时，会向您发送电子 [!UICONTROL trait] 邮件。
* 在[!UICONTROL Trait Builder]中构建算法[!UICONTROL traits]。
* 将[!UICONTROL traits]合并到[!UICONTROL Segment Builder]中的[!UICONTROL segments]中。
* 创建[!UICONTROL segment]数据并将其发送到[!UICONTROL destination]。

## 疑难解答 {#troubleshooting}

我们将取消激活任何未能为连续三个运行生成数据的[!UICONTROL Look-Alike Model]。 请注意，之后不能将模型的状态设置回活动状态。 为确保您的模型生成数据，我们建议您从数据源中构建模型，并且该数据源的[!UICONTROL traits]足以累积数据。

## 了解[!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] 是一种专有的算法，旨在自动发现 [!UICONTROL traits] 新内容。它将当前[!UICONTROL traits]和[!UICONTROL segments]中的[!UICONTROL trait]数据与您通过[!DNL Audience Manager]访问的所有其他第一方和第三方数据进行比较。 有关[!UICONTROL TraitWeight]算法发现过程的说明，请参阅本节。

![](assets/algo_model.png)

以下步骤描述了[!UICONTROL TraitWeight]评估过程。

### 第1步：为[!UICONTROL Trait]比较生成基线

要构建基线，[!UICONTROL TraitWeight]在30、60或90天间隔内测量与受众关联的所有[!UICONTROL traits]。 然后，根据其频率和相关性对[!UICONTROL traits]进行排名。 频率计数可衡量通用性。 关联度量[!UICONTROL trait]仅在基线受众中存在的可能性。 [!UICONTROL Traits] 这通常被说为具有高通用性，这是在与在选定内容中发现的加权分数进行组合时用于设 [!UICONTROL traits] 置加权分数的重要特 [!UICONTROL data sources]征。

### 第2步：在[!UICONTROL Data Source]中查找相同的[!UICONTROL Traits]

在生成要比较的基线后，算法会在所选[!UICONTROL data sources]中查找相同的[!UICONTROL traits]。 在此步骤中，[!UICONTROL TraitWeight]执行所有发现的[!UICONTROL traits]的频率计数，并将它们与基线进行比较。 但是，与基线不同，不常见的[!UICONTROL traits]排名高于显示频率更高的排名。 据说稀有[!UICONTROL traits]表现出高度特异性。 [!UICONTROL TraitWeight] 评估共同基准和不 [!UICONTROL traits] 常见（高度特定）的组合 [!UICONTROL data source] [!UICONTROL traits] 比两个数据集 [!UICONTROL traits] 的共性更具影响力或可取。事实上，我们的模型能够识别这些大的、常见的[!UICONTROL traits]，并且不会为关联度高的数据集分配过多的优先级。 极少数[!UICONTROL traits]会获得更高的优先级，因为与具有较高通用性的[!UICONTROL traits]相比，它们更可能代表新的独特用户。

### 第3步：分配权重

在此步骤中，[!UICONTROL TraitWeight]按照影响或可取性的顺序对新发现的[!UICONTROL traits]进行排名。 权重比例是介于0%到100%之间的百分比。 [!UICONTROL Traits] 排名接近100%意味着它们更像基线人口中的受众。此外，重加权[!UICONTROL traits]很有价值，因为它们代表新的、独特的用户，这些用户的行为可能与您既定的基准受众相似。 请记住，[!UICONTROL TraitWeight]认为，在基线中具有高通用性，在比较的数据源中具有高特异性，这比每个数据集中的[!UICONTROL traits]更有价值。[!UICONTROL traits]

### 第4步：评分用户

所选[!UICONTROL data sources]中的每个用户都将获得一个用户分数，该分数等于该用户用户档案上有影响力的[!UICONTROL traits]的所有权重的总和。 然后，将用户分数标准化为0%到100%。

### 第5步：显示和处理结果

[!DNL Audience Manager] 显示加权模型结果 [!UICONTROL Trait Builder]。当您要构建[!UICONTROL algorithmic trait]时，[!UICONTROL Trait Builder]允许您根据算法在数据运行期间生成的加权得分创建[!UICONTROL traits]。 您可以选择更高的准确度，以仅限定用户分数非常高的用户，因此与基准受众非常相似，而不是受众的其余部分。 如果您希望达到更大的受众（触及范围），则可以降低准确性。

### 第6步：重新评估[!UICONTROL Trait]在处理周期中的重要性

[!UICONTROL TraitWeight]定期根据[!UICONTROL trait]的人口大小和变化重新评估[!UICONTROL trait]的重要性。 随着时间的推移，符合该[!UICONTROL trait]条件的用户数量增加或减少。 这种行为在变得非常大的特征中最为明显。 例如，假设算法使用[!UICONTROL trait A]进行建模。 随着[!UICONTROL trait A]的人口增加，[!UICONTROL TraitWeight]会重新评估该[!UICONTROL trait]的重要性，并可能会分配较低的分数或忽略它。 在这种情况下，[!UICONTROL trait A]太常或太大，不能对其人口说出任何重要的话。 在[!UICONTROL TraitWeight]降低[!UICONTROL trait A]的值（或在模型中忽略它）后，算法特征的种群会减少。 影响[!UICONTROL traits]的列表反映了基线种群的演化。 使用有影响力的[!UICONTROL traits]的列表来了解发生这些更改的原因。

相关链接：

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [精度和范围](../../features/traits/trait-accuracy-reach.md)

## [!UICONTROL Look-Alike Models]和[!UICONTROL Traits] {#update-schedule}的更新计划

为新的或现有的[!UICONTROL algorithmic models]和[!UICONTROL traits]创建和更新计划。

### [!UICONTROL Look-Alike Model] 创建和更新计划

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
   <td colname="col2"> <p>对于新的或克隆的[!UICONTROL相似模型]，创建过程每天运行一次： 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 东部标准时间下午5点（11月 — 3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 美国东部夏令时间下午6点（3月 — 11月） </li> 
     </ul> </p> <p>在创建截止日期之后构建或克隆的模型将在第二天进行处理。 </p> <p>如果模型的第一次运行没有生成任何数据，它将再次运行，即第二天。 如果第二次尝试也未生成任何数据，则第三次尝试，即第二天。 如果第三次尝试也未生成任何数据，则模型将停止运行。 在这种情况下，我们将取消激活模型。 请参阅<a href="../../features/algorithmic-models/understanding-models.md#troubleshooting">类似型模型疑难解答</a>中的更多信息。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想条件下，现有车型在工作日运行，至少每7天运行一次。 例如，如果您在星期一（截止日期）创建了一个模型，则它会在下一个星期一最晚更新。 </p> <p>如果模型满足以下任一条件，将重新运行该模型： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">它上次的运行没有成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">它在过去7天中根本没有运行，而且模型至少附加了一个活动特征。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] 创建和更新计划

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
   <td colname="col2"> <p>特征创建过程每天（周一至周五）运行。 通常，新的算法特征会在48小时内显示在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特征</b> </td> 
   <td colname="col2"> <p>现有特征至少每7天更新一次，并按照计划更新模型。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型列表视图{#models-list-view}

列表视图是一个中心工作区，可帮助您创建、审阅和管理模型。

[!UICONTROL Models]列表页面包含有助于您：

* 创建新模型。
* 管理现有模型（编辑、暂停、删除或克隆）。
* 按名称搜索模型。
* 使用任何给定型号创建[!UICONTROL algorithmic traits]。

## 模型摘要视图{#models-summary-view}

摘要页显示模型详细信息，如名称、访问/准确性、处理历史记录以及从模型创建的[!UICONTROL traits]。 该页面还包含允许您创建和管理模型的设置。 单击摘要列表中的模型名称以查看其详细信息。

“模型摘要”页包含以下部分。

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
   <td colname="col2"> <p>包括有关模型的基本信息，如其名称和上次运行时间。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型范围和准确性</span> </p> </td> 
   <td colname="col2"> <p>显示<a href="../../features/traits/trait-accuracy-reach.md">准确性并达到上次运行模型的</a>数据。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型处理历史记录</span> </p> </td> 
   <td colname="col2"> <p>显示最近10个运行的处理日期和时间，以及这些运行是否生成了数据。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 影响力特征</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">影响特征</span>表： </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列表模型基准群体中最能代表的50个最具影响力的特征。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">按其<span class="wintitle">相对权重</span>排名对每个特征进行排名。 <span class="wintitle">相对权重</span>按影响或可取性对新发现的特征进行排序。 权重比例是介于0%到100%之间的百分比。 排名接近100%的特征意味着它们更像基线人口中的受众。 请参阅<a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight">了解TraitWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">显示每个特征的30天唯一值和总特征人口。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 特征使用模型</span> </p> </td>
   <td colname="col2"> <p>显示基于所选模型的算法特征列表。 单击特征名称或特征ID可了解有关该特征的详细信息。 选择<b><span class="uicontrol">使用Model</span></b>创建新特征以转到算法特征创建过程。 </p> <p>章节标签会根据模型的名称而更改。 例如，假设您创建一个模型并将其命名为Model A。加载摘要页面时，此部分的名称将更改为<span class="wintitle">使用模型A</span>的特征。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目标](../../features/destinations/destinations.md)
>* [特征](../../features/traits/trait-details-page.md)
>* [区段](../../features/segments/segments-purpose.md)

