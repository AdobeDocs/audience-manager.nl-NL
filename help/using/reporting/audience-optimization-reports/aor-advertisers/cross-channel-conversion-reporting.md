---
description: Met de optie Kanaaloverschrijdende omzetting in de Audience Optimization-rapporten kunt u offlineconversies toewijzen aan bediende onlineafbeeldingen of kunt u klikken.
seo-description: Met de optie Kanaaloverschrijdende omzetting in de Audience Optimization-rapporten kunt u offlineconversies toewijzen aan bediende onlineafbeeldingen of kunt u klikken.
seo-title: Cross-channelconversie
solution: Audience Manager
title: Cross-channelconversie
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%

---


# Cross-channelconversie{#cross-channel-conversion}

Met de optie Kanaaloverschrijdende omzetting in de Audience Optimization-rapporten kunt u offlineconversies toewijzen aan bediende onlineafbeeldingen of kunt u klikken.

In de [!UICONTROL Cross Channel Conversion]-rapporten worden de resultaten van het [!DNL Google Campaign Manager]-platform gecombineerd met de conversietekenmerken [!DNL Audience Manager]. Hiermee kunt u offlineconversies koppelen aan onlineafbeeldingen of klikt u erop.

U kunt [!UICONTROL Cross Channel Conversion] voor [de Prestaties van het Segment](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) en [Optimale Frequentie](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) rapporten gebruiken.

Als u de [!UICONTROL Cross Channel Conversion]-rapporten wilt weergeven, selecteert u het item **[!UICONTROL AAM + Ad Server Name]** in de vervolgkeuzelijst **[!UICONTROL Platform]**.

De volgende tabel bevat belangrijke overwegingen bij het instellen van [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>Er moet ten minste één conversietekenmerk aan een gegevensbron worden toegewezen om de rapporten <span class="wintitle"> Kanaalconversie</span> te kunnen uitvoeren. Zie <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basisinformatie voor Traits</a> voor meer informatie over eigenschappen. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Kenmerkvenster </p> </td> 
   <td> <p> <b><span class="uicontrol"> Het attributievenster van AAM+Google Campaign </span></b> Manager is 14 dagen, wat betekent dat alleen conversietekenmerken die in de laatste twee weken zijn tentoongesteld, in aanmerking worden genomen. </p> </td> 
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
