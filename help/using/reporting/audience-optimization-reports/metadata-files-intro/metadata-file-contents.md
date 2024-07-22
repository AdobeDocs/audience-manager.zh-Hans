---
description: 根据这些规范设置Audience Optimization元数据文件内容的格式。
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: 元数据文件的内容格式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# 元数据文件的内容格式{#content-format-for-metadata-files}

根据这些规范设置Audience Optimization元数据文件内容的格式。

## 语法 {#syntax}

以下语法定义元数据文件中格式正确的内容的结构。 请注意，*斜体*&#x200B;表示变量占位符。

**语法：** *内容ID* | *名称* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

从技术上讲，第三列&#x200B;**-1**&#x200B;是父ID，它是旧版字段。 该值应始终设置为&#x200B;**-1**。

>[!NOTE]
>
>请注意，每个维度需要一个元数据文件，因此存储段中需要多个元数据文件。 维度在[元数据文件的命名约定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)一文中列出。

**使用^a （control-A或ASCII 001）分隔文件条目**

使用`^a` （control-A或ASCII 001）分隔元数据文件中的内容。 由于它们是非打印字符，因此上述语法示例显示仅用于显示的竖线“|”。

如果需要，您可以下载示例文件 — [20181105_0_1](assets/20181105_0_1.zip)。 解压该元数据，然后在您选择的编辑器中编辑，并根据实际的元数据内容进行调整，因为该元数据已包含所需的分隔符。

>[!IMPORTANT]
>
>请勿将标题行添加到元数据文件。

## 示例 {#examples}

让我们看一下如何在元数据文件中构建内容。 此结构的一部分取决于尺寸。 维度在[元数据文件的命名约定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)一文中列出。

**Campaign**

在此示例中，文件标题为20180921_0_1，文件中的三列为：促销活动ID、名称和父级ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**创意**

在此示例中，文件标题为20180827_0_2，文件中的三列为：创作ID、名称和父ID。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**站点**

在此示例中，文件标题为20180921_0_5，文件中的三列为：站点ID、名称和父ID。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
