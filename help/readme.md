---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 说明

**注意：此页面（或任何readme.md页面）不会发布到面向客户的文档**

## 目录

+ `TOC.md` 位于用户指南根目录的提供了此解决方案指南中包含的主题的组织。
+ 每个用户指南都有其自己的唯一`TOC.md`，您可以在其中根据需要对所有页面/主题进行排序。
+ 所有用户指南的第一页为`overview.md`。

## 用户指南

+ 用户指南的简介称为`overview.md`
+ 用户指南中的每个主题都有其自己的不同目录。
   + 如果指南中有一个名为&#x200B;*Implementation*&#x200B;的主题，则相应的目录为`/implementation`
+ 所有图像资产都存储在用户指南根目录的`/assets`中。
   + `/assets`目录中的所有图像都将进行本地化。
   + `/no-localize`目录中的任何图像都不会进行本地化（很吃惊吧！）。 这可用于确保在本地化版本中不会复制不必要的特定资产。

## 用户指南级别元数据

+ 描述用户指南的元数据存储在`TOC.md`中。 这包括：
   + product — 产品/功能的名称。
   + cloud — 此产品所属的云。
   + audience — 指南所针对的受众或原型。
   + user-guide — 用户指南的名称。

## 页面级别元数据

+ 描述文档所需的元数据将作为每个单独页面的一部分存储。 这包括：
   + title — 页面的标题。
   + description — 页面描述。
   + seo-title - seo替代标题。
   + seo-description — 用于SEO的替代标题。
   + short-title — （可选字段）。
   + index - yes / no — 该页面是否会被Adobe的搜索平台编入索引。
   + translate - yes / no — 此页面是否会进行本地化。
   + version — 主要用于AEM和Campaign，用于表示产品的版本。
   + private-feature-pack — 主要用于AEM。
   + 测试版 — 此产品是否为测试版？
   + 重定向 — 如果需要，可用于为新页面创建引用。
   + doc类型：参考（默认）/疑难解答/开发人员/教程/知识库/白皮书。

## 更多信息

有关更多发布说明、风格指南、示例和其他资源，请访问[协作文档存储库](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
