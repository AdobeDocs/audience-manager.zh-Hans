---
description: 特征排除在建模工作流程中提供额外的控制，允许您根据域专业知识和法规要求为模型添加必要的防护边栏。使用“排除”选项可选择从一个或多个数据源创建模型时要忽略的特征。
seo-description: 特征排除在建模工作流程中提供额外的控制，允许您根据域专业知识和法规要求为模型添加必要的防护边栏。使用“排除”选项可选择从一个或多个数据源创建模型时要忽略的特征。
seo-title: 算法模型特征排除
title: 算法模型特征排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在建模工作流程中提供其他控件，允许您根据域专业知识和法规要求为模型添加必要的防护边栏。Use the [!UICONTROL Exclusions] option to select which traits to ignore when creating models from one or more data sources.

## 用例 {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] 使您能够排除特定的捕获特征，如站点访客特征，因此您不会对模型产生偏差，从而导致结果单调。
* 您可以删除不了解或不信任数据来源的特征，以更好地了解影响力的特征。
* 您可以排除某些特征(如人口统计特征)，以帮助您履行可能具有的任何合规性义务。

>[!IMPORTANT]
>
>第三个用例上的重要说明。If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. 创建模型后，不能排除建模中的特征。See [Important Aspects &amp; Limitations](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). 请在使用此功能时务必小心，并与数据提供程序一起工作以确保您获知对源结构的任何更改。

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. [!UICONTROL Exclusions] 选择将灰显，直到您选择一个或多个数据源进行建模。
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. **[!UICONTROL Select Traits to Exclude]** 在窗口中，您可以看到与之前选定的数据源关联的所有特征。选择要排除的特征。
4. 您可以按特征类型筛选特征，也可以浏览特征文件夹。请注意，特征文件夹仅显示与选定数据源关联的特征。
5. Press **[!UICONTROL Exclude Selected Traits]**.

>[!TIP]
>
>您可以排除文件夹特征，而不是逐个排除文件夹中的特征，从而排除整个文件夹。例如，在具有20种特征的文件夹中，您只需要排除文件夹特征，而不是逐个排除所有特征。

如果您喜欢视频教程，请观看我们的“特征排除”视频演示：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=chi_hans)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>模型摘要视图中排除的特征 </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>基于角色的访问控制(CLUAC) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>修改模型后修改被排除的特征 </p> </td>
   <td colname="col2"> <p>创建并保存模型后，不能修改已排除的特征。如果要调整结果，则可以仿制模型并更改排除的特征。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可以排除的最大特征数 </p> </td>
   <td colname="col2"> <p>可从模型中排除的最大特征数为500。使用文件夹特征最大限度地发挥排除功能。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基线特征 </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## 相关链接

* [关于算法特征](/help/using/features/algorithmic-models/understanding-models.md)
* [特征排除-教程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)