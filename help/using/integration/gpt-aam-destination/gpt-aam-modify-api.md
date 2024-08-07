---
description: 在调用Google Publisher Tag .setTargeting方法之前，添加if语句以检查Audience ManagerCookie。
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: 修改GPT setTargeting API调用
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# 修改GPT `setTargeting` API调用 {#modify-the-gpt-settargeting-api-call}

在调用[!DNL Google Publisher Tag] `.setTargeting`方法之前添加if语句以检查Audience ManagerCookie。

## 使用`IF`语句检查Audience ManagerCookie

`.setTargeting`方法从Audience Manager目标Cookie和唯一用户ID Cookie ( `aam_uuid`)获取数据。 但是，如果在[!UICONTROL DIL]写入这些Cookie之前调用了`.setTargeting`，或者Cookie为空，则您可能会在页面加载时看到错误。 为避免出现这种情况，请将`.setTargeting`方法包装在检查这些Cookie的`if`语句中。 如果未设置这些参数，此语句将阻止`.setTargeting`调用`AamGpt`函数。

### `IF`语句代码示例

在此示例中，Audience Manager目标Cookie名称为`Sample`。 在Audience Manager用户界面中创建目标Cookie时设置此名称。 [!UICONTROL DIL]设置`aam_uuid` Cookie，且名称无法更改。

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>根据您希望如何与[!DNL Google Ad Manager]集成，您只需要上述代码示例中的某些行：
>
>* 客户端集成：仅使用第1-3行。
>* 服务器端集成：无需任何线路。
>* 摄取[!DNL Google Ad Manager]日志文件以在[!DNL Audience Manager]中报告：仅使用第4-6行。 此代码会将`aam_uuid` Cookie的值插入日志，以便将其摄取用于报表。

### `AamGpt`函数和数据类型

定义`if`语句中使用的键变量。

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 函数 </th> 
   <th colname="col2" class="entry"> 类型 </th> 
   <th colname="col3" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>返回键值区段对中的键。 例如，如果您的键值对由<code> color=blue </code>组成，则返回<code> color </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>字符串数组 </p> </td> 
   <td colname="col3"> <p>返回数组中的值，如<code> ["value1","value2"] </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>整数 </p> </td> 
   <td colname="col3"> <p>返回Audience Manager的用户ID，例如<code> 12345 </code>。 </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [创建 GPT 目标](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher Tag 的 Audience Manager 代码](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
