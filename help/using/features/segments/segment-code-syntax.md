---
description: 通过区段生成器，您可以使用代码编辑器为区段构建特征规则。 单击“特征”面板中的区段表达式（代码视图）选项卡以访问此功能。
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: 区段表达式编辑器中使用的代码语法
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 4%

---

# 区段表达式编辑器中使用的代码语法 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder]允许您使用代码编辑器为区段构建特征规则。 单击&#x200B;**[!UICONTROL Segment Expressions (Code View)]**&#x200B;面板中的[!UICONTROL Traits]选项卡以访问此功能。

## 表达式生成器代码语法

您可以使用代码将特征规则添加到区段，而不是使用拖放功能。 编码时，将示例中的斜体元素替换为实际的表达式或值。 基础代码使用以下语法：

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>默认情况下，[!DNL Boolean] [!UICONTROL OR]条件适用于表达式中&#x200B;*的多个特征*。

### 使用布尔运算符连接区段

要构建区段组，请将频率函数括在括号中，并使用&#x200B;*运算符（*、[!DNL Boolean]和[!UICONTROL AND]）为每个表达式设置[!UICONTROL OR]之间的关系[!UICONTROL NOT]。

### 参数

>[!NOTE]
>
>除非另有说明，否则所有参数都是必需的。

| 名称或变量 | 描述 |
|---|---|
| `FREQUENCY` | 必须在表达式前面的文本。 |
| `[`&lt;`traitID`>`T]` | 特征ID数组，后跟字母`T`。 用逗号分隔多个特征。 例如，`[123T, 456T]`。 |
| `<Recency Operator><Numeric Value>D` | *（可选）*&#x200B;针对区段中的特征设置回访间隔规则。 字母`D`表示回访间隔（天）。 |
| `<Frequency Operator><Numeric Value>` | 设置区段中特征的频率规则。 |

### 允许的回访间隔和频率运算符

使用比较运算符和整数设置[回访间隔和频率](../../features/segments/recency-and-frequency.md)间隔。 [!UICONTROL Segment Builder]使用&lt; （小于）、> （大于）、== （等于）等标准表达式。 但是，当您设置回访间隔或频率时，允许的运算符类型会有所不同。 下表列出了允许的回访间隔/频率运算符。

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 回访间隔运算符 </th> 
   <th colname="col2" class="entry"> 频率运算符 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= （大于/等于） </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= （小于/等于） </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= （大于/等于） </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= （小于/等于） </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==（等于） </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [回访间隔和频度](../../features/segments/recency-and-frequency.md)
>* [特征和区段生成器中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比较运算符](../../features/traits/trait-comparison-operators.md)
>* TraitBuilder表达式中的[运算顺序](../../features/traits/trait-operator-precedence.md)
