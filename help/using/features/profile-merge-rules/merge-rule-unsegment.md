---
description: 取消分段描述了将设备配置文件从区段中取消资格和删除的过程。 您能否从区段中删除设备配置文件取决于用于创建配置文件合并规则的设备选项。
seo-description: 取消分段描述了将设备配置文件从区段中取消资格和删除的过程。 您能否从区段中删除设备配置文件取决于用于创建配置文件合并规则的设备选项。
seo-title: 配置文件合并规则和设备取消分段过程
solution: Audience Manager
title: 配置文件合并规则和设备取消分段过程
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 配置文件合并规则和设备取消分段过程 {#profile-merge-rules-and-device-un-segmentation-processes}

取消分段描述了将设备配置文件从区段中取消资格和删除的过程。 您能否从区段中删除设备配置文件取决于用于创建设备的设备选项 [!UICONTROL Profile Merge Rule]。

## 可用的设备选项 {#device-options}

作为提醒，在创 [!UICONTROL Device Options] 建或编辑 [!UICONTROL Profile Merge Rules Setup] 时，部分中会显示这些 [!UICONTROL Profile Merge Rule]。

![](assets/merge-rules-options.png)

## 当前设备配置文件选项和设备取消分段 {#current-device-profile-options}

**[!UICONTROL Current Device Profile]** 是设备的默认配置文件选 [!UICONTROL Profile Merge Rule]项 [!DNL Audience Manager] 可以在您使用该选项时从区段中删除设 [!UICONTROL Profile Merge Rule] 备配置 **[!UICONTROL Current Device Profile]** 文件。 在这些情况下，当出现以下情况时，将发生取消分段：

* 设备配置文件已停用120天。 每周的数据清理过程可从您的区段中删除非活动的设备配置文件。
* 设备不再有资格获得区段，因为设备配置文件的更新或更改会取消区段资格。 当区段资格条件发生更改，或者您对区段规则应用运算符，或者指定使用小于／等于设置的 [!DNL AND NOT] 最近和频率条件时 [](../../features/segments/recency-and-frequency.md) ，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了用例](../../features/profile-merge-rules/instant-cross-device-suppression.md) 。

![](assets/single_device_use_case.png)

<!-- 

<p> <span class="keyword"> Audience Manager</span> can remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses the <b><span class="uicontrol"> Current Device Profile</span></b> option. Under these conditions, unsegmentation happens when: </p> 
<p> 
 <ul id="ul_596501272A224228BD330DD56E01D973"> 
  <li id="li_E4FA1A5C722748CD82AE3A49FCBE86F6">The device profile has been inactive for 120-days. A weekly data cleanup process removes inactive device profiles from your segments. </li> 
  <li id="li_DB0CCD28425048D5B35309B8C2C384F9">The device no longer qualifies for a segment because updates or changes to the device profile disqualify it. This happens when segment qualification criteria change, or you apply an AND NOT operator to a segment rule, or specify <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> conditions that use the less than/equal to settings. </li> 
 </ul> </p> 
<p style="text-align: center;"> <img src="assets/unsegment3.png" id="image_B55E5A5EB1964AA08C817211006294E1" /> </p>

 -->

## 无设备选项和设备取消分段 {#no-device-option}

[!DNL Audience Manager] 在您使用+选项时，可以从区段中删 [!UICONTROL Profile Merge Rule] 除跨设 **[!UICONTROL No Device Profile]** 备ID **[!UICONTROL Current Authenticated]** 。 在这些情况下，当跨设备ID不再符合区段资格时，会发生取消分段，因为对跨设备配置文件的更新或更改将取消分段资格。 当区段资格条件发生更改，或者您对区段规则应用运算符，或者指定使用小于／等于设置的 [!UICONTROL AND NOT] 最近和频率条件时 [](../../features/segments/recency-and-frequency.md) ，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了用例](../../features/profile-merge-rules/instant-cross-device-suppression.md) 。

![](assets/no_device_use_case.png)

## 设备图选项和设备取消分段 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] 使用设备图形选项时，可从区段中删除 [!UICONTROL Profile Merge Rule] 多个设备配置文件。 当设备图形中设备的合并配置文件不再符合区段的条件时，会发生取消分段，因为对此合并配置文件的更新或更改会使其不符合区段的条件。 当区段资格条件发生更改，或者您对区段规则应用运算符，或者指定使用小于／等于设置的 [!UICONTROL AND NOT] 最近和频率条件时 [](../../features/segments/recency-and-frequency.md) ，会发生这种情况。 “即时跨设备抑制”文 [档中介绍了用例](../../features/profile-merge-rules/instant-cross-device-suppression.md) 。

