---
description: 在特征生成器中，通过表达式生成器，您可以创建和测试规则以确立受众资格要求。 规则由键值对组成，如“color == blue”或“price &gt;100”。 比较运算符可建立键和值之间的关系。 布尔表达式可确定规则组之间的关系。
seo-description: 在特征生成器中，通过表达式生成器，您可以创建和测试规则以确立受众资格要求。 规则由键值对组成，如“color == blue”或“price &gt;100”。 比较运算符可建立键和值之间的关系。 布尔表达式可确定规则组之间的关系。
seo-title: 管理特征规则
solution: Audience Manager
title: 管理特征规则
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: 特征
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 1%

---

# 管理特征规则 {#managing-trait-rules}

在[!UICONTROL Trait Builder]中，通过[!UICONTROL Expression Builder]，您可以创建和测试规则以确定受众资格要求。 规则由键值对组成，如`color == blue`或`price > 100`。 比较运算符可建立键和值之间的关系。 [!DNL Boolean] 表达式确定规则组之间的关系。

<!-- c_tb_rules.xml -->

## 描述的主要信号规则特征

![](assets/manage-trait-rules.png)

1. **[!UICONTROL Expression Builder]**&#x200B;或&#x200B;**[!UICONTROL Code View]**&#x200B;选项卡提供了特征中规则的概述。 使用&#x200B;**[!UICONTROL Expression Builder]**&#x200B;选项卡，可以创建包含字段和下拉菜单的规则。 **[!UICONTROL Code View]**&#x200B;允许您通过手动将这些表达式编写为代码来创建规则。 上图显示了一个简单特征，该特征由一个信号组成，该信号用于评估符合条件（在此例中，产品键等于特定值）的数据。`color == "blue"`

1. 利用此部分中的字段和控件，可从键值对创建信号，并使用比较运算符设置它们之间的关系。 需要键、运算符和值。
1. [!UICONTROL Data Explorer Options]允许您回填信号的特征实现。

   >[!NOTE]
   >
   >此选项仅适用于[!UICONTROL Data Explorer]客户。 有关详细信息，请联系您的Adobe顾问。

1. 此部分显示过去7天对于[!UICONTROL Expression Builder]中定义的信号、回填和未回填特征的特征实现情况的估计。

   >[!NOTE]
   >
   >此选项仅适用于[!UICONTROL Data Explorer]客户。 有关详细信息，请联系您的Adobe顾问。

1. 利用测试字段，可验证发送数据到Audience Manager时要使用的信号规则或[!DNL URL]的组合。

## 创建特征规则{#create-trait-rule}

规则（或表达式）由单个或一组键值对组成。 比较运算符可设置键值对之间的关系。 要创建规则，请提供键、值，选择运算符，然后单击&#x200B;**[!UICONTROL Add Rule]**。

<!-- t_tb_create_rules.xml -->

在&#x200B;*创建特征规则之前，填写&#x200B;**[!UICONTROL Basic Information]**部分*&#x200B;中的必填字段。

1. 展开&#x200B;**[!UICONTROL Trait Expression]**&#x200B;部分，然后输入键和值名称。 这会创建一个&#x200B;*`signal`*。

   >[!NOTE]
   >
   >如果事件调用使用该语法向[!DNL Audience Manager]发送数据，请为键变量包含`c_`前缀（或任何其他命名约定）。

1. 从&#x200B;**[!UICONTROL Operator]**&#x200B;下拉列表中选择[比较运算符](../../features/traits/trait-comparison-operators.md)。 比较运算符评估信号中元素之间的关系。

   >[!NOTE]
   >
   >[!DNL Boolean] [!UICONTROL OR]运算符建立&#x200B;*组内多个信号*&#x200B;之间的关系，不能更改。

1. 单击 **[!UICONTROL Add Rule]**. 保存的规则将显示在数据输入字段上方的特征工作区中。

### 示例 {#example-trait-rule}

在以下示例中，用户根据产品ID创建了新特征规则。 为构建此规则，用户向值`2093`提供了与等于运算符(`==`)链接的键`productkey`。

![](assets/tb_sample_rule1.png)

单击&#x200B;**[!UICONTROL Add Rule]**&#x200B;会保存特征并将其移入[!UICONTROL Expression Builder]工作区。

![](assets/tb_sample_rule2.png)

## 创建新规则组{#create-rule-group}

此过程说明如何创建新规则组。

<!-- t_tb_new_rule_group.xml -->

您的特征必须至少包含两个规则，才能创建新规则组。

1. 将光标移动到要移动的规则上以突出显示它。
1. 将鼠标悬停在突出显示的规则边框上。

   这会自动将规则与其当前组分隔，并将其移入新组。

   >[!NOTE]
   >
   >如果无意中移动规则，请将规则拖回其原始组。

1. 从下拉菜单中选择[!DNL Boolean]运算符([!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT])，以设置规则组之间的关系。

## 在组{#move-rules-between-groups}之间移动规则

要移动规则，请单击，然后将其拖动到另一个组。

## 编辑特征{#edit-trait}

此过程描述如何编辑特征。

<!-- t_tb_edit.xml -->

1. 在[!UICONTROL Traits]功能板中，将鼠标悬停在要编辑的特征的&#x200B;**[!UICONTROL Actions]**&#x200B;列上。 此时会显示特征管理图标。
1. 单击铅笔以编辑特征。

   ![](assets/tb_edit_trait.png)

## 删除特征规则{#delete-trait}

此过程说明如何删除特征规则。

<!-- t_tb_delete_rule.xml -->

1. 在[!UICONTROL Traits]功能板中，将鼠标悬停在要编辑的特征的[!UICONTROL Actions]列上，然后单击铅笔图标。 此时会显示特征管理图标。
1. 展开[!UICONTROL Trait Expression]部分。
1. 将鼠标悬停在要删除的规则上，然后单击X图标。 将立即删除该规则。

>[!MORELIKETHIS]
>
>* [创建新规则组](../../features/traits/manage-trait-rules.md#create-rule-group)
* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
* [创建特征规则](../../features/traits/manage-trait-rules.md#create-trait-rule)
* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)
* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

