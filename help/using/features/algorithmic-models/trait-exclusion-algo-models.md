---
description: 特征排除在建模工作流程中提供了其他控件，允许您根据您的域专业知识和法规要求向模型添加必要的防护栏。 使用“排除”选项，在从一个或多个数据源创建模型时选择要忽略的特征。
seo-description: 特征排除在建模工作流程中提供了其他控件，允许您根据您的域专业知识和法规要求向模型添加必要的防护栏。 使用“排除”选项，在从一个或多个数据源创建模型时选择要忽略的特征。
seo-title: 算法模型特征排除
title: 算法模型特征排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
translation-type: tm+mt
source-git-commit: e6e22c0c4a8f1374d3d8d18cb7b242e18a29571f

---


# 相似建模：特征排除 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在建模工作流程中提供其他控件，允许您根据您的域专业知识和法规要求向模型添加必要的防护栏。 使用选 [!UICONTROL Exclusions] 项，在从一个或多个数据源创建模型时选择要忽略的特征。

## 用例 {#use-cases}

以下是一些用例，您可以通过以下方式解决 [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] 允许您排除某些“全部捕获”特征(如站点访客特征)，因此您不会偏倚模型，导致平坦结果。
* 您可以从数据源中删除您不知道或不信任的特征，以更好地了解这些有影响力的特征。
* 您可以排除某些特征（如人口统计特征），以帮助履行您可能承担的任何合规义务。

>[!IMPORTANT]
>
>关于第三个用例的重要说明。 如果第三方数据提供者在您创建模型后向数据馈送添加 *了新的人口统计特征*，则该特征会由模型自动选取。 在创建模型后，不能从建模中排除特征。 请参 [阅重要方面和限制](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)。 在使用此功能时请务必小心，并与数据提供者合作，以确保您获悉对供给结构的任何更改。

![](assets/lam_exclude_traits.png)

## 如何使用特征排除 {#how-to-use}

使用“构 [建模型”工作流](../../features/algorithmic-models/create-model.md#build-model) ，构建新的算法模型。

1. 在您 [!UICONTROL Exclusions] 为建模选择一个或多个数据源之前，选择的内容将灰显。
2. 选择一个或多个数据源进行建模后，按 **[!UICONTROL Browse All Traits]**。
3. 在窗口 **[!UICONTROL Select Traits to Exclude]** 中，您可以看到与您之前选择的数据源关联的所有特征。 选择要排除的特征。
4. 您可以按特征类型、特征填充类型([设备ID](../../reference/ids-in-aam.md) 和 [跨设备ID](../../reference/ids-in-aam.md))筛选特征，也可以浏览特征文件夹。 请注意，特征文件夹只显示与所选数据源关联的特征。
5. Press **[!UICONTROL Exclude Selected Traits]**.

![trait-exclusions](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>通过排除文件夹特征而不是逐个排除文件夹中的特征，可以排除整个文件夹。 例如，在具有20个特征的文件夹中，您只需排除文件夹特征，而不是逐个排除所有特征。

如果您喜欢视频教程，请观看我们的“特征排除”视频演示：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

## 重要方面和限制 {#important-aspects-and-limitations}

请注意以下方面和限制 [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 项目 </th> 
   <th colname="col2" class="entry"> 描述 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>“模型汇总”视图中排除的特征 </p> </td>
   <td colname="col2"> <p>被排除的特 <i>征不会显示在“模型摘要</i> ”视图中。 您只能在“编辑模型”工作流中查看被排 <b><span class="uicontrol"> 除的特征</span></b> 。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>基于角色的访问控制(RBAC) </p> </td>
   <td colname="col2"> <p>请注意以下对于使用 <a href="../../features/administration/administration-overview.md#administration"> RBAC的公司的限制</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">如果您无权视图某个特征，则无 <i>法选择</i> 要从模型中排除的该特征。 </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">如果您无权视图某个特征，则无法在被排除的 <i>特征列表</i> 中视图该特征。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>在保存模型后修改被排除的特征 </p> </td>
   <td colname="col2"> <p>在创建并保存模型后，不能修改被排除的特征。 如果要调整结果，可克隆模型并更改被排除的特征。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可排除的最大特征数 </p> </td>
   <td colname="col2"> <p>您可以从模型中排除的最大特征数为500。 使用文件夹特征最大化排除。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基线特征 </p> </td>
   <td colname="col2"> <p>默认情况下，基线特征被排除，因此在构建模型时，它不会显示在 <b><span class="uicontrol"> Exclusions列表中</span></b> 。 </p> </td>
  </tr>
 </tbody>
</table>

观看以下视频，了解如何以及为何从中排除特定特征 [!UICONTROL Look-Alike Model]。

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 相关链接

* [关于算法特征](/help/using/features/algorithmic-models/understanding-models.md)
* [特征排除——教程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)