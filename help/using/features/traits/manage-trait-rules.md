---
description: 在特征生成器中，表达式生成器允许您创建和测试建立受众资格要求的规则。 规则由键值对组成，如“color == blue”或“price&amp；gt； 100”。 比较运算符建立键和值之间的关系。 布尔表达式确定规则组之间的关系。
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: 管理特征规则
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 0%

---

# 管理特征规则 {#managing-trait-rules}

在[!UICONTROL Trait Builder]中，[!UICONTROL Expression Builder]允许您创建和测试建立受众资格要求的规则。 规则包含键值对，如`color == blue`或`price > 100`。 比较运算符建立键和值之间的关系。 [!DNL Boolean]表达式确定规则组之间的关系。

<!-- c_tb_rules.xml -->

## 描述的主要信号规则功能

![](assets/manage-trait-rules.png)

1. **[!UICONTROL Expression Builder]**&#x200B;或&#x200B;**[!UICONTROL Code View]**&#x200B;选项卡提供特征中规则的概述。 **[!UICONTROL Expression Builder]**&#x200B;选项卡允许您创建包含字段和下拉菜单的规则。 **[!UICONTROL Code View]**&#x200B;允许您通过手动将这些表达式写入代码来创建规则。 上图显示了一个由信号组成的简单特征，该信号评估产品键等于特定值（在此例中为`color == "blue"`）的合格条件的数据。

1. 此部分中的字段和控件允许您从键值对创建信号，并使用比较运算符设置它们之间的关系。 键、运算符和值是必需的。
1. [!UICONTROL Data Explorer Options]允许您回填信号的特征实现。

   >[!NOTE]
   >
   >此选项仅适用于[!UICONTROL Data Explorer]个客户。 有关详细信息，请与Adobe顾问联系。

1. 此部分针对在[!UICONTROL Expression Builder]中定义的信号，针对回填和非回填特征，显示过去7天特征实现的估计值。

   >[!NOTE]
   >
   >此选项仅适用于[!UICONTROL Data Explorer]个客户。 有关详细信息，请与Adobe顾问联系。

1. 测试字段允许您验证信号规则的组合或向Audience Manager发送数据时要使用的[!DNL URL]的组合。

## 创建特征规则 {#create-trait-rule}

规则（或表达式）由单个键值对或键值对组组成。 比较运算符设置键值对之间的关系。 要创建规则，请提供键、值、选择运算符，然后单击&#x200B;**[!UICONTROL Add Rule]**。

<!-- t_tb_create_rules.xml -->

在创建特征规则之前，请先填写&#x200B;**[!UICONTROL Basic Information]**&#x200B;部分&#x200B;*中的必填字段*。

1. 展开&#x200B;**[!UICONTROL Trait Expression]**&#x200B;部分并输入键和值名称。 这将创建一个&#x200B;*`signal`*。

   >[!NOTE]
   >
   >如果您的事件调用使用该语法将数据发送到`c_`，请包含键变量的[!DNL Audience Manager]前缀（或任何其他命名约定）。

1. 从[下拉列表中选择](../../features/traits/trait-comparison-operators.md)比较运算符&#x200B;**[!UICONTROL Operator]**。 比较运算符评估信号中元素之间的关系。

   >[!NOTE]
   >
   >[!DNL Boolean] [!UICONTROL OR]运算符在&#x200B;*组内的多个信号*&#x200B;之间建立关系，且无法更改。

1. 单击&#x200B;**[!UICONTROL Add Rule]**。 保存的规则将显示在数据输入字段上方的特征工作区中。

### 示例 {#example-trait-rule}

在以下示例中，用户已根据产品ID创建新的特征规则。 为生成此规则，用户提供了键`productkey`，该键与值`==`的equals运算符(`2093`)链接。

![](assets/tb_sample_rule1.png)

单击&#x200B;**[!UICONTROL Add Rule]**&#x200B;可保存特征并将其移到[!UICONTROL Expression Builder]工作区。

![](assets/tb_sample_rule2.png)

## 创建新规则组 {#create-rule-group}

此过程说明如何创建新规则组。

<!-- t_tb_new_rule_group.xml -->

您的特征必须至少包含两个规则，才能创建新规则组。

1. 将光标移动到要移动的规则上以突出显示它。
1. 将鼠标悬停在突出显示的规则边框上。

   这会自动将规则与其当前组分离，并将其移动到新组中。

   >[!NOTE]
   >
   >如果无意中将规则移回原始组，请将其拖回原始组。

1. 从下拉菜单中选择一个[!DNL Boolean]运算符([!UICONTROL AND]、[!UICONTROL OR]、[!UICONTROL AND NOT])以设置规则组之间的关系。

## 在组之间移动规则 {#move-rules-between-groups}

要移动规则，请单击该规则并将其拖动到其他组。

## 编辑特征 {#edit-trait}

此过程描述如何编辑特征。

<!-- t_tb_edit.xml -->

1. 在[!UICONTROL Traits]仪表板中，将鼠标悬停在要编辑的特征的&#x200B;**[!UICONTROL Actions]**&#x200B;列上。 这会显示特征管理图标。
1. 单击铅笔可编辑特征。

   ![](assets/tb_edit_trait.png)

## 删除特征规则 {#delete-trait}

此过程描述如何删除特征规则。

<!-- t_tb_delete_rule.xml -->

1. 在[!UICONTROL Traits]仪表板中，将鼠标悬停在要编辑的特征的[!UICONTROL Actions]列上，然后单击铅笔图标。 这会显示特征管理图标。
1. 展开[!UICONTROL Trait Expression]部分。
1. 将鼠标悬停在要删除的规则上，然后单击X图标。 规则将立即删除。

>[!MORELIKETHIS]
>
>* [创建新规则组](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [创建特征规则](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)
>* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
