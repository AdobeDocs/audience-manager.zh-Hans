---
description: DCS API程式碼、方法和程式的概念資訊、說明和定義。
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: DCS API 参考概述
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 14%

---

# DCS API 参考概述

概念資訊、說明和定義 [!DNL DCS API] 程式碼、方法和程式。

* [DCS API 方法](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   將資料傳送至 [!DNL DCS API] 使用GET或POST方法。

* [DCS 错误代码、消息和示例](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   資料收集伺服器(DCS)產生的錯誤碼和訊息，會依代碼ID以數字順序列出。

* [ID監控與封鎖清單](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS會監控收到的ID，並將短時間內以異常高的頻率傳送的ID新增至拒絕清單。

* [DCS 区域 ID、位置和主机名](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   呼叫DCS需要地區DCS伺服器主機名稱。 這是因為DCS會將資訊儲存在地理位置上接近網站訪客的資料中心。 如果您將查詢傳送至錯誤的DCS，查詢將正常運作，但這些呼叫效率不彰，且可能會延遲回應。 若要提出DCS請求，請將地區ID與其對應的地區主機名稱配對，並使用正確的主機名稱來組成查詢。

* [格式化 DCS 调用中的键值对](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   進行呼叫時，DCS會接受標準或序列化格式的機碼值資料。 如需如何格式化標準及序列化索引鍵值資料的詳細資訊，請參閱本節。

* [争用条件和错误处理](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   說明如何防止競爭條件和DCS錯誤處理。

* [DCS API 调用支持的属性](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   列出並描述您可以傳遞至資料收集伺服器(DCS)的語法和支援的屬性（或機碼值組）。 此資訊可協助您格式化DCS請求，並瞭解此系統傳回的引數。
