---
description: 根据这些规范设置Audience Optimization元数据文件内容的格式。
seo-description: 根据这些规范设置Audience Optimization元数据文件内容的格式。
seo-title: 元数据文件的内容格式
solution: Audience Manager
title: 元数据文件的内容格式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: 日志文件
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 6%

---

# 元数据文件的内容格式{#content-format-for-metadata-files}

根据这些规范设置Audience Optimization元数据文件内容的格式。

## 语法{#syntax}

以下语法定义元数据文件中格式良好的内容的结构。 注意，*斜体*&#x200B;表示变量占位符。

**语法：**  *内容* ID *|名* 称 *| -1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

第三列&#x200B;**-1**&#x200B;在技术上是父ID，它是旧字段。 该值应始终设置为&#x200B;**-1**。

>[!NOTE]
>
>请注意，每个维度需要一个元数据文件，因此存储桶中需要多个元数据文件。 维列在文章[元数据文件的命名约定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)中。

**用^a（control-A或ASCII 001）分隔文件条目**

使用`^a`（control-A或ASCII 001）将元数据文件中的内容分开。 由于这些字符是非打印字符，上面的语法示例仅显示管道“|”。

如果需要，您可以下载示例文件 — [20181105_0_1](assets/20181105_0_1.zip)。 解压缩它，在所选编辑器中编辑，并根据实际元数据内容进行调整，因为它已包含所需的分隔符。

>[!IMPORTANT]
>
>请勿向元数据文件添加标题行。

## 示例 {#examples}

让我们看一下如何在元数据文件中构建内容。 此结构的一部分取决于尺寸。 维列在文章[元数据文件的命名约定](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension)中。

**Campaign**

在此示例中，文件标题为20180921_0_1，文件中的三列为：活动ID、名称和父ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**创意**

在此示例中，文件标题为20180827_0_2，文件中的三列为：创意ID、名称和父ID。

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
