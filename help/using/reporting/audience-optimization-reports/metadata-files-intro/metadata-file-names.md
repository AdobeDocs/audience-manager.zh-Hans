---
description: 根据这些规范为Audience Optimization元数据文件命名。
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: 元数据文件的命名约定
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 3%

---

# 元数据文件的命名约定{#naming-conventions-for-metadata-files}

根据这些规范为Audience Optimization元数据文件命名。

## 语法和ID类别 {#syntax}

以下语法定义了格式正确的元数据文件名的结构。 请注意，*斜体*&#x200B;表示变量占位符。 其他元素为常量，不会更改。

**语法：** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*不*&#x200B;在元数据文件（.txt或其他）中使用文件扩展名。

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 中间组件&#x200B;**0**&#x200B;从技术上讲是父ID，它是旧版字段。 该值应始终设置为&#x200B;**0**。
* 根据维度，子ID的值可以介于1和10之间。 请参阅以下代码：

## 子ID维度 {#child-dimension}

在元数据文件名中，子ID是一个标识符，用于对文件中的数据类型进行分类并将其放入层次结构中。 您可以使用以下类别ID在文件名中标记子ID：

1. 促销活动
1. Creative
1. 投放位置
1. Exchange
1. Site（网站）
1. 广告商（如果在[数据源](../../../features/manage-datasources.md#details)中使用集成代码）
1. 插入顺序(IO)
1. 垂直（即，特定行业或业务类别，如“计算机”、“汽车”、“房地产”等）
1. 策略
1. 业务单位或品牌

## 示例 {#example}

对于Creative元数据文件，文件名可以是20190115_0_2。

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
