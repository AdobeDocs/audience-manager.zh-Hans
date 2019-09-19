---
description: 已定义列标题标签。
seo-description: 已定义列标题标签。
seo-title: 批量管理工具词汇表
solution: Audience Manager
title: 批量管理工具词汇表
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 批量管理工具词汇表{#bulk-management-tools-glossary}

已定义列标题标签。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>不 [!UICONTROL Bulk Management Tools] 支持 *。*[!DNL Audience Manager]此工具仅出于方便和礼貌而提供。 对于批量更改，我们建议您改用 [Audience Manager API](../../api/rest-api-main/aam-api-getting-started.md) 。 [在UI中分配的](../../features/administration/administration-overview.md) RBAC组权限 [!DNL Audience Manager] 在UI中被接受 [!UICONTROL Bulk Management Tools]。

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
   <td colname="col2"> <p>要批量返回 <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> 或分配</a> 的数据源的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>导出 <a href="../../features/derived-signals.md"> 的信号</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> description</span> </p> </td> 
   <td colname="col2"> <p>可为对象提供的简短、信息性说明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>要映射或删 <a href="../../features/destinations/destinations.md"> 除的目标</a> ID。 </p> </td> 
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
   <td colname="col2"> <p>信号是根据用户活动传入 <span class="keyword"> Audience Manager的数据位</span> 。 这些值作为键 <a href="../../reference/key-value-pairs-explained.md"> 值对传输</a>。 源键是不变的常数。 它有助于对可能更改的源值进行分类。 请参阅 <a href="../../features/derived-signals.md"> 派生的信号</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>源值是作为键值对的一部分传 <a href="../../reference/key-value-pairs-explained.md"> 入的变量</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>指示区段何时开始发送到目标。 使用 <tt>yyyy-mm-dd格式</tt> 。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">派生信号中使用的键。 请参阅 <a href="../../features/derived-signals.md"> 派生的信号</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>与派生的信号键一起传入的值。 请参阅 <a href="../../features/derived-signals.md"> 派生的信号</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>传递到非基于Cookie的目标的ID。 对于基于cookie的目标，这是键值对 <a href="../../reference/key-value-pairs-explained.md"> 中的键</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>用于收集数据的实际特征或区段规则。 批量请求将返回在 <span class="keyword"> Audience Manager中使用特征规则构建器</span> 或区段规则构建器创 <a href="../../features/traits/about-trait-builder.md"> 建的规则</a><a href="../../features/segments/segment-builder.md"></a>。 在更新段或特征时，您还可以使用这些工具构建规则并批量应用这些规则。 </p> <p>另请参阅创 <a href="../../reference/bulk-management-tools/bulk-rules.md"> 建或更新特征规则和区段规则</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>标识特征类型的字符串。 选项包括： </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_HOCKED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> 区段</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>当用户符合区段条件时由DIL触发的像素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>传递到Cookie目标 <a href="../../reference/key-value-pairs-explained.md"> 的键值对中的键</a> 。 </p> </td> 
  </tr> 
 </tbody> 
</table>

