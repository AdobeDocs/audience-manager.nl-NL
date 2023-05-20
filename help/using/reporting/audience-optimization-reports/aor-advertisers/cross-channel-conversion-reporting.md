---
description: Met de optie Kanaaloverschrijdende omzetting in de Audience Optimization-rapporten kunt u offlineconversies toewijzen aan bediende onlineafbeeldingen of kunt u klikken.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Cross-channelconversie
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 2%

---

# Cross-channelconversie{#cross-channel-conversion}

Met de optie Kanaaloverschrijdende omzetting in de Audience Optimization-rapporten kunt u offlineconversies toewijzen aan bediende onlineafbeeldingen of kunt u klikken.

De [!UICONTROL Cross Channel Conversion] de verslagen combineren resultaten van [!DNL Google Campaign Manager] platform met [!DNL Audience Manager] conversietekenmerken. Hiermee kunt u offlineconversies koppelen aan onlineafbeeldingen of klikt u erop.

U kunt de [!UICONTROL Cross Channel Conversion] voor de [Segmentprestaties](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) en [Optimale frequentie](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) rapporten.

Als u het dialoogvenster [!UICONTROL Cross Channel Conversion] rapporten, selecteert u de **[!UICONTROL AAM + Ad Server Name]** item in het **[!UICONTROL Platform]** vervolgkeuzelijst.

De volgende tabel bevat belangrijke overwegingen bij het instellen [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Overwegingen </th> 
   <th class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Minimumaantal omrekeningskenmerken </p> </td> 
   <td colname="col1"> <p>Ten minste één conversietekenmerk moet aan een gegevensbron worden toegewezen om <span class="wintitle"> Kanaalconversie</span> rapporten die moeten worden uitgevoerd. Zie <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basisinformatie over sporen</a> voor meer informatie over de kenmerken . </p> </td> 
  </tr>
  <tr> 
   <td> <p>Kenmerkvenster </p> </td> 
   <td> <p> <b><span class="uicontrol"> Campagnebeheer AAM+Google</span></b> attributievenster is 14 dagen, wat betekent dat alleen conversietekenmerken die in de laatste twee weken zijn tentoongesteld, in aanmerking worden genomen. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Last-touch-methodologie </p> </td> 
   <td> <p>Het creatieve dat de gebruiker het laatst heeft gezien alvorens om te zetten is degene die de omzetting toewijst. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Klikken en indrukken </p> </td> 
   <td> <p>Een klik krijgt voorrang boven een indruk wanneer het bepalen van de attributie als zij op het nauwkeurige zelfde ogenblik voorkomen. Op een pagina waarop bijvoorbeeld meerdere creatieve items worden weergegeven, krijgt u de conversie toegewezen waarop u klikt. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Recente gegevens </p> </td> 
   <td> <p>De rapporten worden altijd berekend voor gegevens beschikbaar de vorige dag. </p> </td> 
  </tr> 
 </tbody> 
</table>
