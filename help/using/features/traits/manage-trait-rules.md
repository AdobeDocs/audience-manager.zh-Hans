---
description: 在Travientity Builder中，Expression Builder允许您创建和测试确立受众资格要求的规则。规则由键值对组成，如“color== blue”或“price>100”。比较运算符建立键与值之间的关系。Boolean表达式确定规则组之间的关系。
seo-description: 在Travientity Builder中，Expression Builder允许您创建和测试确立受众资格要求的规则。规则由键值对组成，如“color== blue”或“price>100”。比较运算符建立键与值之间的关系。Boolean表达式确定规则组之间的关系。
seo-title: 管理特征规则
solution: Audience Manager
title: 管理特征规则
uuid: 827d4567-2b6f-411e-bd5 c-9735c916291 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Managing Trait Rules {#managing-trait-rules}

In [!UICONTROL Trait Builder], the [!UICONTROL Expression Builder] lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as `color == blue` or `price > 100`. 比较运算符建立键与值之间的关系。[!DNL Boolean] 表达式确定规则组之间的关系。

<!-- c_tb_rules.xml -->

## 介绍的主要信号规则功能

![](assets/manage-trait-rules.png)

1. **[!UICONTROL Expression Builder]****[!UICONTROL Code View]** 或选项卡概述了您的特征中的规则。**[!UICONTROL Expression Builder]** 该选项卡允许您创建包含字段和下拉菜单的规则。The **[!UICONTROL Code View]** lets you create rules by manually writing those expressions as code. The illustration above shows a simple trait composed of a signal that evaluates data for a qualifying condition where a product key equals a specific value, in this case `color == "blue"`.

1. 通过此部分中的字段和控件，您可以从关键值对创建信号，并设置与比较运算符之间的关系。关键、运算符和值是必需的。
1. [!UICONTROL Data Explorer Options] 允许您为信号回填特征真实性。
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. 有关详细信息，请与Adobe顾问联系。
1. This section shows you an estimation of trait realizations for the past 7 days, for the signals defined in the [!UICONTROL Expression Builder], for backfilled and non-backfilled traits.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. 有关详细信息，请与Adobe顾问联系。
1. The test fields let you validate combinations of signal rules or the [!DNL URL]s that you want to use when sending data to Audience Manager.

## Create a Trait Rule {#create-trait-rule}

规则(或表达式)由一个或多组关键值对组成。比较运算符设置键值对之间的关系。To create a rule,provide a key, a value, select an operator, and click **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete the required fields in the **[!UICONTROL Basic Information]** section *before* creating trait rules.

1. Expand the **[!UICONTROL Trait Expression]** section and enter a key and value name. This creates a *`signal`*.
   >[!NOTE]
   >
   >Include the `c_` prefix (or any other naming convention) for key variable if your event calls send data to [!DNL Audience Manager] using that syntax.
1. Select a [comparison operator](../../features/traits/trait-comparison-operators.md) from the **[!UICONTROL Operator]** dropdown. 比较运算符可评估信号中元素之间的关系。
   >[!NOTE]
   >
   >[!DNL Boolean][!UICONTROL OR] 运营商建立一个组 *内* 多个信号之间的关系，无法更改。
1. 单击 **[!UICONTROL Add Rule]**. 保存的规则显示在数据条目字段上方的特征工作区中。

### 示例 {#example-trait-rule}

在以下示例中，用户根据产品ID创建了新的特征规则。To build this rule, the user provided the key `productkey` linked with an equals operator ( `==`) to the value `2093`.
![](assets/tb_sample_rule1.png)

Clicking **[!UICONTROL Add Rule]** saves and moves the trait into the [!UICONTROL Expression Builder] workspace.

![](assets/tb_sample_rule2.png)

>[!MORE_ LIKE_ This]
>
>* [创建新规则组](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)


## Create a New Rule Group {#create-rule-group}

此过程介绍如何创建新规则组。

<!-- t_tb_new_rule_group.xml -->

您的特征必须至少包含两个规则，然后才能创建新规则组。

1. 将光标移到要移动的规则上，以突出显示该规则。
1. 将鼠标悬停在高亮显示的规则边框上方。
这会自动将规则与其当前组分开，并将其移至新组。
   >[!NOTE]
   >
   >如果您无意中移动规则，则将该规则拖回它的原始组。
1. Select a [!DNL Boolean] operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) from the drop-down menu to set the relationship between the rule groups.

>[!MORE_ LIKE_ This]
>
>* [创建特征规则](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [在组之间移动规则](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)


## Move Rules Between Groups {#move-rules-between-groups}

要移动规则，请单击并将其拖动到其他组。

>[!MORE_ LIKE_ This]
>
>* [创建特征规则](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [创建新规则组](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [删除特征规则](../../features/traits/manage-trait-rules.md#delete-trait)


## Edit a Trait {#edit-trait}

此过程介绍如何编辑特征。

<!-- t_tb_edit.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the trait you want to edit. 这将显示特征管理图标。
1. 单击铅笔以编辑特征。

   ![](assets/tb_edit_trait.png)

## Delete a Trait Rule {#delete-trait}

此过程介绍如何删除特征规则。

<!-- t_tb_delete_rule.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the [!UICONTROL Actions] columns for the trait you want to edit and click the pencil icon. 这将显示特征管理图标。
1. Expand the [!UICONTROL Trait Expression] section.
1. 将鼠标悬停在要删除的规则上，然后单击X图标。规则将立即删除。