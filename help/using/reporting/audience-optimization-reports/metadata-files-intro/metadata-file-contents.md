---
description: 根据这些规范格式化受众优化元数据文件的内容。
seo-description: 根据这些规范格式化受众优化元数据文件的内容。
seo-title: 元数据文件的内容格式
solution: Audience Manager
title: 元数据文件的内容格式
uuid: ba443738-3e17-40c7-9e8c-5ab8361e16d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Content Format for Metadata Files{#content-format-for-metadata-files}

根据这些规范格式化受众优化元数据文件的内容。

## 语法{#syntax}

以下语法定义了元数据文件中结构良好的内容的结构。Note, *italics* indicates a variable placeholder.

**语法：***内容ID* || *name* || *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

The third column **-1** is technically the Parent ID, which is a legacy field. The value should always be set as **-1**.

>[!NOTE]
>
>请注意，每个维度需要一个元数据文件，因此在桶中需要多个元数据文件。The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**将文件条目与^ a分开(control-A或ASCII001)**

Use `^a` (control-A or ASCII 001) to separate content in your metadata files. 由于这些是非打印字符，上面的语法示例显示了一条管道”||“仅用于显示目的。

If needed, you may download the example file - [20181105_0_1](assets/20181105_0_1.zip). 解压缩它并在选择的编辑器中进行编辑，根据您的实际元数据内容进行调整，因为它已经包含所需的分隔符。

>[!IMPORTANT]
>
>请勿向元数据文件添加标题行。

## 示例 {#examples}

让我们来看看如何在元数据文件中构造内容。这一结构的一部分取决于维度。The dimensions are listed in the article [Naming Conventions for Metadata File](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

在此示例中，文件标题为20180921_0_1，文件中的三列为：系列活动ID、名称和父ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

在此示例中，文件标题为20180827_0_2，文件中的三列为：Creative ID、Name和父ID。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site（网站）**

在此示例中，文件标题为20180921_0_5，文件中的三列为：站点ID、名称和父ID。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
