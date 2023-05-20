---
description: 「上線狀態報表」會檢查成敗比率，以處理傳入資料來源檔案中的記錄。 此報表以互動式長條圖顯示資料，並以表格形式提供摘要量度。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics >上線狀態報表中找到此報表。 建立入站資料來源時，也可使用此報表。
seo-description: The Onboarding Status Report checks success and failure rates for processing records in your inbound data source files. This report displays data in an interactive bar chart and provides summary metrics in tabular form. And, it includes an option that samples files for a fixed time interval and displays the most common errors for each error type. You can find this report in Analytics > Onboarding Status Report. This report is also available when you create an inbound data source.
seo-title: Onboarding Status Report
solution: Audience Manager
title: 载入状态报表
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
feature: Inbound and Outbound Reports
exl-id: 4517276f-5025-4779-917f-4a0bb22ca56c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1416'
ht-degree: 6%

---

# 载入状态报表{#onboarding-status-report-about}

「上線狀態報表」會檢查成敗比率，以處理傳入資料來源檔案中的記錄。 此報表以互動式長條圖顯示資料，並以表格形式提供摘要量度。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。您可以在Analytics >上線狀態報表中找到此報表。 建立入站資料來源時，也可使用此報表。

>[!NOTE]
>
>只有具有管理員許可權的使用者才能在Audience Manager使用者介面中看到此報告。 您可以將非管理員使用者的電子郵件新增至報表，以通知其已上傳傳入檔案的狀態。 另請參閱 [接收電子郵件通知](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## 上線狀態報表：關於 {#onboarding-status-about}

此 [!UICONTROL Onboarding Status Report] 檢查成敗比率，以處理傳入資料來源檔案中的記錄。 此報表以互動式長條圖顯示資料，並以表格形式提供摘要量度。 它还包括一个选项，允许采集固定时间间隔的文件样本，并显示每种错误类型的最常见错误。此報表位於： **[!UICONTROL Analytics > Onboarding Status Report]**. 建立入站資料來源時，也可使用此報表。

## 錯誤報告和錯誤取樣 {#error-reporting-sampling}

錯誤報告和錯誤取樣是 [!UICONTROL Onboarding Status] 報告。

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 功能 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>錯誤報告</b> </p> </td>
   <td colname="col2"> <p>錯誤報告會顯示傳入資料來源中已處理記錄數的成功和失敗率。 它會以互動式棧疊長條圖傳回資料，並在圖表下方的表格中以摘要量度的形式傳回。 </p> <p>錯誤報告是自動的。 它會持續對您的所有傳入資料來源執行。 它會根據預設時間間隔範圍或您使用行事曆Widget設定的自訂時間間隔傳回資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>錯誤取樣</b> </p> </td>
   <td colname="col2"> <p>錯誤取樣會剖析資料檔案的內容，並傳回每種錯誤型別的10個最常見錯誤。 傳入資料檔案中的錯誤會導致無法處理個別記錄。 使用此報表作為疑難排解工具，以協助減少檔案錯誤數並改善處理率。 </p> <p>您必須手動啟動錯誤取樣。 它會在啟動之日起執行14天，然後自行關閉。 您可以在14天間隔過期後重新開啟錯誤取樣。 您啟動錯誤取樣時 <a href="../features/manage-datasources.md#create-data-source"> 建立傳入資料來源</a> 或透過檢查 <b><span class="uicontrol"> 錯誤取樣</span></b> 核取方塊 <span class="wintitle"> 資料來源設定</span> 現有傳入資料來源的區段。 </p> <p>錯誤取樣是運算量很高的程式。 因此，它只會傳回每個錯誤類別的前10個錯誤。 它並非設計用來傳回傳入資料來源中包含的每個錯誤。 這些錯誤是潛在大量類似錯誤的代表性範例。 檢閱整個檔案，檢視此報表標示的錯誤型別、重新格式化檔案，然後再次傳送。 </p> <p>另請參閱 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 傳入資料檔案內容：語法、變數和範例</a> 瞭解更多有關如何正確格式化傳入資料來源的資料檔案。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤報告橫條圖 {#error-report-bar-chart}

錯誤報表會以棧疊長條圖顯示記錄處理的成功和失敗率，如下列範例所示。 圖表為互動式。 按一下長條圖會在圖表下方的表格中顯示當天的摘要量度。

![](assets/stacked-graph.png)

## 錯誤報告表格 {#error-report-tables}

錯誤報告會在長條圖下方顯示表格資料。 此表格顯示成功和失敗率以及總計和百分比。

**成功和失敗的記錄**

此預設檢視顯示報表中記錄總數的頻率計數，並包含按錯誤型別劃分的錯誤。

![](assets/success-failure.png)

**總計和百分比**

按一下 **[!UICONTROL Totals & Percentages]** 檢視您的檔案中有哪個%已成功處理。

![](assets/totals-percentages.png)

## 14天的錯誤取樣報表 {#error-reporting-14-days}

啟用錯誤取樣後，報表會顯示每個錯誤型別的前10個錯誤。 按一下報表頂端的錯誤型別按鈕，檢視每組抽樣資料。

>[!NOTE]
>
>報告沒有在此目前版本中醒目提示記錄錯誤。 若要尋找並修正檔案錯誤，您應該檢閱結果，並將結果與 [傳入資料檔案內容](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 說明檔案。

![](assets/error-samples.png)

## 接收電子郵件通知 {#receive-email-notifications}

您可以新增收件者的電子郵件地址，以便在已上傳傳入檔案的狀態通知該收件者。 請注意，您可以為不同的資料來源選取不同的收件者。

![](assets/mail-notifications.png)

## 建立上線狀態報表 {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] 傳回資料來源中已成功處理的記錄數目以及失敗數目。 請依照下列步驟產生 [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. 前往 **[!UICONTROL Analytics > Onboarding Status Report]**. 搜尋資料來源或從清單中選擇資料來源。

2. 選取日期範圍。 选项包括：

   * 一組固定的報表間隔。
   * 可讓您建立自訂日期範圍的行事曆Widget。

3. 单击 **[!UICONTROL OK]**.

## 入門狀態報表條款與定義 {#report-terms-conditions}

此報告中使用的標籤和辭彙參考指南。

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 术语 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>資料同步檔案名稱</b> </p> </td> 
   <td colname="col2"> <p>列出符合以下條件的檔案： <span class="keyword"> Audience Manager</span> 已從您選取的傳入資料來源接收及處理。 </p> <p>如果檔案名稱的格式不正確，檔案處理將失敗。 檔案名稱要求依您傳送此資料的方式而異 <span class="keyword"> Audience Manager</span>. 傳遞方法包括 <span class="keyword"> Amazon S3</span> 和FTP。 如需如何為檔案命名的說明，請參閱： </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 入站数据文件的 Amazon S3 名称要求 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>格式錯誤</b> </p> </td> 
   <td colname="col2"> <p>列出由於不符合語法或格式要求而處理失敗的記錄數。 另請參閱 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 傳入資料檔案內容：語法、變數和範例</a> 以取得如何格式化資料的資訊。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>無效的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的數量 <span class="keyword"> Audience Manager</span> 使用者ID (UUID)。 這通常代表ID： </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">不符合預期的38位數格式。 </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">包含字母字元。 ID只能是數字。 </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>無效的裝置識別碼</b> </p> </td> 
   <td colname="col2"> <p>列出格式不正確的全域裝置ID數目。 另請參閱 <a href="../reference/ids-in-aam.md">Audience Manager內的ID索引</a> 和 <a href="../features/global-data-sources.md">全域資料來源</a>  取得裝置ID的格式設定方式，以及您應使用的全域資料來源的詳細資訊（根據裝置型別）。</p>
  <p>報表的錯誤取樣區段包含有關無效裝置ID的詳細資訊，例如：</p>
   <ul>
    <li>與無效裝置ID對應的資料來源ID；</li>
    <li>無效的裝置ID；</li>
    <li>預期的裝置ID型別，根據資料來源而定。</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>沒有相符的AAM ID</b> </p> </td> 
   <td colname="col2"> <p>這些是已上線的ID <span class="keyword"> Audience Manager</span> 無法與現有ID相符。 已上線的ID在以下情況下可以具有此狀態： <span class="keyword"> Audience Manager</span> 尚未執行ID同步，或即使在同步後仍無法與ID相符。 </p> <p>若是行動ID不相符， <span class="keyword"> Audience Manager</span> 將： </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">繼續儲存並嘗試同步此ID。 </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">將其記錄為 <span class="wintitle"> 儲存的記錄</span> 報表中的ID是否無法同步。 </li> 
    </ul> <p>如果您的已上線檔案包含行動ID，那麼您可以比其他量度更輕鬆地處理這些數字。 它們不會影響後續檔案的成功和匹配率。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未實現任何特徵</b> </p> </td> 
   <td colname="col2"> <p>列出符合以下條件的特徵 <span class="keyword"> Audience Manager</span> 無法比對已上線的特徵。 這可能是下列原因所致： </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">傳入資料檔案中的特徵格式不正確。 如需如何格式化資料檔案的相關資訊，請參閱 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 傳入資料檔案內容：語法、變數和範例</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">尚未定義的特徵 <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>成功百分比</b> </p> </td> 
   <td colname="col2"> <p>檔案中已成功儲存的記錄百分比。 成功百分比=處理的記錄/檔案中的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已接收的記錄</b> </p> </td> 
   <td colname="col2"> <p>已接收的記錄總數。 在大多數情況下，此數字應該符合傳入資料檔案中的記錄總數（行）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>儲存的記錄</b> </p> </td> 
   <td colname="col2"> <p>成功儲存的記錄數。 由於檔案格式錯誤，收到的某些記錄可能無法由儲存 <span class="keyword"> Audience Manager</span>. 儲存的記錄數可以少於接收的記錄數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>已實現特徵總數</b> </p> </td> 
   <td colname="col2"> <p>所有傳入檔案中，所有使用者的特徵數，這些檔案會儲存在 <span class="keyword"> Audience Manager</span> 平台。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>未使用的訊號總數</b> </p> </td> 
   <td colname="col2"> <p>報告中收到的未使用訊號總數。 此總計是根據成功儲存的記錄總數。 </p> <p>另請參閱 <a href="../reporting/dynamic-reports/unused-signals.md"> 未使用的訊號報表</a> 以取得詳細資訊。 </p> </td> 
  </tr> 
 </tbody> 
</table>
