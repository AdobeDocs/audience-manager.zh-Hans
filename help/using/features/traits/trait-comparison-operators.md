---
description: 本文說明Trait Builder所使用的比較運運算元。
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: 在特征生成器中使用比较运算符
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 10%

---

# 在特征生成器中使用比较运算符 {#working-with-comparison-operators-in-trait-builder}

本文說明使用的比較運運算元 [!UICONTROL Trait Builder].

## 比較運運算元的用途

<!-- c_tb_comparison_operators.xml -->

比較運運算元（或關聯運運算元）可用來比較、測試或評估不同值之間的關係。 在 [!UICONTROL Trait Builder]，在建立訊號規則時，比較運運算元可讓您測試不同索引鍵/值組之間的關係。 例如，您可以建立訊號規則，為昂貴的相機購物者定義對象。 在此情況下，您可以建立相機/價格索引鍵值配對，並讓使用者在尋找價格等於或大於設定金額的相機時符合資格。

## 比較運運算元的優點

當您需要根據多個值評估及建立特徵時，比較運運算元會很有用。 檢視商品和服務價格可以說明這種情況。 例如，您的企業可能想要根據訪客所檢視產品的價格來識別訪客。 然而，根據特定值定義個別區段在管理上可能缺乏效率。 比較運運算元會根據價格臨界值或範圍來建立細分觸發程式，有助於克服此障礙。

## 比較運運算元

您可以使用以下比較運運算元來建置規則：

| 操作员 | 定义 |
|---|---|
| **==** | 等於 |
| **!=** | 不等於 |
| **>** | 大于 |
| **&lt;** | 小于 |
| **=>** | 大於/等於 |
| **&lt;=** | 小於/等於 |

## 已命名的運運算元

您可以使用以下具名運運算元建立規則：

| 操作员 | 評估至 [!DNL True] 時間 |
|---|---|
| **[!UICONTROL Contains]** | 機碼值組中的值 *包含* 此運運算元指定的字元。 |
| **[!UICONTROL Matcheswords]** | 機碼值組中的值 *符合* 此運運算元指定的模式。 |
| **[!UICONTROL Startswith]** | 機碼值組中的值 *開頭為* 此運運算元指定的字元。 |
| **[!UICONTROL Endswith]** | 機碼值組中的值 *結尾為* 此運運算元指定的字元。 |
| **[!UICONTROL Matchesregex]** | 機碼值組中的值 *符合* 規則運算式指定的模式。 [瞭解更多](../../features/traits/trait-builder-regex.md) 關於使用規則運算式 [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [特征和区段生成器中的布尔表达式](../../reference/boolean-expressions-tsb.md)
>* [瞭解TraitBuilder中的布林運算式](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder運算式中的作業順序](../../features/traits/trait-operator-precedence.md)
>* [含布尔和比较运算符的示例表达式](../../features/traits/trait-expression-samples.md)

