---
description: 宣告ID的運作方式、設定程式、程式碼範例和變數。
keywords: id同步
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: 声明的 ID
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 9%

---

# [!UICONTROL Declared IDs] {#declared-ids}

如何 [!UICONTROL declared IDs] 工作、設定程式、程式碼範例和變數。

## [!UICONTROL Declared ID] 目标 {#declared-id-targeting}

與交換及同步使用者ID [!DNL Audience Manager] 來自未使用或接受永久儲存機制的裝置或瀏覽器，例如協力廠商 [!DNL cookies].

## 用途 [!UICONTROL Declared ID] 目標定位 {#declared-id-targeting-purpose}

有些瀏覽器和大部分行動裝置不接受協力廠商 [!DNL cookies]. 這使得保留有關網站訪客的資訊或指派永久ID變得困難。 若要解決此問題， [!DNL Audience Manager] 使用 [!UICONTROL DIL] 讓您傳入 [!UICONTROL declared IDs] 事件呼叫時。 此外， [!UICONTROL declared ID] 可作為通用ID，套用至中所有解決方案的相同使用者。 [!DNL Experience Cloud]. 下表說明ID目標定位/比對程式：

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 过程 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>事件呼叫</b> </td> 
   <td colname="col2"> <p>若要运行，您需要 <span class="wintitle"> 在页面上 DIL </span> 和 <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a> 代码。 <span class="wintitle">DIL </span> 从 Adobe Experience Platform Identity 服务 </span> 提供 <span class="keyword"> 的函数中 <code> setVisitorID </code> 获取 <span class="wintitle"> 声明的 id </span> ，并将其传递到 <span class="keyword"> Audience Manager </span> 。 </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>匹配 ID</b> </td> 
   <td colname="col2"> <p>Audience Manager 尝试在我们的系统中使用相应的 ID 匹配客户端和访客 ID。 如果不存在匹配 ID，Audience Manager 会创建一个新 ID，并将其与客户端和访客 ID 相关联。 </p> <p> <p>注意：如果您的ID對應至多個Audience ManagerID，則會使用最近的對應。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>傳回ID</b> </td> 
   <td colname="col2"> <p>Audience Manager會將其同步的ID寫入使用者端網域或應用程式中的第一方Cookie （或其他可定址儲存空間）。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>後續事件呼叫</b> </td>
   <td colname="col2"> <p>其他事件呼叫會從使用者端的網域讀取Audience ManagerID並將其傳送給Audience Manager。 </p> </td>
  </tr> 
 </tbody>
</table>

