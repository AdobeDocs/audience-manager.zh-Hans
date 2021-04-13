---
description: 格式化入站特征数据文件时应遵循的必填字段、语法和规则。
seo-description: 格式化入站特征数据文件时应遵循的必填字段、语法和规则。
seo-title: 入站数据文件内容语法、无效字符、变量和示例
solution: Audience Manager
title: 入站数据文件内容语法、无效字符、变量和示例
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: 入站数据传输
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '1196'
ht-degree: 4%

---

# 入站数据文件内容：语法、无效字符、变量和示例 {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

格式化入站特征数据文件时应遵循的必填字段、语法和规则。

## 文件内容语法{#file-content-syntax}

入站数据文件中的字段必须按以下顺序显示。 在此示例中，已添加`<` `>`符号，以帮助以可视方式分离每个元素。 您无需在数据文件中包含这些内容。

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

有关其他已接受的文件内容格式，请参阅[自定义合作伙伴集成](/help/using/integration/sending-audience-data/custom-partner-integrations.md)。

>[!NOTE]
>
>对于入站数据文件中发送的每个用户ID，我们最多可处理200行。 例如，如果您为用户ID发送300行，则前200行将保留，另外100行将被放弃。 在以下示例中，您做得不错，因为您每行发送3行，分别代表用户ID 1和用户ID 2。 我们不对您在行中包含的特征或键值对的数量设置限制。
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## 定义的文件变量{#file-variables-defined}

表列表并定义格式正确的入站数据文件中使用的变量。 *斜体*&#x200B;表示变量占位符。

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 变量 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>用户ID可以是： </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">由<span class="keyword">Audience Manager</span>(<a href="../../../reference/ids-in-aam.md">Audience ManagerUUID </a>)分配的唯一用户ID。 </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">在CRM系统中分配的唯一用户ID(在Audience Manager</a>中为<a href="../../../reference/ids-in-aam.md"> DPUUID)。 </a></li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">移动Android或iOS设备ID，其原始的、未修改的形式由移动操作系统公开。 </li> 
     </ul> </p> <p>对于移动ID: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA格式：ID必须大写，而不是散列。 例如，<code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android格式：ID必须小写，而不是散列。 例如，<code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>使用单个制表符分隔符分隔用户ID和特征ID。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword">Audience Manager</span>特征ID。 我们要求在入站数据文件中仅包含<i>已载入的特征</i>。 在入站数据传输中，我们不处理任何其他特征类型。 </p> <p> <p>注意： 特征ID可通过使用返回所有特征详细信息的GET方法来找到。 有关详细信息，请参阅<a href="../../../api/rest-api-main/api-traits.md">特征API方法</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 格式化[!UICONTROL Trait IDs] {#formatting-trait-ids}

下表描述了标识入站数据文件中[!UICONTROL trait]名称或ID的前缀。 有关示例，请参见[示例文件](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples)。

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 前缀 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p><code> d_sid </code>前缀告诉我们的系统ID是<span class="keyword">Audience Manager</span>特征ID。 这是用户界面中显示的同一ID。 您还可以使用API <code> GET </code>方法返回特征ID。 请参阅<a href="../../../api/rest-api-main/api-traits.md">特征API方法</a>。 </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>以<code> d_unsid </code>为前缀的数据会从该特征中删除用户。 在<code> overwrite </code>文件中忽略<code> d_unsid </code>前缀。 </p> <p><code> d_unsid= </code>前缀告诉我们的系统ID是<span class="keyword">Audience Manager</span>特征ID。 这是用户界面中显示的同一ID。 您还可以使用API <code> GET </code>方法返回特征ID。 请参阅<a href="../../../api/rest-api-main/api-traits.md">特征API方法</a>。 </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 特征规 </a> 则允许您设置特征限定条件。如果将特征规则格式设置为<code> ic == trait ID </code>，则可以以简单的逗号格式列表发送特征。 </p> <p>例如，假设您创建了以下3个特征规则： </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>这些特征与<code> ic </code>键关联。 这样，您就可以在数据文件中创建更简单的特征列表。 而且，您不需要包含<code> ic </code>前缀。 因此，数据文件的内容可能如下所示： </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>键值对 </p> </td> 
   <td colname="col2"> <p>特征数据可以使用字母数字字符串作为键值对进行格式化。 有几种格式化键值对的方法，如下所示： </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> ,, <code> "gender"=m </code> 是 <code> model = "pickup truck" </code> 正 <code> product = tablet </code> 确格式键值对的示例。 </p> </td> 
  </tr>
 </tbody>
</table>

## [!UICONTROL Trait IDs]、[!UICONTROL User IDs]和键值对{#invalid-chars}中的字符无效

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] 只包含数字字符。我们要求在入站数据文件中仅包含&#x200B;*[!UICONTROL onboarded traits]*。 在入站数据传输中，我们不处理任何其他[!UICONTROL trait]类型。

### [!UICONTROL User IDs]

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 类型 </th> 
   <th colname="col2" class="entry"> 要求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>请</i> 勿使用编码冒号() <code> %3A </code>或未编码冒号(:)符号。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile iOS(IDFA)或Android设备ID </p> </td> 
   <td colname="col2"> <p>移动设备ID必须严格格式化，如下所示： </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA格式：ID必须大写，而不是散列。 例如，<code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android格式：ID必须小写，而不是散列。 例如，<code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 键值对

