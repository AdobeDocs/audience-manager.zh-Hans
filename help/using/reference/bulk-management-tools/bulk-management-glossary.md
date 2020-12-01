---
description: 列标题标签已定义。
seo-description: 列标题标签已定义。
seo-title: 批量管理工具术语表
solution: Audience Manager
title: 批量管理工具术语表
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: baaam
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 5%

---


# 批量管理工具术语表{#bulk-management-tools-glossary}

列标题标签已定义。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[在UI](../../features/administration/administration-overview.md) 中分配的RBAC [!DNL Audience Manager] 组权限在中得到保 [!UICONTROL Bulk Management Tools]留。

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 列标题 </th> 
   <th colname="col2" class="entry"> 定义 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>要批量返回或分配的<a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings">数据源</a>的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p><a href="../../features/derived-signals.md">派生信号</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>您可以为对象提供的简短、信息丰富的描述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>要映射或删除的<a href="../../features/destinations/destinations.md">目标</a>的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>将区段映射到目标时分配给区段的特殊ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>区段或特征文件夹的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>您正在处理的对象的名称。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>包含其他文件夹的区段或特征文件夹的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sid</span> </p> </td> 
   <td colname="col2"> <p>区段ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>信号是根据用户Audience Manager传递到<span class="keyword">活动</span>的数据位。 这些值以<a href="../../reference/key-value-pairs-explained.md">键值对</a>的形式传输。 源键是不变的常数。 它有助于对可以更改的源值进行分类。 请参阅<a href="../../features/derived-signals.md">派生信号</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>源值是作为<a href="../../reference/key-value-pairs-explained.md">键值对</a>的一部分传入的变量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>指示何时可将开始发送到目标。 使用<i>yyyy-mm-dd</i>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">派生信号中使用的键。 请参阅<a href="../../features/derived-signals.md">派生信号</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>用派生信号键传递的值。 请参阅<a href="../../features/derived-signals.md">派生信号</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>传递到非基于Cookie的目标的ID。 对于基于cookie的目标，这是<a href="../../reference/key-value-pairs-explained.md">键值对</a>中的键。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule/segmentRule</span> </p> </td> 
   <td colname="col2"> <p>用于收集数据的实际特征或区段规则。 批量请求返回在<span class="keyword">Audience Manager</span>中使用<a href="../../features/traits/about-trait-builder.md">特征规则生成器</a>或<a href="../../features/segments/segment-builder.md">段规则生成器</a>创建的规则。 在更新段或特征时，您还可以使用这些工具构建规则并批量应用它们。 </p> <p>另请参阅<a href="../../reference/bulk-management-tools/bulk-rules.md">创建或更新特征规则和区段规则</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>标识特征类型的字符串。 选项包括： </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>当用户符合段条件时由DIL触发的像素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p><a href="../../reference/key-value-pairs-explained.md">键值对</a>中传递到cookie目标的键。 </p> </td> 
  </tr> 
 </tbody> 
</table>

