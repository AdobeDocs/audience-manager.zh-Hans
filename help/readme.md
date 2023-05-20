---
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---
# 说明

**注意：此頁面（或任何readme.md頁面）不會發佈至面對客戶的檔案**

## 目錄

+ `TOC.md` 位於使用手冊的根目錄，提供使用手冊中所包含適用於此解決方案的主題組織。
+ 每個使用手冊都有其自己的唯一 `TOC.md`，您可視需要排序所有頁面/主題。
+ 所有使用手冊的第一頁都是 `overview.md`.

## 用户指南

+ 我們將使用手冊的簡介稱為 `overview.md`
+ 使用手冊中的每個主題都有自己的不同目錄。
   + 如果指南中有一個名為的主題 *實作*，對應的目錄為 `/implementation`
+ 所有影像資產都儲存在 `/assets` 位於使用手冊的根目錄。
   + 中的所有影像 `/assets` 目錄將會本地化。
   + 中的任何影像 `/no-localize` 目錄將不會翻譯（令人驚訝！）。 這可用來確保在loc版本中特定資產不會不必要地重現。

## 使用手冊層級中繼資料

+ 說明使用手冊的中繼資料會儲存在 `TOC.md`. 这包括：
   + product — 產品/功能的名稱。
   + cloud — 此產品所屬的雲端。
   + 對象 — 手冊所針對的對象或原型。
   + 使用手冊 — 使用手冊的名稱。

## 頁面層級中繼資料

+ 描述檔案所需的中繼資料會儲存為每個個別頁面的一部分。 这包括：
   + title — 頁面標題。
   + description — 頁面說明。
   + seo-title - seo替代標題。
   + seo-description - SEO用途的替代標題。
   + short-title - （選擇性欄位）。
   + index - yes / no — 頁面是否會由Adobe的搜尋平台建立索引。
   + 翻譯 — 是/否 — 此頁面是否會翻譯。
   + 版本 — 主要用於AEM和Campaign，代表產品的版本。
   + private-feature-pack — 主要用於AEM。
   + beta — 此產品是否為beta版？
   + 重新導向 — 必要時可用於建立新頁面的參照。
   + doc-type：參考（預設） /疑難排解/開發人員/教學課程/ kb /白皮書。

## 更多信息

如需更多發佈指示、風格指南、範例和其他資源，請造訪 [合作檔案存放庫](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
