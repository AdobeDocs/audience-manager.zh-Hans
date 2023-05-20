---
description: 根據這些規格將Audience Optimization中繼資料檔案的內容格式化。
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: 元数据文件的内容格式
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# 元数据文件的内容格式{#content-format-for-metadata-files}

根據這些規格將Audience Optimization中繼資料檔案的內容格式化。

## 语法 {#syntax}

下列語法定義中繼資料檔案中格式正確的內容的結構。 注意， *斜體* 表示變數預留位置。

**語法：**  *內容ID* | *名稱* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

第三欄 **-1** 技術上來說，是父系ID，亦即舊版欄位。 值一律應設為 **-1**.

>[!NOTE]
>
>請注意，每個維度需要一個中繼資料檔案，因此貯體中應該有多個中繼資料檔案。 維度會列在文章中 [中繼資料檔案的命名慣例](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**以^a （control-A或ASCII 001）分隔檔案專案**

使用 `^a` （control-A或ASCII 001）以分隔中繼資料檔案中的內容。 由於這些字元為非列印字元，上述語法範例顯示僅供顯示之用的垂直號「|」。

如有需要，您可以下載範例檔案 —  [20181105_0_1](assets/20181105_0_1.zip). 解壓縮並在您選擇的編輯器中編輯，並根據您的實際中繼資料內容進行調整，因為它已包含必要的分隔字元。

>[!IMPORTANT]
>
>請勿在中繼資料檔案中新增標頭列。

## 示例 {#examples}

讓我們來看看您如何在中繼資料檔案中建構內容。 此結構的一部分取決於尺寸。 維度會列在文章中 [中繼資料檔案的命名慣例](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

在此範例中，檔案標題為20180921_0_1，而檔案中的三欄為：促銷活動ID、名稱和父項ID。

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

在此範例中，檔案標題為20180827_0_2，檔案中的三欄為：創作ID、名稱和父項ID。

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site（网站）**

在此範例中，檔案標題為20180921_0_5，檔案中的三欄為：場地ID、名稱和父項ID。

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
