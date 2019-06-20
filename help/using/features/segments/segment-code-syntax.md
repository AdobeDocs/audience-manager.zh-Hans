---
description: 区段生成器允许您使用代码编辑器为区段构建特征规则。单击“特征”面板中的“区段表达式”(代码视图)选项卡以访问此功能。
seo-description: 区段生成器允许您使用代码编辑器为区段构建特征规则。单击“特征”面板中的“区段表达式”(代码视图)选项卡以访问此功能。
seo-title: 区段表达式编辑器中使用的代码语法
solution: Audience Manager
title: 区段表达式编辑器中使用的代码语法
uuid: 7b4b06ca-7879-4501-8ba7-b2 b6467 b8 a3 b
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Code Syntax Used in the Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 允许您使用代码编辑器为区段构建特征规则。Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## 表达式生成器代码语法

您可以使用代码向区段添加特征规则，而不是使用拖放功能。在编码时，用实际表达式或值替换示例中的斜体元素。基本代码使用以下语法：

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>By default, [!DNL Boolean] [!UICONTROL OR] conditions apply to multiple traits *within* an expression.

### 与布尔操作符连接区段

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### 参数

>[!NOTE]
>
>除非另有说明，否则所有参数都是必需的。

| 名称或变量 | 描述 |
|---|---|
| `FREQUENCY` | 必须在表达式前面的文本。 |
| ` [`&lt;`traitID`&gt;`T]` | An array of trait IDs followed by the letter `T`. 用逗号分隔多个特征。`[123T, 456T]`例如， |
| ` <Recency Operator><Numeric Value>D` | *(可选)* 设置区段中特征的新近度规则。The letter `D` indicates recency in days. |
| ` <Frequency Operator><Numeric Value>` | 设置区段中特征的频率规则。 |

### 允许的新近度和频率运算符

Set [recency and frequency](../../features/segments/recency-and-frequency.md) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] 使用标准表达式(小于(小于)、&gt;(大于)、==(相等)等)。但是，在设置最近的缩进或频率时，允许的操作符类型会有所不同。下表列出允许的新近度/频率运算符。

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 近期运算符 </th> 
   <th colname="col2" class="entry"> 频率操作符 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=(大于/等于) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;=(小于/等于) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=(大于/等于) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;=(小于/等于) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==(等于) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ This]
>
>* [新近度和频率](../../features/segments/recency-and-frequency.md)
>* [特征和区段生成器中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [在TritBuilder中与比较运算符协作](../../features/traits/trait-comparison-operators.md)
>* [TritBuilder表达式中的操作顺序](../../features/traits/trait-operator-precedence.md)

