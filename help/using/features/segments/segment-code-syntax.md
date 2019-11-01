---
description: 使用Segment Builder，您可以使用代码编辑器为区段构建特征规则。 单击“特征”面板中的“段表达式”（“代码视图”）选项卡以访问此功能。
seo-description: 使用Segment Builder，您可以使用代码编辑器为区段构建特征规则。 单击“特征”面板中的“段表达式”（“代码视图”）选项卡以访问此功能。
seo-title: 段表达式编辑器中使用的代码语法
solution: Audience Manager
title: 段表达式编辑器中使用的代码语法
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 段表达式编辑器中使用的代码语法 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 允许您使用代码编辑器为区段构建特征规则。 单击面 **[!UICONTROL Segment Expressions (Code View)]** 板中的选 [!UICONTROL Traits] 项卡以访问此功能。

## 表达式构建器代码语法

您可以使用代码将特征规则添加到区段，而不是使用拖放功能。 在编码时，将示例中的斜体元素替换为实际的表达式或值。 基本代码使用以下语法：

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>默认情况下， [!DNL Boolean] 条件适用 [!UICONTROL OR] 于表达式中 *的多个* 特征。

### 使用Boolean运算符连接区段

要构建段组，请将频率函数括在圆括号中，并使用运算符( *、* 和)设置每个 [!DNL Boolean] 表达式之间的关[!UICONTROL AND]系 [!UICONTROL OR][!UICONTROL NOT]。

### 参数

>[!NOTE]
>
>除非另有说明，否则所有参数都是必需的。

| 名称或变量 | 描述 |
|---|---|
| `FREQUENCY` | 必须位于表达式之前的文本。 |
| ` [`&lt;`traitID`&gt;`T]` | 一组特征ID，后跟字母 `T`。 用逗号分隔多个特征。 For example, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *（可选）* ，设置区段中特征的近期规则。 信以天 `D` 为单位表示最近的情况。 |
| ` <Frequency Operator><Numeric Value>` | 设置区段中特征的频率规则。 |

### 允许的最近和频率操作符

使用 [比较运算符和整数](../../features/segments/recency-and-frequency.md) ，设置最近和频率间隔。 [!UICONTROL Segment Builder] 使用标准表达式，如&lt;（小于）、&gt;（大于）、==（等于）等。 但是，当您设置最近或频率时，允许的运算符类型会有所不同。 下表列出了允许的最近频率／频率运算符。

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 最近操作符 </th> 
   <th colname="col2" class="entry"> 频率操作符 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=(greater than/equal to) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;=(less than/equal to) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=(greater than/equal to) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;=(less than/equal to) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==（等于） </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [近况和频率](../../features/segments/recency-and-frequency.md)
>* [Trait和Segment Builder中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [在TraitBuilder中使用比较运算符](../../features/traits/trait-comparison-operators.md)
>* [TraitBuilder表达式中的操作顺序](../../features/traits/trait-operator-precedence.md)

