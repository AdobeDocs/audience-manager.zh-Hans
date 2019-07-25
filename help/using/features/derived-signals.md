---
description: 派生的信号可根据访客已经看到的特征来限定其他特征。换句话说，即使用户从未见过新的特征，也可以从当前展示的特征中衍生出其他特征资格资格资格。
seo-description: 派生的信号可根据访客已经看到的特征来限定其他特征。换句话说，即使用户从未见过新的特征，也可以从当前展示的特征中衍生出其他特征资格资格资格。
seo-title: 派生信号
solution: Audience Manager
title: 派生信号
uuid: e52600e3-26d1-4607-9b96-afd6086 a252 d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Derived Signals {#derived-signals}

A [!UICONTROL derived signal] qualifies site visitors for additional traits based on a trait they've already seen. 换句话说，即使用户从未见过新的特征，也可以从当前展示的特征中衍生出其他特征资格资格资格。

<!-- c_tb_derived_signal.xml -->

## 派生信号的用途

In [!DNL Audience Manager], you can create a relationship between signals (or trait rules) passed in during an event call to other, specified signals or traits. For example, assume an event call passes in a signal composed of the key-value [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] 会将该信号连接到使用该 [!UICONTROL derived signals] 工具创建的任何其他内容。Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as [!UICONTROL Trait Builder] rules. For example, in the illustration below, when a user action fires the signal [!DNL "product = new car"] that user can also qualify for traits defined by the target key and value signals.

![](assets/derived_signal_example.png)

## 派生信号的位置

Create and manage [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** from the sidebar navigation.

## Create a Derived Signal {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. Select **[!UICONTROL Derived Signals]** from the [!UICONTROL Tools] menu.
1. 提供：
   * *(可选)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 单击 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>The character limit for the [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key], and [!UICONTROL Target Value] fields is 228 characters.

## Edit a Derived Signal {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Hover over the signal, then click **[!UICONTROL Edit]**.
2. Make the required code, key, or value changes, then click **[!UICONTROL Save]**.

## Delete a Derived Signal {#delete}

<!-- t_tb_delete_derived.xml -->

To delete a [!UICONTROL derived signal], hover over the signal, then click **[!UICONTROL Delete]**.
