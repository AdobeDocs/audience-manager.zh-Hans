---
description: 构建和管理相似建模中使用的特征或区段。
keywords: relative weight, lookalike
seo-description: 构建和管理相似建模中使用的特征或区段。
seo-title: 关于相似建模
solution: Audience Manager
title: 关于相似建模
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: a6e8db30c54e0629e27b1ee7f189a6c471d2bb6d

---


# 了解相似建模 {#about-algorithmic-models}

## 使用相似建模查找新用户 {#find-new-users}

[!UICONTROL Look-Alike Modeling] 帮助您通过自动化数据分析发现新的独特受众。 当您选择特征或区段、时间间隔以及第一方和第三方数据源时，流程开始。 您的选择为算法模型提供输入。 当分析过程运行时，它会根据所选人群的共享特征来查找合格用户。 完成后，此数据在 [Trait Builder](../../features/traits/about-trait-builder.md) （特征生成器）中可用，您可以在此处使用它根据准确性和范围创 [建特征](../../features/traits/trait-accuracy-reach.md)。 此外，您还可以构建将算法特征与基于规则的特征相结合的细分，并通过布尔表达式和比较运算符添加其他资格要求。 [!UICONTROL Look-Alike Modeling] 为您提供了从所有可用特征数据中提取值的动态方式。

## 优势 {#advantages}

使用的主要益处 [!UICONTROL Look-Alike Modeling] 包括：

* **数据准确性：** 该算法运行规律性强，有助于保持结果的最新和相关性。
* **自动化：** 您不必管理大量静态规则。 算法将为您找到受众。
* **节省时间并减少工作量：** 通过我们的建模过程，您不必猜测哪些特征／细分可能起作用，或将时间资源用于活动以发现新受众。 模型可以帮您完成此操作。
* **可靠性：** 建模功能与服务器端发现和鉴定流程配合使用，这些流程可以评估您自己的数据以及您有权访问的选定第三方数据。 这意味着您不必查看站点上的访客即可确定他们是否具有某个特征。

## 工作流 {#workflow}

您可以在中管理模型 **[!UICONTROL Audience Data > Models]**。 从高度上讲，工作流过程涉及以下几个方面：

* 选择您希望算法评估的基线数据。 这包括特征或区段、时间范围和数据源(您已经通过访问过的您自己的数据和第三方数 [!DNL Audience Manager]据)。 在模型创建工作流中，您可以排除不希望干扰模型的特征。
* 保存模型。 一旦保存，算法评估过程就会自动运行。 但是，请注意，完成此过程最多可能需要7天。 [!DNL Audience Manager] 当算法完成且结果可用于特征创建时，会向您发送电子邮件。
* 在中构建算法特 [!UICONTROL Trait Builder]征。
* 将特征合并到区段中 [!UICONTROL Segment Builder]。
* 创建区段数据并将其发送到目标。

## 疑难解答 {#troubleshooting}

我们会取消激 [!UICONTROL Look-Alike Model] 活任何未能为连续三次运行生成数据的操作。 请注意，之后不能将模型的状态设置回活动状态。 为确保您的模型生成数据，我们建议您从具有足够特征的数据源构建模型以从中累积数据。

## 了解TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] 是专有算法，旨在自动发现新特征。 它将来自您当前特征和区段的特征数据与您访问的所有其他第一方和第三方数据进行比较 [!DNL Audience Manager]。 有关算法发现过程的说明，请参 [!UICONTROL TraitWeight] 阅本节。

<!-- traitweight.xml -->

![](assets/algo_model.png)

以下步骤描述了评估 [!UICONTROL TraitWeight] 过程。

### 第1步：构建特征比较的基线

要构建基线， [!UICONTROL TraitWeight] 请在30天、60天或90天间隔内测量与受众关联的所有特征。 其次，根据特征的频率和相关性对特征进行排序。 频率计数衡量共性。 关联度量特征仅存在于基线受众中的可能性。 通常出现的特征被认为具有高通用性，这是用于在与选定数据源中发现的特征结合时设置加权得分的重要特征。

### 第2步：在数据源中查找相同的特征

在构建基准进行比较后，算法会在所选数据源中查找相同的特征。 在此步骤中，对 [!UICONTROL TraitWeight] 所有已发现的特征执行频率计数，并将它们与基线进行比较。 但是，与基线不同，不常见特征的排名高于那些显示频率更高的特征。 据说，稀有特征显示出高度特异性。 [!UICONTROL TraitWeight] 评估常见基线特征和不常见（高度特定）数据源特征的组合，它们比两个数据集通用的特征更有影响力或更可取。 事实上，我们的模型能够识别这些大的共性特征，并且不会为具有高相关性的数据集分配过多的优先级。 稀有特征具有更高的优先级，因为它们更可能代表新的独特用户，而不是全局通用性高的特征。

### 第3步：分配权重

在此步骤中，按 [!UICONTROL TraitWeight] 照影响力或期望性对新发现的特征进行排名。 权重比例是从0%到100%的百分比。 排名接近100%的特征意味着它们更像基线人口中的受众。 此外，权重较大的特征很有价值，因为它们代表的是新的独特用户，他们的行为可能与您已确立的基准受众相似。 请记住， [!UICONTROL TraitWeight] 将基线中具有高通用性的特征和比较数据源中具有高特异性的特征视为比每个数据集中共有的特征更有价值。

