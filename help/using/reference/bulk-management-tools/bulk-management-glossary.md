---
description: 已定义列标题标签。
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: 批量管理工具术语表
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 0%

---

# 批量管理工具术语表{#bulk-management-tools-glossary}

已定义列标题标签。

>[!IMPORTANT]
>
>批量管理工具不是官方支持的Adobe产品。 通过客户关怀团队提供的故障排除和支持将按具体情况处理。

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]接受在[!DNL Audience Manager] UI中分配的[RBAC组权限](../../features/administration/administration-overview.md)。

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
   <td colname="col2"> <p>要返回或批量分配的<a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings">数据源</a>的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p><a href="../../features/derived-signals.md">派生的信号</a> ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">描述</span> </p> </td> 
   <td colname="col2"> <p>您可以为对象提供的简短的信息性描述。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">目标ID</span> </p> </td> 
   <td colname="col2"> <p>要映射或删除的<a href="../../features/destinations/destinations.md">目标</a>的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>区段映射到目标时分配给该区段的特殊ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>区段或特征文件夹的ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">名称</span> </p> </td> 
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
   <td colname="col2"> <p>信号是根据用户活动传递到<span class="keyword">Audience Manager</span>的数据位。 这些键值对以<a href="../../reference/key-value-pairs-explained.md">键值对</a>的形式传输。 源密钥是一个不变的常量。 它有助于对可更改的源值进行分类。 查看<a href="../../features/derived-signals.md">派生的信号</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>源值是作为<a href="../../reference/key-value-pairs-explained.md">键值对</a>的一部分传入的变量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>指示何时可以开始将区段发送到目标。 使用<i>yyyy-mm-dd</i>格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">在派生信号中使用的键。 查看<a href="../../features/derived-signals.md">派生的信号</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>使用派生的信号键传入的值。 查看<a href="../../features/derived-signals.md">派生的信号</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">特征别名</span> </p> </td> 
   <td colname="col2"> <p>传递到不基于Cookie的目标的ID。 对于基于Cookie的目标，这是<a href="../../reference/key-value-pairs-explained.md">键值对</a>中的键。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>用于收集数据的实际特征或区段规则。 批量请求返回使用<a href="../../features/traits/about-trait-builder.md">特征规则生成器</a>或<a href="../../features/segments/segment-builder.md">区段规则生成器</a>在<span class="keyword">Audience Manager</span>中创建的规则。 您还可以使用这些工具来构建规则，并在更新区段或特征时批量应用这些规则。 </p> <p>另请参阅<a href="../../reference/bulk-management-tools/bulk-rules.md">创建或更新特征规则和区段规则</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term">特征类型</span> </p> </td> 
   <td colname="col2"> <p>一个字符串，用于标识特征类型。 选项包括： </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>用户符合区段资格时DIL触发的像素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p><a href="../../reference/key-value-pairs-explained.md">键值对</a>中的键传递到Cookie目标。 </p> </td> 
  </tr> 
 </tbody> 
</table>
