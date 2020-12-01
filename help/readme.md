---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 说明

**注意：本页（或任何readme.md页面）将不会发布到面向客户的文档**

## 目录

+ `TOC.md` 在用户指南的根目录中，可以组织本解决方案指南中包含的主题。
+ 每个用户指南都有其自己的唯一`TOC.md`，您可以根据需要对所有页面／主题进行排序。
+ 所有用户指南的第一页为`overview.md`。

## 用户指南

+ 用户指南的简介称为`overview.md`
+ 用户指南中的每个主题都有其自己的独特目录。
   + 如果指南中有一个主题名为&#x200B;*Implementation*，则相应的目录为`/implementation`
+ 所有图像资源都存储在用户指南的根目录`/assets`中。
   + `/assets`目录中的所有映像都将本地化。
   + `/no-localize`目录中的所有图像都不会本地化（这很令人吃惊！）。 这可用于确保在本地版本中不会不必要地复制特定资产。

## 用户指南级元数据

+ 描述用户指南的元数据存储在`TOC.md`中。 这包括：
   + product —— 产品／功能的名称。
   + 云——此产品所属的云。
   + 受众-指南针对的受众或原型。
   + 用户指南——用户指南的名称。

## 页面级元数据

+ 描述文档所需的元数据作为每个单独页面的一部分进行存储。 这包括：
   + title —— 页面的标题。
   + description —— 页面说明。
   + seo-title - seo替代标题。
   + seo-description —— 用于SEO的替代标题。
   + short-title -（可选字段）。
   + 索引——是／否——页面将按Adobe的搜索平台进行索引。
   + 翻译——是／否——此页面是否将本地化。
   + version —— 主要用于AEM和活动，用于表示产品的版本。
   + private-feature-pack —— 主要用于AEM。
   + beta —— 此产品是beta版本吗？
   + 重定向——可用于根据需要为新页面创建引用。
   + doc-type:参考（默认）/疑难解答／开发人员／教程/ kb /白皮书。

## 更多信息

有关发布说明、风格指南、示例和其他资源的详细信息，请访问[协作文档回购](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
