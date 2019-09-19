---
description: 派生的信号根据访客已看到的特征使网站访客有资格获得其他特征。 换句话说，即使用户从未见过新特征，也可以从当前展示的特征派生其他特征资格。
seo-description: 派生的信号根据访客已看到的特征使网站访客有资格获得其他特征。 换句话说，即使用户从未见过新特征，也可以从当前展示的特征派生其他特征资格。
seo-title: 派生信号
solution: Audience Manager
title: 派生信号
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# 派生信号 {#derived-signals}

根据 [!UICONTROL derived signal] 访客已看到的特征，使网站访客有资格获得其他特征。 换句话说，即使用户从未见过新特征，也可以从当前展示的特征派生其他特征资格。

<!-- c_tb_derived_signal.xml -->

## 派生信号的用途

在中， [!DNL Audience Manager]您可以创建在事件调用期间传入的信号（或特征规则）与其他指定信号或特征之间的关系。 例如，假定事件调用在由键值()组成的信号中 [!DNL "product = new_car"]`https://<domain alias>/event?product=new_car`通过。 [!DNL Audience Manager] 会将该信号连接到使用该工具创建的任何其 [!UICONTROL derived signals] 他工具。 虽然关联的信号可以是您指定的任何键值，但是当链接到已设置为规则的现有信号时，这些信号最有 [!UICONTROL Trait Builder] 用。 例如，在下图中，当用户操作触发信号时，用户 [!DNL "product = new car"] 也可以符合目标键和值信号定义的特征。

![](assets/derived_signal_example.png)

## 派生信号的位置

在提要栏导 [!UICONTROL derived signals] 航中 **[!UICONTROL Tools > Derived Signals]** 创建和管理。

## 创建派生信号 {#create}

<!-- t_tb_create_derived.xml -->

要创建，请执行以下操 [!UICONTROL derived signal]作：

1. 从菜 **[!UICONTROL Derived Signals]** 单中选 [!UICONTROL Tools] 择。
1. 提供：
   * *（可选）*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 单击 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>、、和字段的字 [!UICONTROL Source Key]符限 [!UICONTROL Source Value]制为 [!UICONTROL Target Key]228 [!UICONTROL Target Value] 个字符。

## 编辑派生的信号 {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. 将鼠标悬停在信号上，然后单击 **[!UICONTROL Edit]**。
2. 更改所需的代码、键或值，然后单击 **[!UICONTROL Save]**。

## 删除派生信号 {#delete}

<!-- t_tb_delete_derived.xml -->

要删除信 [!UICONTROL derived signal]号，请将鼠标悬停在信号上，然后单击 **[!UICONTROL Delete]**。
