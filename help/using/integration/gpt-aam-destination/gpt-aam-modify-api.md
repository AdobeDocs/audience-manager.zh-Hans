---
description: 添加if语句以检查Audience Manager cookies，然后调用Google Publisher标记. setTargeting方法。
seo-description: 添加if语句以检查Audience Manager cookies，然后调用Google Publisher标记. setTargeting方法。
seo-title: 修改GPT Settargeting API调用
solution: Audience Manager
title: 修改GPT Settargeting API调用
uuid: 0cd38f30-5d29-4511-a779-d32587 f1 dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

Add an if statement to check for Audience Manager cookies before calling the [!DNL Google Publisher Tag] `.setTargeting` method.

## Check for Audience Manager Cookies With an `IF` Statement

`.setTargeting` 该方法从Audience Manager目标cookie和唯一用户ID cookie( `aam_uuid`)获取数据。However, if `.setTargeting` gets invoked before [!UICONTROL DIL] writes these cookies, or the cookies are empty, you may see errors when the page loads. To help avoid this, wrap the `.setTargeting` method in an `if` statement that checks for these cookies. If they're not set, this statement prevents `.setTargeting` from calling the `AamGpt` function.

### `IF` 语句代码示例

In this example, the Audience Manager destination cookie name is `Sample`. 在Audience Manager UI中创建目标cookie时，您可以设置此名称。[!UICONTROL DIL] 设置 `aam_uuid` cookie并且不能更改名称。

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
>Depending on how you want to integrate with [!DNL DFP], you only need some of the lines in the code sample above:
>
>* 客户端集成：只使用第1-3条。
>* 服务器端集成：没有任何一行是必需的。
>* Ingest [!DNL DFP] log files for reporting in [!DNL Audience Manager]: use lines 4-6 only. This code inserts the value of the `aam_uuid` cookie into the logs so they can be ingested for reporting.


### `AamGpt` 函数和数据类型

Defines the key variables used in the `if` statement.

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
   <td colname="col1"> <p> <code> AAM PPT. getKey </code> </p> </td> 
   <td colname="col2"> <p>字符串 </p> </td> 
   <td colname="col3"> <p>返回键值区段对中的键。For example, if your key-value pair consisted of <code> color=blue </code>, this returns <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AMAMgt. getValues </code> </p> </td> 
   <td colname="col2"> <p>字符串数组 </p> </td> 
   <td colname="col3"> <p>Returns values in an array, e.g., <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AAM PPT. getCookies </code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Returns the Audience Manager user ID, e.g., <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ This]
>
>* [创建GPT目标](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher标签的Audience Manager代码](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

