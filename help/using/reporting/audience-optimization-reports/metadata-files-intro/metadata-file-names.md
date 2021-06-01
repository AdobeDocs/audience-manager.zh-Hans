---
description: 根据这些规范命名您的Audience Optimization元数据文件。
seo-description: 根据这些规范命名您的Audience Optimization元数据文件。
seo-title: 元数据文件的命名约定
solution: Audience Manager
title: 元数据文件的命名约定
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: 日志文件
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 11%

---

# 元数据文件的命名约定{#naming-conventions-for-metadata-files}

根据这些规范命名您的Audience Optimization元数据文件。

## 语法和ID类别 {#syntax}

以下语法定义格式正确的元数据文件名的结构。 请注意， *斜体*&#x200B;表示变量占位符。 其他元素是常量，不会更改。

**语法：***`yyyymmdd_0_childID`*

>[!NOTE]
>
>*请* 勿在元数据文件（.txt或其他）中使用文件扩展名。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 从技术上讲，中间组件&#x200B;**0**&#x200B;是父ID，它是旧版字段。 该值应始终设置为&#x200B;**0**。
* 子ID的值可以介于1到10之间，具体取决于维度。 请参阅以下代码：

## 子ID维度{#child-dimension}

在元数据文件名中，子ID是一个标识符，用于对文件中的数据类型进行分类，并将其置于层次结构中。 您可以使用以下类别ID在文件名中标记子ID:

1. 促销活动
1. 创意
1. 版面
1. Exchange
1. Site（网站）
1. 广告商（如果在[数据源](../../../features/manage-datasources.md#details)中使用集成代码）
1. 插入顺序(IO)
1. 垂直（即特定行业或业务类别，如“计算机”、“汽车”、“房地产”等）
1. 战术
1. 业务单位或品牌

## 示例 {#example}

对于创作元数据文件，文件名可以为20190115_0_2。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
