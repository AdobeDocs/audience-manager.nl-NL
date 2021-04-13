---
description: Op deze pagina vindt u een overzicht van informatie die rechtstreeks door onze partners wordt verstrekt wanneer deze beschikbaar wordt, samen met eventuele implicaties voor uw gebruik van Audience Manager. De belangrijkste implicaties voor partners die deze updates uitvoeren, zijn het resultaat van de GDPR (General Data Protection Regulation of AVG), die op 25 mei 2018 in werking is getreden, en het nieuwe IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-description: Op deze pagina vindt u een overzicht van informatie die rechtstreeks door onze partners wordt verstrekt wanneer deze beschikbaar wordt, samen met eventuele implicaties voor uw gebruik van Audience Manager. De belangrijkste implicaties voor partners die deze updates uitvoeren, zijn het resultaat van de GDPR (General Data Protection Regulation of AVG), die op 25 mei 2018 in werking is getreden, en het nieuwe IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR (AVG)-overwegingen voor bestemmingen
solution: Audience Manager
title: GDPR (AVG)-overwegingen voor bestemmingen
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Beheer en privacy van gegevens
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 96%

---

# GDPR (AVG)-overwegingen voor bestemmingen {#gdpr-considerations-for-destinations}

Op deze pagina vindt u een overzicht van informatie die rechtstreeks door onze partners wordt verstrekt wanneer deze beschikbaar wordt, samen met eventuele implicaties voor uw gebruik van Audience Manager. De belangrijkste implicaties voor partners die deze updates uitvoeren, zijn het resultaat van de GDPR (General Data Protection Regulation of AVG), die op 25 mei 2018 in werking is getreden, en het nieuwe IAB GDPR Transparency &amp; Consent Framework (IAB Framework).

Adobe-partners zijn eigenaar van hun bedrijfsprocessen en kunnen besluiten hun integratievereisten met Audience Manager van tijd tot tijd bij te werken. Wij werken proactief met ons Audience Manager-partnerecosysteem om onze klanten van veranderingen op de hoogte te houden.

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table> -->

## Update van gebruikersinterface voor Audience Manager - Yahoo/Oath/DataX-integratie {#ui-update}

Naast de hierboven vermelde updates van het IAB-framework heeft Yahoo/Oath/DataX de nieuwe parameters **gdpr** en **gdpr_mode** toegevoegd aan hun taxonomie- en Audience-API’s. Hun parameters laten Yahoo/Oath/DataX weten dat ze de rechten hebben om een bepaald segment te verwerken als dataverwerker of datacontroller. Daardoor moeten Audience Manager-klanten die segmenten naar een Yahoo/Oath/DataX-bestemming verzenden, de juiste parameter (Processor of Controller) aangeven op basis van hun overeenkomst met Oath.

Neem contact op met uw consultant of de klantenservice om de juiste parameter in te stellen. Adobe kan deze update niet namens een klant uitvoeren, tenzij we schriftelijke correspondentie ontvangen waarin deze update wordt aangevraagd. Neem contact op met uw Yahoo/Oath/DataX-vertegenwoordiger voor meer informatie over de volledige definitie van deze parameters.