若要開始使用，您需要設定 [!DNL Experience Cloud] ID服務與 [!UICONTROL DIL] 橫跨您要用於資料收集的網站頁面。 另請參閱 [DIL建立](../dil/dil-class-overview/dil-create.md#dil-create) 和 [宣告ID變數](../features/declared-ids.md#declared-id-variables).

## 選擇退出呼叫 {#opt-out-calls}

此 [!UICONTROL declared ID] 程式會遵循網站訪客選擇退出的偏好設定 [!DNL Audience Manager] 依您的網站鎖定目標。 時間 [!DNL Audience Manager] 會收到選擇退出請求， [!DNL JSON] 傳回 [!DNL DCS] 包含錯誤代碼171，並出現訊息 `Encountered opt out tag`，而非 [!DNL Audience Manager] 使用者ID。

* [!DNL Audience Manager] 可以傳入 [!UICONTROL declared ID] 同時選擇退出 [!DNL Audience Manager] [!UICONTROL UUID] 在 [!DNL URL].
* 此 [!UICONTROL declared ID] 選擇退出會儲存在 [!UICONTROL Profile Cache Server] ([!UICONTROL PCS])依每個合作夥伴而定。 使用的平台層級沒有選擇退出 [!UICONTROL declared IDs]. 此外， [!DNL Audience Manager] 將使用者從邊緣上的特定區域選擇退出(選擇退出不會超過 [!DNL DCS] 區域)。

另請參閱 [資料隱私權](../overview/data-security-and-privacy/data-privacy.md) 以取得選擇退出資料收集的詳細資訊。

## [!UICONTROL Declared ID] 選擇退出範例 {#opt-out-examples}

您可以建立 [!UICONTROL declared ID] 使用的選擇退出請求 `d_cid` 和 `d_cid_ic` 機碼值組。 虽然旧版参数（如 `d_dpid` 和 `d_dpuuid`）仍然可用，但已考虑将其弃用。请参阅 [CID 取代 DPID 和 DPUUID](../reference/cid.md)。在示例中，*斜体*&#x200B;表示变量占位符。

### [!UICONTROL CID]选择禁用和[!UICONTROL CID_IC]

有关说明和语法，请参阅[已声明 ID 的 URL 变量和语法](../features/declared-ids.md#variables-and-syntax)。

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 选择退出请求所用方式 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供商 ID 和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多個 <code> d_cid </code> 和 <code> d_cid_ic </code> 機碼值組。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 選擇退出，透過 [!UICONTROL DPID]， [!UICONTROL DPUUID]、和 [!UICONTROL UUID] （已棄用）

這些方法仍然有效，但被視為已過時。 此資訊僅供舊版參考之用。 舊版選擇退出包括：

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 退出（已弃用） </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> 在 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>合作夥伴層級選擇退出 </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>系統會儲存合作夥伴層級的選擇退出，以便對此進行最新對應 <code> dpid </code> + <code> dpuuid </code> 配對至AAM UUID。 如果沒有先前存在的對應，Audience Manager會檢查要求是否在Cookie中包含AAM UUID，如果包含，會使用該UUID儲存選擇退出。 否則，Audience Manager會產生新的AAM UUID並在其下儲存選擇退出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> 和明確 <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> 始终优先。 <code> dpid </code>如果 + <code> dpuuid </code> 组合映射到其他 AAM uuid，则选择禁用会存储在请求（ <code> d_uuid </code> ）中传递的 AAM UUID 下。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 的变量和语法 [!UICONTROL Declared IDs] {#variables-and-syntax}

下表列出了在数据提供程序 ID 中 [!DNL Audience Manager] 传递的键值对，以及用户 id 或集成代码（如果使用）。 注意， *斜体* 表示变量占位符。 添加了空格以使其更易于阅读。

在每个键值对中：

* 此 `=` 符號會將金鑰與其相關值分開。
* 非列印 [!DNL ASCII] 字元 `%01` 分隔值。

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>包含一个键-值对中的数据提供程序 ID 和关联的唯一用户 ID。 <code> d_cid </code> 取代 <code> d_dpid </code> 和 <code> d_dpuuid </code>，這已被取代，但仍受支援。 请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>在單一索引鍵值配對中包含整合代碼和關聯的不重複使用者ID。 <code> d_cid_ic </code> 取代 <code> d_dpid </code> 和 <code> d_dpuuid </code>，已過時，但仍受支援。 请参阅 <a href="../reference/cid.md">CID 取代 DPID 和 DPUUID</a>。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 範例事件呼叫 {#sample-event-calls}

根據這些機碼值組及其必要的語法，您可以進行事件呼叫，如下所示。

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件呼叫包括 </th> 
   <th colname="col2" class="entry"> 代码示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>数据提供商 ID 和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>集成代码和用户 ID。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>多個 <code> d_cid </code> 和 <code> d_cid_ic </code> 機碼值組。 </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] 变量 {#declared-id-variables}

描述用于传递 [!UICONTROL declared IDs] [!UICONTROL DIL] 到的配置变量 [!DNL Audience Manager.]

## [!UICONTROL DIL][!DNL Adobe Experience Platform Identity Service]使用来传递[!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

与 [ Adobe Experience Platform Identity 服务 ](https://experienceleague.adobe.com/docs/id-service/using/home.html) 一起使用时，您不再需要与已弃用 `dpid` 的和 `dpuuid` 变量一起传递 [!UICONTROL declared IDs] 。而是依赖于函数的当前版本 [!UICONTROL DIL] 从 `setCustomerIDs` 获取 [!UICONTROL declared IDs] 函数 [!UICONTROL Adobe Experience Platform Identity Service] 。 `visitorService`有关详细信息，请参阅 [ 客户 id 和 Authentication 状态 ](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html) 。 您可以按如下所示进行调用 `visitorService` `DIL.create` 。

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

`namespace`在键值对中， `MCORG` 是您 [!DNL Experience Cloud] 的组织 ID。如果您没有此 ID，则可以在 [!UICONTROL Administration] 功能板的部分 [!DNL Experience Cloud] 找到它。 您需要管理員許可權才能檢視此儀表板。 另請參閱 [管理：核心服務](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html).

## 已棄用的函式 {#deprecated-functions}

使用最新版本的 [!UICONTROL DIL] (6.2+)，您不需要使用這些機碼值組來傳入 [!UICONTROL declared IDs]. 這是因為 [!UICONTROL DIL] 現在仰賴 `visitorService` 函式如上述程式碼範例所示。 此函式取得 [!UICONTROL declared IDs] 從 [!UICONTROL Adobe Experience Platform Identity Service]. 不過，我們在此參考這些變數，是為了歷史記錄和舊版用途。 请参阅下面的代码，以了解有关如何配置 `DIL.create` 以从 [!UICONTROL Visitor ID Service] 进行获取 [!UICONTROL declared ID] 的示例。下表說明使用的舊版變數 `declaredId` 物件：

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名称 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>由Audience Manager指派的資料合作夥伴ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> 字符串 </td> 
   <td colname="col3"> <p>用户的唯一数据提供程序 ID。 </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] 和 [!UICONTROL DPUUID]

[!DNL Audience Manager] 比較並比對已合併的 `DPID` 和 `DPUUID` 至我們系統中的對應使用者ID。 如果ID不存在， [!DNL Audience Manager] 建立新的使用者ID並將其同步至 `DPID/DPUUID` 組合。 一次 [!DNL Audience Manager] 比對或建立使用者ID (此類 `UUID`)它會傳回 [!DNL JSON] 對的回應 [!DNL cookie] 在使用者端的網域中（第一方） [!DNL cookie])或其他本機儲存空間。

使用時呼叫此函式 [!UICONTROL DIL] v6.1或更早版本。 但是，此函数已被弃用，取而代之的是从 [!DNL Adobe Experience Platform Identity Service] 获取 [!UICONTROL declared IDs] 的新版本。

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>您需要以程式設計方式開發代碼，為以下專案提供ID值： `d_dpuuid` 和 `d_dpid` 金鑰。

### 在以下時間後傳遞ID： [!UICONTROL DIL] 具現化

>[!NOTE]
>
>如果您建立 [!DNL API] 使用不同的呼叫 `declaredID` 組合，則新組合將僅用於該呼叫。 其他定期事件呼叫將使用原始的 `DIL.create`  `declaredID` 組合。

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## 請求/回應範例 {#request-response-examples}

該請求會將資料提供者和使用者ID傳送至 [!DNL Audience Manager]：

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

回應會傳回Audience ManagerID (例如 `UUID`)，會寫入頁面網域中的第一方Cookie。

```js
myCallback({
...
   "uuid":"abc123"
})
```

## 不要鎖定和選擇退出呼叫 {#do-not-target}

此 [!UICONTROL declared ID] 程式會遵循網站訪客選擇退出的偏好設定 [!DNL Audience Manager] 依您的網站鎖定目標。 時間 [!DNL Audience Manager] 會收到選擇退出請求， [!DNL DCS] 傳回空白 [!DNL JSON] 物件而非 [!DNL Audience Manager] 使用者ID。

>[!MORELIKETHIS]
>
>* [CID 取代 DPID 和 DPUUID](../reference/cid.md)