>[!NOTE]
>
>**在使用设备图来评估区段时** ，针对区段评估和取消资格的四个设备限制最多 [!DNL Audience Manager][!UICONTROL Profile Merge Rule] 可合并四个设备。 [!DNL Audience Manager] 评估当 *前设备和最后一个实时查看的三个其他设备*。 如果发出未分段信号，则当前设备和三个实时显示的附加设备将从目标的分段中移除。 例如，在六设备群集中，最多四个设备被合并、评估和限定为区段。 同样，最多四个设备被合并、评估和未分段。

![](assets/cross_device_workflow.png)

<!-- 

<p>Currently, <span class="keyword"> Audience Manager</span> <i>cannot </i> remove a device profile from a segment when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This applies to rules created with these <span class="wintitle"> Device Options</span> settings: </p> 
<p> 
 <ul id="ul_0923834C984F464E9AB12FF5A8773214"> 
  <li id="li_731F67B7A07342988B13D7F91ECA5A9E">Profile Link Device Graph. </li> 
  <li id="li_D1EFC6F124124E64A0732DD060F788BE">The <span class="keyword"> Adobe</span> device graph. </li> 
  <li id="li_CFD4189D4488432D92732532D23B30C7">Other third-party device graph options available that are available to you. </li> 
 </ul> </p> 
<p> Unlike the previous case above, using the AND NOT operator or less than/equal to settings won't remove all of the devices from a segment profile. However, you can unsegment device profiles if you create simple segment rules and apply unsegment logic in the destination that receives your data. The following sections walks you through different unsegmentation use cases. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with Boolean <span class="wintitle"> AND NOT</span> logic when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. This procedure uses separate, simple segments mapped to the same destination. In this case, you apply AND NOT logic on the destination rather than creating rules in Segment Builder. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_677F0F9E6CB640079D9021DE66819916"> 
  <li id="li_95F898FDFB2D4F5395201FEA2E60A3AF">Create separate, single-trait segments as shown in the following example. <p style="text-align: center;"><img src="assets/unsegment1.png" id="image_9574D599F449482F8475D9AD2B725DE1" /> </p> </li> 
  <li id="li_3A9F6D8B3CBB4F65B9A06EEC3B265158">Map the segments to the same destination. In this case, we're sending these to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_092BB5887D0D4EE4B09F4B1C6703D454">Set AND NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. <p style="text-align: center;"><img src="assets/unsegment2.png" id="image_1E707693ABED41129F11F9FBA334DA58" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply AND NOT logic on whatever destination receives these segments. </p>

 -->



<!-- 

<p>This workaround shows you how to unsegment with the < = (less than/equal to) recency and frequency settings when your <span class="wintitle"> Profile Merge Rule</span> uses a device graph option. To set up unsegment rules for this use case: </p> 
<p> 
 <ol id="ol_DCBEE004B9FE40A881E4EC17FAEA50C2"> 
  <li id="li_DB8C1B6D5C5546E68769902A4F367966">Create a segment that contains a single trait and apply a > = (greater than/equal to) recency and frequency rule to the trait. <p style="text-align: center;"><img src="assets/unsegment4.png" id="image_38069E00B8E8435AAD6E4420CC788D1E" /> </p> </li> 
  <li id="li_0DC50960D83B4B27A40F0BC76B944E0B">Map the segment to a destination. In this case, we're sending the segment to <span class="keyword"> Media Optimizer</span>. </li> 
  <li id="li_FC23194A9FE54296914393F8067A6672">Set NOT logic on the destination (<span class="keyword"> Media Optimizer</span>) rather than in <span class="keyword"> Audience Manager</span>. Use NOT logic to exclude all devices that qualify for this segment from your campaign. <p style="text-align: center;"><img src="assets/unsegment5.png" id="image_BE4408DCB12041A191F208CB1807B9E6" /> </p> </li> 
 </ol> </p> 
<p> If you're not using <span class="keyword"> Media Optimizer</span>, apply NOT logic on whatever destination receives these segments. </p>

 -->

>[!MORE_LIKE_THIS]
>
>* [配置文件合并规则和设备图常见问题解答](../../faq/faq-profile-merge.md)
>* [即时跨设备抑制](../../features/profile-merge-rules/instant-cross-device-suppression.md)
>* [关于设备图的配置文件合并规则的重要注意事项](../../features/profile-merge-rules/considerations-pmr-device-graph.md)

