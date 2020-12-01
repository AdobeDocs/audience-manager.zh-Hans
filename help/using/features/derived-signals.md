---
description: 派生信号根据站点访客已看到的特征使站点数据有资格获得其他特征。 换言之，即使用户以前从未见过新特征，也可以从当前展示的特征中衍生出其他特征资格。
seo-description: 派生信号根据站点访客已看到的特征使站点数据有资格获得其他特征。 换言之，即使用户以前从未见过新特征，也可以从当前展示的特征中衍生出其他特征资格。
seo-title: 派生的信号
solution: Audience Manager
title: 派生的信号
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---


# 派生的信号 {#derived-signals}

[!UICONTROL derived signal]根据站点访客已看到的特征，确定其他特征。 换言之，即使用户以前从未见过新特征，也可以从当前展示的特征中衍生出其他特征资格。

<!-- c_tb_derived_signal.xml -->

## 派生信号的用途

在[!DNL Audience Manager]中，您可以在事件调用期间传入的信号（或特征规则）之间创建关系，以调用其他指定的信号或特征。 例如，假定事件调用通过由key-value [!DNL "product = new_car"](`https://<domain alias>/event?product=new_car`)组成的信号。 [!DNL Audience Manager] 会将该信号连接到使用该工具创建的任何其 [!UICONTROL derived signals] 他人。虽然关联信号可以是您指定的任何键值，但当链接到已设置为[!UICONTROL Trait Builder]规则的现有信号时，它们最有用。 例如，在下图中，当用户操作触发信号[!DNL "product = new car"]时，用户还可以符合由目标键和值信号定义的特征。

![](assets/derived_signal_example.png)

## 派生信号的位置

在提要栏导航中创建和管理&#x200B;**[!UICONTROL Tools > Derived Signals]**&#x200B;中的[!UICONTROL derived signals]。

## 创建派生信号{#create}

<!-- t_tb_create_derived.xml -->

要创建[!UICONTROL derived signal]:

1. 从[!UICONTROL Tools]菜单中选择&#x200B;**[!UICONTROL Derived Signals]**。
1. 提供：
   * *（可选）* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 单击 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>[!UICONTROL Source Key]、[!UICONTROL Source Value]、[!UICONTROL Target Key]和[!UICONTROL Target Value]字段的字符限制为228个字符。

## 编辑派生信号{#edit}

<!-- t_tb_edit_derived.xml -->

要编辑[!UICONTROL derived signal]:

1. 将鼠标悬停在信号上，然后单击&#x200B;**[!UICONTROL Edit]**。
2. 更改所需的代码、键或值，然后单击&#x200B;**[!UICONTROL Save]**。

## 删除派生信号{#delete}

<!-- t_tb_delete_derived.xml -->

要删除[!UICONTROL derived signal]，请将鼠标悬停在信号上，然后单击&#x200B;**[!UICONTROL Delete]**。
