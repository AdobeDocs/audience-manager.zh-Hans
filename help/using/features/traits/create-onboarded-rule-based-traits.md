---
description: 描述为基于规则和已载入的特征创建过程设置特定的步骤和功能。
keywords: 创建特征；创建特征
seo-description: 描述为基于规则和已载入的特征创建过程设置特定的步骤和功能。
seo-title: 创建基于规则或已载入的特征
solution: Audience Manager
title: 创建基于规则或已载入的特征
uuid: 4243e09f-1f96-443a-864a-d6e6918079fa
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# 创建基于规则或已载入的特征 {#create-rules-based-or-onboarded-traits}

描述设置特定于创建过程和特征 [!UICONTROL rules-based] 的步 [!UICONTROL onboarded] 骤和功能。

<!-- c_tb_rules_traits.xml -->

## 特征的基本信息 {#basics}

在中， [!UICONTROL Trait Builder]通过 [!UICONTROL Basic Information] 这些设置可以创建新特征或编辑现有特征。 基 [!UICONTROL Basic Information] 于规则、已载入的和算法特征的设置相同。 要创建新特征，请提供名称（避免特殊字符）、数据源，然后选择存储文件夹。 其他 [!UICONTROL Basic Information] 字段为可选字段。

<!-- c_tb_basics.xml -->

### 已定义的基本信息字段

<table id="table_42AEC7A5B22346C5BB996D2D36C56229"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 界面元素 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol">名称</span></b> </td> 
   <td colname="col2"> <p>特征名称。 必需. </p> <p>最大长度：255个字符。 </p> <p> <p>注意：在命名特征时，请避免使用以下特殊字符： 
      <ul id="ul_AB38A333F21A4AA9B5656CBA69BA65E3"> 
       <li id="li_0E5033B540BC41E799075845388E85A7">逗号 </li> 
       <li id="li_B1A6C3E3FB98473A91E4675EE09460F0">虚线 </li> 
       <li id="li_579302FE34B64FE0AE3C751012839229">连字符 </li> 
       <li id="li_44890F738CC64E449CC2545D701ECBC7">选项卡 </li> 
       <li id="li_C203837501A94342923C99A7DAD1ED61">竖条或管道符号 </li> 
      </ul> </p> </p> <p>这有助于减少在设置入站数据文件传输时 <a href="../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 的处理错误</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 描述</span></b> </td> 
   <td colname="col2"> 用几个词来描述特质的目的或功能。 可选。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 事件类型</span></b> </td> 
   <td colname="col2"> 将特征分配给类型或类别，通常根据函数（例如，转化、网站访客、合作伙伴、页面查看等）。 可选。 <p> 要了解如何创建转化特征，请参阅Audience Manager <a href="https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/traits-and-segments/creating-conversion-traits.html">中的创建转化特征视频</a>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 数据源</span></b> </td> 
   <td colname="col2"> 将特征与特定数据提供者关联。 必需. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 集成代码</span></b> </td> 
   <td colname="col2"> ID、SKU或内部业务流程使用的其他值的字段。 可选。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 评论</span></b> </td> 
   <td colname="col2"> 有关特征的一般说明。 可选。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 存储在</span></b> </td> 
   <td colname="col2"> 确定特征属于哪个存储文件夹。 必需. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 数据类别</span></b> </td> 
   <td colname="col2"> 根据常识类别对特征进行分类。 <p>注意： 特征只属于单个类别。 可选。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 设置特征到期间隔 {#set-expiration-interval}

在 [!UICONTROL Trait Builder]中， [!UICONTROL Advanced Options] 可设置特征的实时([!DNL TTL])间隔。 [!DNL TTL] 定义合格访客在某个特征中保留的天数（默认为120天）。 设置为0时，特征成员资格永不过期。

<!-- t_tb_ttl.xml -->

### 设置特征的TTL

1. 展开 [!UICONTROL Advanced Options] 该部分并输入一个数字以设置 [!DNL TTL] 特征的值。
2. 单击 **[!UICONTROL Save]**.
   ![](assets/TTL.png)

>[!MORE_LIKE_THIS]
>
>* [细分有效时间说明](../../features/traits/segment-ttl-explained.md)

