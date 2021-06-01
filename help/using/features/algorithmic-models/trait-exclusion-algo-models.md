---
description: 特征排除在建模工作流程中提供了其他控件，允许您根据域专业知识和法规要求向模型添加必要的防护栏。 使用排除项选项选择在从一个或多个数据源创建模型时要忽略的特征。
seo-description: 特征排除在建模工作流程中提供了其他控件，允许您根据域专业知识和法规要求向模型添加必要的防护栏。 使用排除项选项选择在从一个或多个数据源创建模型时要忽略的特征。
seo-title: 算法模型特征排除
title: 算法模型特征排除
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: 算法模型
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# 相似人群拓展建模：特征排除 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 在建模工作流程中提供了其他控件，使您能够根据您的域专业知识和法规要求向模型添加必要的防护栏。使用[!UICONTROL Exclusions]选项选择在从一个或多个数据源创建模型时要忽略的特征。

## 用例 {#use-cases}

以下是可通过[!UICONTROL Trait Exclusion]解决的一些用例：

* [!UICONTROL Trait Exclusion] 可让您排除某些通用特征（如网站访客特征），以便不会偏差模型，从而产生平面结果。
* 您可以从数据源中删除您不知道或不信任的特征，以便更好地了解具有影响力的特征。
* 您可以排除某些特征（如人口统计特征），以帮助履行您可能承担的任何合规义务。

>[!IMPORTANT]
>
>关于第三个用例的重要说明。 如果在创建模型&#x200B;*后，第三方数据提供程序向数据馈送*&#x200B;中添加了新的人口统计特征，则模型会自动选取该特征。 在创建模型后，不能从建模中排除特征。 请参阅[重要方面和限制](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)。 使用此功能时请务必谨慎，并与数据提供商合作，以确保您获悉对信息源结构所做的任何更改。

![](assets/lam_exclude_traits.png)

## 如何使用特征排除{#how-to-use}

使用[构建模型](../../features/algorithmic-models/create-model.md#build-model)工作流构建新的算法模型。

1. 在您选择一个或多个数据源进行建模之前，[!UICONTROL Exclusions]选项将呈灰显状态。
2. 选择一个或多个数据源进行建模后，按&#x200B;**[!UICONTROL Browse All Traits]**。
3. 在&#x200B;**[!UICONTROL Select Traits to Exclude]**&#x200B;窗口中，您可以看到与您之前选择的数据源关联的所有特征。 选择要排除的特征。
4. 您可以按特征类型、特征群体类型（[设备ID](../../reference/ids-in-aam.md)和[跨设备ID](../../reference/ids-in-aam.md)）筛选特征，也可以浏览特征文件夹。 请注意，特征文件夹仅显示与您选择的数据源关联的特征。
5. 按&#x200B;**[!UICONTROL Exclude Selected Traits]**。

![特征排除](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>您可以逐个排除文件夹特征，而不是排除文件夹中的特征，从而排除整个文件夹。 例如，在具有20个特征的文件夹中，您只需排除文件夹特征，而无需逐个排除所有特征。

如果您喜欢使用视频教程，请观看我们的视频演示以了解特征排除：

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

此外，请观看以下视频，详细了解跨设备量度的工作方式。

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## 重要方面和限制{#important-aspects-and-limitations}

请注意与[!UICONTROL Trait Exclusion]相关的以下方面和限制：

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
   <td colname="col2"> <p>排除的特征<i>不会在“模型摘要”视图中显示</i>。 您只能在<b><span class="uicontrol">编辑模型</span></b>工作流中查看排除的特征。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>基于角色的访问控制(RBAC) </p> </td>
   <td colname="col2"> <p>请注意以下对使用<a href="../../features/administration/administration-overview.md#administration"> RBAC</a>的公司的限制： </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">如果您无权查看某个特征，则<i>不能</i>选择要从模型中排除的特征。 </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">如果您无权查看特征，则<i>不能</i>在排除的特征列表中查看该特征。 </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>在保存模型后修改排除的特征 </p> </td>
   <td colname="col2"> <p>创建并保存模型后，便无法修改排除的特征。 如果要调整结果，可以克隆模型并更改排除的特征。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>可排除的特征数上限 </p> </td>
   <td colname="col2"> <p>您可以从模型中排除的最大特征数为500。 使用文件夹特征可最大化排除项。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>排除基线特征 </p> </td>
   <td colname="col2"> <p>默认情况下，基线特征会被排除，因此在构建模型时，该特征不会显示在<b><span class="uicontrol">排除项</span></b>列表中。 </p> </td>
  </tr>
 </tbody>
</table>

请观看以下视频，了解如何从[!UICONTROL Look-Alike Model]中排除特定特征以及为何从中排除特定特征。

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 相关链接

* [关于算法特征](/help/using/features/algorithmic-models/understanding-models.md)
* [特征排除 — 教程](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
