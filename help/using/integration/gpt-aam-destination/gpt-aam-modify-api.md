---
description: 在调用Google Publisher标记。setTargeting方法之前，添加if语句以检查Audience Manager Cookie。
seo-description: 在调用Google Publisher标记。setTargeting方法之前，添加if语句以检查Audience Manager Cookie。
seo-title: 修改GPT setTargeting API调用
solution: Audience Manager
title: 修改GPT setTargeting API调用
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 修改GPT `setTargeting` API调用 {#modify-the-gpt-settargeting-api-call}

在调用方法之前，添加if语句以检查Audience Manager [!DNL Google Publisher Tag]`.setTargeting` cookies。

## 通过语句检查Audience Manager Cookies `IF`

该方 `.setTargeting` 法从Audience manager目标cookie和唯一用户ID cookie()中获取数 `aam_uuid`据。 但是，如果 `.setTargeting` 在写入这些Cookie之 [!UICONTROL DIL] 前被调用，或Cookie为空，则页面加载时可能会看到错误。 为避免这种情况，请将该方 `.setTargeting` 法包含在检查 `if` 这些Cookie的语句中。 如果未设置，则此语句将阻止 `.setTargeting` 调用函 `AamGpt` 数。

### `IF` 语句代码示例

在此示例中，Audience manager目标cookie名称为 `Sample`。 在Audience Manager UI中创建目标cookie时，可以设置此名称。 [!UICONTROL DIL] 设置 `aam_uuid` cookie，并且名称无法更改。

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
>根据要与集成的方式， [!DNL DFP]您只需要上面代码示例中的一些行：
>
>* 客户端集成：仅使用第1-3行。
>* 服务器端集成：无需任何一行。
>* 在以 [!DNL DFP] 下位置收录要报告的日志文件 [!DNL Audience Manager]:仅使用第4-6行。 此代码将cookie的值插入 `aam_uuid` 日志中，以便可以摄取它们以进行报告。


### `AamGpt` 函数和数据类型

定义语句中使用的关键 `if` 变量。

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
   <td colname="col3"> <p>返回键值段对中的键。 例如，如果键值对由组成，则 <code> color=blue </code>返回此值 <code> color </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>字符串数组 </p> </td> 
   <td colname="col3"> <p>返回数组中的值，例如 <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>返回Audience Manager用户ID，例如， <code> 12345 </code> </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [创建GPT目标](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher标记的Audience Manager代码](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

