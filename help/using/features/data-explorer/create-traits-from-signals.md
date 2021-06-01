---
description: 从所有信号（包括已在特征中使用的特征）创建新特征，并捕获在特征创建后符合条件的未来受众。
seo-description: 从所有信号（包括已在特征中使用的特征）创建新特征，并捕获在特征创建后符合条件的未来受众。
seo-title: 从信号创建特征
title: 从信号创建特征
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# 从信号创建特征

从所有信号（包括已在特征中使用的特征）创建新特征，并捕获在特征创建后符合条件的未来受众。 观看视频以快速演示或阅读以了解详细信息：

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## 从信号仪表板{#create-traits-from-signal-dashboard}创建特征

[!UICONTROL Signal Dashboard]允许您从[!UICONTROL Top Unused Signals]、[!UICONTROL New Unused Signals]和保存的搜索创建新特征。

创建新特征时，会根据信号类型预先设置特征类型：

* **[!UICONTROL Rule-based]** 实时信号、可操作的日志文件和信号的 [!DNL Adobe Analytics] 特征；

* **[!UICONTROL Onboarded]** 已载入信号的特征。

要从&#x200B;**[!UICONTROL Signal Dashboard]**&#x200B;创建新特征，请识别要在特征中使用的信号，然后单击相应的&#x200B;**[!UICONTROL Create Rule-Based Trait]**&#x200B;或&#x200B;**[!UICONTROL Create Onboarded Trait]**&#x200B;链接。

![](assets/signals-create-trait.png)

您将被重定向到&#x200B;**[特征生成器](../../features/traits/about-trait-builder.md)**&#x200B;以创建新特征。

## 从信号搜索创建特征{#create-traits-from-signal-search}

根据[!UICONTROL Signal Dashboard]中未显示的已使用或未使用信号创建特征。

搜索特定信号，并根据结果创建基于规则的特征或已载入的特征。 下面是如何执行此操作：

1. 转到&#x200B;**[!UICONTROL Audience Data > Signals > Search]**&#x200B;并根据要查找的键值对运行搜索，或单击&#x200B;**[!UICONTROL Search]**&#x200B;而不输入任何键值对以显示所有结果。
2. 在结果列表中识别要在特征中使用的信号。
   * 要从一个信号创建特征，请单击相应的&#x200B;**[!UICONTROL Create Rule-Based Trait]**&#x200B;或&#x200B;**[!UICONTROL Create Onboarded Trait]**&#x200B;链接。
   * 要从多个信号创建特征，请单击每个信号的相应复选框，然后单击&#x200B;**[!UICONTROL Create Trait from Multiple Signals]**。

   >[!NOTE]
   >您只能根据同一类型的信号创建特征。 您无法基于实时信号和已载入信号的组合创建特征。
   >
   > ![](assets/signals-create-trait-search.png)
   >您也可以根据使用的信号创建特征。 已在特征中使用的信号具有&#x200B;**[!UICONTROL Included in Traits]**&#x200B;列中显示的特征数。 单击箭头可查看包含信号的特征。
   >
   >![](assets/signals-used-traits.png)

3. 使用&#x200B;**[特征生成器](../../features/traits/about-trait-builder.md)**&#x200B;创建新特征。