### 第4步：评分用户

所选数据源中的每个用户都会得到一个用户分数，该分数等于该用户用户档案上影响特征的所有权重的总和。 然后，用户得分在0%到100%之间标准化。

### 第5步：显示和处理结果

受众管理器会显示加权模型结果 [!UICONTROL Trait Builder]。 当您要构建算法特征时， [!UICONTROL Trait Builder] 允许您根据算法在数据运行期间生成的加权得分创建特征。 您可以选择更高的准确度，以仅满足用户得分很高且因此与基准受众非常相似的用户，而不是受众的其余部分。 如果要达到更大的受众（到达），可降低精度。

### 第6步：重新评估特征在处理周期中的重要性

定期 [!UICONTROL TraitWeight] 地，根据特征的人口大小和变化重新评估特征的重要性。 随着时间的推移，符合该特征的用户数量会增加或减少。 这种行为在变大的特征中最为明显。 例如，假设算法使用特征A进行建模。 随着特征A的数量增加，可 [!UICONTROL TraitWeight] 以重新评估该特征的重要性，并可以指定较低的分数或忽略它。 在这种情况下，特征A太常见或太大，不能对其人口说出任何重要的话。 在 [!UICONTROL TraitWeight] 降低特征A的值（或在模型中忽略它）后，算法特征的群体会减少。 影响特征的列表反映了基线群体的演化。 使用影响特征的列表来了解这些变化发生的原因。

相关链接：

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [准确性和范围](../../features/traits/trait-accuracy-reach.md)

## 更新相似模型和特征的计划 {#update-schedule}

为新的或现有的算法模型和特征创建和更新计划。

<!-- c_model_update_schedule.xml -->

### 相似模型创建和更新计划

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
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 东部时间下午5点（11月- 3月） </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 美国东部夏令时间下午6点（3月- 11月） </li> 
     </ul> </p> <p>在创建截止日期后构建或克隆的模型将在第二天进行处理。 </p> <p>如果模型的第一次运行没有生成任何数据，它将再次运行，即第二天。 如果第二次尝试也不生成任何数据，则第三次尝试，即第二天。 如果第三次尝试也不生成任何数据，则模型将停止运行。 在这种情况下，我们将取消激活模型。 查看相似模 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 型疑难解答中的更多信息</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>更新模型</b> </td> 
   <td colname="col2"> <p>在理想条件下，现有车型在工作日运行，至少每7天运行一次。 例如，如果您在星期一（截止日期）创建了一个模型，则该模型会在下一个星期一更新为最新版本。 </p> <p>如果模型满足以下任一条件，则将重新运行该模型： </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">上次运行未成功。 </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">在AND系统运行前已成功运行，在过去7天中，它根本没有运行。模型至少附加了一个活动特征。 </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 相似特征创建和更新计划

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
   <td colname="col2"> <p>特征创建过程每天（从星期一到星期五）运行。 通常，新的算法特征在48小时内会显示在UI中。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>更新特征</b> </td> 
   <td colname="col2"> <p>现有特征至少每7天更新一次，并遵循模型更新计划。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 模型列表视图 {#models-list-view}

列表视图是一个中心工作区，可帮助您创建、审阅和管理模型。

<!-- c_models_list_view.xml -->

“模型列表”页面包含帮助您：

* 创建新模型。
* 管理现有模型（编辑、暂停、删除或克隆）。
* 按名称搜索模型。
* 使用任何给定模型创建算法特征。

## 模型摘要视图 {#models-summary-view}

摘要页显示模型详细信息，如名称、范围／准确性、处理历史记录和从模型创建的特征。 该页面还包含允许您创建和管理模型的设置。 单击摘要列表中的模型名称可查看其详细信息。

<!-- c_models_summary.xml -->

模型摘要页面包括以下几节。

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
   <td colname="col2"> <p>显示 <a href="../../features/traits/trait-accuracy-reach.md"> 上次模型运行的准确</a> 、触及数据。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 模型处理历史</span> </p> </td> 
   <td colname="col2"> <p>显示最近10次运行的处理日期和时间以及这些运行是否生成了数据。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 影响力特征</span> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Impoffect Traits</span> table: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 列表模型基准人口中最能代表的50个最具影响力的特征。 </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">按相对权重排名对每个特征进 <span class="wintitle"> 行排名</span> 。 “相 <span class="wintitle"> 对权重</span> ”按影响或期望顺序对新发现的特征进行排序。 权重比例是从0%到100%的百分比。 排名接近100%的特征意味着它们更像基线人口中的受众。 请参 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> 阅了解TraitWeight</a>。 </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">显示每个特征的30天唯一值和总特征人口。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 特征使用模型</span> </p> </td>
   <td colname="col2"> <p>显示基于所选模型的算法特征列表。 单击特征名称或特征ID可了解有关该特征的更多信息。 选 <b><span class="uicontrol"> 择“使用模型创建新特征</span></b> ”以转到算法特征创建过程。 </p> <p>章节标签会根据模型名称而更改。 例如，假设您创建一个模型并将其命名为Model A。加载摘要页面时，此部分的名称将更改为“使用模 <span class="wintitle"> 型A的特征”</span>。 </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [目标](../../features/destinations/destinations.md)
>* [特征](../../features/traits/trait-details-page.md)
>* [区段](../../features/segments/segments-purpose.md)

