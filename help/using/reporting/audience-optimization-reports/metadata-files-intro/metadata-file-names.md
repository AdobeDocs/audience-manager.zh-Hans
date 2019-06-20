---
description: 根据这些规范命名受众优化元数据文件。
seo-description: 根据这些规范命名受众优化元数据文件。
seo-title: 元数据文件的命名约定
solution: Audience Manager
title: 元数据文件的命名约定
uuid: cab55b2a-2e54-45f6-aea-3735b911 f821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

根据这些规范命名受众优化元数据文件。

## Syntax and ID Categories {#syntax}

以下语法定义了结构良好的元数据文件名的结构。Note, *italics* indicates a variable placeholder. 其他元素是常量，不会更改。

**语法：***`yyyymmdd_0_childID`*

>[!NOTE]
>
>*请勿* 在元数据文件(.txt或其他)中使用文件扩展名。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* 子ID可有一个介于和10之间的值，具体取决于维度。请参阅以下代码：

## Child ID dimensions {#child-dimension}

在元数据文件名中，子ID是一个标识符，用于分类文件中的数据类型并将其放置到层次结构中。您可以用以下类别ID标记文件名中的子ID：

1. 促销活动
1. Creative
1. 版面
1. Exchange
1. Site（网站）
1. Advertiser (if using integration codes in a [data source](../../../features/manage-datasources.md#details))
1. 插入顺序(IO)
1. 垂直(即，诸如“计算机”、“汽车”、“房地产”等特定行业或业务类别)
1. Tactic
1. 业务单位或品牌

## 示例 {#example}

对于Creative元数据文件，文件名可以是20190115_0_2。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
