---
description: 在Trait builder中，通过Expression Builder可创建和测试确立受众资格要求的规则。 规则由键值对组成，如“color == blue”或“price > 100”。 比较运算符建立键和值之间的关系。 布尔表达式确定规则组之间的关系。
seo-description: 在Trait builder中，通过Expression Builder可创建和测试确立受众资格要求的规则。 规则由键值对组成，如“color == blue”或“price > 100”。 比较运算符建立键和值之间的关系。 布尔表达式确定规则组之间的关系。
seo-title: 管理特征规则
solution: Audience Manager
title: 管理特征规则
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 管理特征规则 {#managing-trait-rules}

在中， [!UICONTROL Trait Builder]您可 [!UICONTROL Expression Builder] 以创建和测试确立受众资格要求的规则。 规则由键值对组成，如 `color == blue` 或 `price > 100`。 比较运算符建立键和值之间的关系。 [!DNL Boolean] 表达式确定规则组之间的关系。

<!-- c_tb_rules.xml -->

## 描述的主要信号规则功能

![](assets/manage-trait-rules.png)

1. 这些 **[!UICONTROL Expression Builder]** 或 **[!UICONTROL Code View]** 多个选项卡概述了您的特征中的规则。 通过 **[!UICONTROL Expression Builder]** 该选项卡，您可以创建包含字段和下拉菜单的规则。 通过 **[!UICONTROL Code View]** 手动将这些表达式编写为代码，可创建规则。 上图显示了由一个信号组成的简单特征，该信号对产品键等于特定值的限定条件的数据进行评估，在这种情况下 `color == "blue"`。

1. 此部分中的字段和控件允许您从键值对创建信号，并使用比较运算符设置它们之间的关系。 键、运算符和值是必需的。
1. 它 [!UICONTROL Data Explorer Options] 允许您回填信号的特征实现。
   >[!NOTE]
   >
   >此选项仅对客户 [!UICONTROL Data Explorer] 可用。 有关详细信息，请与Adobe顾问联系。
1. 此部分显示过去7天中为回填和非回填特征定义的信号对特 [!UICONTROL Expression Builder]征实现的估计。
   >[!NOTE]
   >
   >此选项仅对客户 [!UICONTROL Data Explorer] 可用。 有关详细信息，请与Adobe顾问联系。
1. 通过测试字段，您可以验证向Audience manager发送数 [!DNL URL]据时要使用的信号规则或规则的组合。

## 创建特征规则 {#create-trait-rule}

规则（或表达式）由单个或一组键值对组成。 比较运算符设置键值对之间的关系。 要创建规则，请提供键、值，选择运算符，然后单击 **[!UICONTROL Add Rule]**。

<!-- t_tb_create_rules.xml -->

在创建特征规则之前，请先填写 **[!UICONTROL Basic Information]** 该 *部分中* 的必填字段。

1. 展开部 **[!UICONTROL Trait Expression]** 分并输入键和值名称。 这会创建 *`signal`*。
   >[!NOTE]
   >
   >如果事 `c_` 件调用使用该语法向发送数据，则为键变量添加前缀(或任何其他命名约 [!DNL Audience Manager] 定)。
1. 从下拉列 [表中选择比较运](../../features/traits/trait-comparison-operators.md)**[!UICONTROL Operator]** 算符。 比较运算器评估信号中各元素之间的关系。
   >[!NOTE]
   >
   >该操 [!DNL Boolean] 作器在 [!UICONTROL OR] 一个组内的多个信号之间 *建立关系* ，并且不能改变。
1. 单击 **[!UICONTROL Add Rule]**. 保存的规则显示在数据条目字段上方的特征工作区中。

### 示例 {#example-trait-rule}

在以下示例中，用户已基于产品ID创建了新的特征规则。 要构建此规则，用户将与等号运 `productkey` 算符()链接的键提 `==`供到值 `2093`。
![](assets/tb_sample_rule1.png)

单击 **[!UICONTROL Add Rule]** 将保存特征并将其移入工作 [!UICONTROL Expression Builder] 区。

![](assets/tb_sample_rule2.png)

>[!MORE_LIKE_THIS]
>
>* [创建新规则组](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)


## 创建新规则组 {#create-rule-group}

此过程介绍如何创建新规则组。

<!-- t_tb_new_rule_group.xml -->

您的特征必须至少包含两个规则，然后才能创建新规则组。

1. 将光标移到要移动的规则上以突出显示它。
1. 将鼠标悬停在高亮显示的规则边框上。
这会自动将规则与其当前组分开，并将其移入新组。
   >[!NOTE]
   >
   >如果无意中移动规则，请将其拖回原始组。
1. 从下拉 [!DNL Boolean] 菜单中选 [!UICONTROL AND]择一个运 [!UICONTROL OR]算符(,, [!UICONTROL AND NOT])，以设置规则组之间的关系。

>[!MORE_LIKE_THIS]
>
>* [创建特征规则](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)


## 在组之间移动规则 {#move-rules-between-groups}

要移动规则，请单击并将其拖动到另一个组。

>[!MORE_LIKE_THIS]
>
>* [创建特征规则](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [创建新规则组](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)


## 编辑特征 {#edit-trait}

此过程介绍如何编辑特征。

<!-- t_tb_edit.xml -->

1. 在功 [!UICONTROL Traits] 能板中，将指针悬 **[!UICONTROL Actions]** 停在要编辑的特征的列上。 这会显示特征管理图标。
1. 单击铅笔以编辑特征。

   ![](assets/tb_edit_trait.png)

## 删除特征规则 {#delete-trait}

此过程介绍如何删除特征规则。

<!-- t_tb_delete_rule.xml -->

1. 在功 [!UICONTROL Traits] 能板中，将指针悬 [!UICONTROL Actions] 停在要编辑的特征列上，然后单击铅笔图标。 这会显示特征管理图标。
1. Expand the [!UICONTROL Trait Expression] section.
1. 将指针悬停在要删除的规则上并单击X图标。 该规则将立即删除。