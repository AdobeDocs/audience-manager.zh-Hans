---
description: 說明如何防止競爭條件和DCS錯誤處理。
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: 争用条件和错误处理
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# 競爭條件、速率限制和錯誤處理 {#race-conditions-and-error-handling}

說明如何防止競爭條件和 [!DNL DCS] 錯誤處理。

## 防止競爭條件 {#prevent-race-conditions}

如果您同時（或快速接續）傳送多個呼叫至 [!DNL DCS] 完成回應初始查詢及將資料寫入使用者Cookie之前。 競爭條件是不可取的，因為它可能會損毀或不適當地覆寫Cookie資料。 最佳實務是考慮下列方法來協助避免此問題：

* 請勿同時呼叫，或連續快速呼叫 [!DNL DCS] 來自同一使用者。
* 等候每個回應返回，再進行後續呼叫。

## 速率限制 {#rate-limiting}

如果Adobe偵測到過多的DCS API呼叫可能對服務可用性造成負面影響，則可能會引入速率限制。

如果啟用速率限制，您可能會收到 `429 Too Many Requests` DCS呼叫上的HTTP回應狀態碼。 收到此HTTP回應時，請稍後重試API呼叫。

## 錯誤處理 {#error-handling}

無效或格式錯誤的查詢的錯誤處理受到限制。 無效的請求傳回 `HTTP 200 OK` 回應且無資料。 此外， [!DNL DCS] 停止處理請求、捨棄特徵資料，並傳回 `HTTP 200 OK` 當使用者發生以下情況時回應：

* 在Audience Manager或合作夥伴層級選擇退出追蹤。
* 來自無效/未選取的地理區域。
* 停用瀏覽器Cookie （所有或第三方）。

另請參閱 [DCS錯誤代碼、訊息和範例](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