键值对中的值名称格式不正确也会导致问题。 创建或命名键值对中的值时，请遵循以下规则：

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 字符 </th> 
   <th colname="col2" class="entry"> 要求 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>引号字符(") </p> </td> 
   <td colname="col2"> <p>您可以在键和键值对的值部分中使用引号字符，如： </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>虚线字符(-) </p> </td> 
   <td colname="col2"> <p>我们不理钥匙开始的破折号。 例如，<code> -product = camera </code>解释为<code> product = camera </code>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>不</i> 要 <code> TAB </code> 在键值对中使用空值。仅使用<code> TAB </code>在入站数据文件中分隔变量。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>请勿在键或值中使用新行或制表符字符(<code> \n, \t </code>)。 </p> </td> 
  </tr>
 </tbody>
</table>

## 数据文件示例{#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 数据文件格式 </th> 
   <th colname="col2" class="entry"> 说明和示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>具有<code> d_sid </code>或<code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>此数据文件显示符合特征24、26、27的用户，已从特征28和29中删除。 </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>注释:  <p>您还可以使用以下语法从用户用户档案中删除特征，而不是使用d_unsid: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>通过 <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>这些特征已添加到具有<code> ic </code>前缀的特征规则中。 因此，您可以将它们添加到以逗号分隔的数据文件中，如所示。 制表符分隔UUID和特征ID。 文件中不需要<code> ic </code>前缀。 </p> <p><b>数字ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>字符串ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>带键值对 </p> </td> 
   <td colname="col2"> 此文件数据使用键值对将数据传递到<span class="keyword">Audience Manager</span>。 <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[如果](assets/ftp_dpm_1234_1445374061.overwrite) 您需要其他示例，请下载示例数据文件。下载文件具有`.overwrite`文件扩展名。 您可以使用简单的文本编辑器打开它。

## 示例矩阵{#examples-matrix}

下图显示了格式化入站文件的正确方法示例，具体取决于[类型的ID](../../../reference/ids-in-aam.md)以及向用户档案添加[!UICONTROL traits]的方法。

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID类型/操作 </th> 
   <th colname="col2" class="entry"> 使用d_sid向用户用户档案添加特征 </th> 
   <th colname="col3" class="entry"> 使用d_unsid从用户用户档案中删除特征 </th> 
   <th colname="col4" class="entry"> 发送键值对以向用户用户档案添加特征 </th> 
   <th colname="col5" class="entry"> 使用ic前缀向用户用户档案添加特征 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience ManagerUUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> 示例1  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> 示例2  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> 示例3  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> 示例4  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>适用于Android设备的Google广告ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 示例5  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 示例6  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 示例7  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 示例8  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>适用于iOS设备的Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> 示例9  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 示例10  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 示例11  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 示例12  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>您自己的CRM ID(DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 示例13  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 示例14  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 示例15  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 示例16  </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 示例1 {#example-1}

使用[!UICONTROL trait IDs]发送[!DNL Audience Manager] [!DNL UUIDs]的[!UICONTROL trait]资格信息。

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### 示例2 {#example-2}

使用[!UICONTROL trait IDs]发送[!DNL Audience Manager] [!DNL UUIDs]的[!UICONTROL trait]取消资格信息。

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

或

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

或

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### 示例3 {#example-3}

发送键值对，以添加[!DNL Audience Manager] [!DNL UUIDs]的[!UICONTROL trait]资格信息。

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

或

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### 示例4 {#example-4}

使用`ic`前缀可发送[!DNL Audience Manager] [!DNL UUIDs]的[!UICONTROL trait]资格信息。

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

或

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### 示例5 {#example-5}

使用[!UICONTROL trait IDs]发送[!DNL Android]设备的[!UICONTROL trait]资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 示例6 {#example-6}

使用[!UICONTROL trait IDs]发送[!DNL Android]设备的[!UICONTROL trait]取消资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### 示例7 {#example-7}

发送键值对，以添加[!DNL Android]设备的[!UICONTROL trait]资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### 示例8 {#example-8}

使用`ic`前缀可发送[!DNL Android]设备的[!UICONTROL trait]资格信息。

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

或

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### 示例9 {#example-9}

使用[!UICONTROL trait IDs]发送[!DNL iOS]设备的[!UICONTROL trait]资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 示例10 {#example-10}

使用[!UICONTROL trait IDs]发送[!DNL iOS]设备的[!UICONTROL trait]取消资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### 示例11 {#example-11}

发送键值对，以添加[!DNL iOS]设备的[!UICONTROL trait]资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### 示例12 {#example-12}

使用`ic`前缀可发送[!DNL iOS]设备的[!UICONTROL trait]资格信息。

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

或

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### 示例13 {#example-13}

使用[!UICONTROL trait IDs]发送[!DNL DPUUIDs]的[!UICONTROL trait]资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### 示例14 {#example-14}

使用[!UICONTROL trait IDs]发送[!DNL DPUUIDs]的[!UICONTROL trait]取消资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### 示例15 {#example-15}

发送键值对，以添加[!DNL DPUUIDs]的[!UICONTROL trait]资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### 示例16 {#example-16}

使用`ic`前缀可发送[!DNL DPUUIDs]的[!UICONTROL trait]资格信息。

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

或

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [特征生成器](../../../features/traits/about-trait-builder.md)

