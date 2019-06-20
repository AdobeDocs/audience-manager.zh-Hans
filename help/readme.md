---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# 说明

**注意：此页面(或任何readme. md页面)不会发布到面向客户的文档**

## 目录

+ `TOC.md` 用户指南的根目录提供了该解决方案指南中包含的主题。
+ Each user guide will have its own unique `TOC.md`, in which you can order all the pages/topics as necessary.
+ The first page of all user guides is `overview.md`.

## 用户指南

+ The introduction to the user guide is called `overview.md`
+ 用户指南中的每个主题都有自己的独特目录。
   + If there is a topic in the guide called *Implementation*, the corresponding directory is `/implementation`
+ All image assets are stored in `/assets` at the root of the user guide.
   + `/assets` 目录中的所有图像都将本地化。
   + `/no-localize` 目录中的任何图像都不会本地化(有一个意外！)。这可用于确保在loc版本中不必要重现特定资产。

## 用户指南级别元数据

+ Meta data which describes the user guide is stored in the `TOC.md`. 这包括：
   + 产品-产品/功能的名称。
   + 云-此产品所属的云。
   + 受众-定位指南的受众或类型。
   + 用户指南-用户指南的名称。

## 页面级别元数据

+ 描述文档所需的元数据作为每个单独页面的一部分存储。这包括：
   + 标题-页面标题。
   + 描述-页面描述。
   + seo-title- seo替换标题。
   + seo-description-用于SEO用途的替换标题。
   + short-title-(可选字段)。
   + 索引-是/否-页面将由Adobe的搜索平台索引。
   + translate- yes/no- this page be localized.
   + 版本(主要用于AEM和Campaign)以表示产品版本。
   + private-feature-pack-主要用于AEM。
   + Beta-此产品是Beta版产品吗？
   + 重定向-可用于为新页面创建引用。
   + doc-type：reference(default)/疑难解答/developer/tutorial/kb/白皮书。

## 更多信息

For more publishing instructions, style guides, samples and other resources, please visit the [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
