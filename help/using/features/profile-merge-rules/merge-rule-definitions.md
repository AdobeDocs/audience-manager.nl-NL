---
description: Met de opties voor samenvoegregels kunt u het type gegevens bepalen dat Audience Manager gebruikt voor segmentatie. Een samenvoegregel kan apparaatprofielen bevatten die zijn toegewezen door de apparaatgrafiek van de Verbinding van het Profiel en/of andere, apparaatgrafiekproviders van derden die zijn geïntegreerd met Audience Manager. U kunt maximaal vier regels voor het samenvoegen van profielen maken.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Opties voor regel voor samenvoegen van profiel gedefinieerd
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules] Gedefinieerde opties {#profile-merge-rule-options-defined}

Met de opties van [!UICONTROL profile merge rule] kunt u het type gegevens bepalen dat [!DNL Audience Manager] gebruikt voor segmentatie. Een [!UICONTROL profile merge rule] kan apparaatprofielen bevatten die zijn toegewezen door de [!UICONTROL Profile Link] -apparaatgrafiek en/of andere, externe apparaatgrafiekproviders die zijn geïntegreerd met [!DNL Audience Manager] . U kunt maximaal 4 [!UICONTROL Profile Merge Rules] maken. De vierde [!UICONTROL Profile Merge Rule] is uitsluitend beschikbaar voor klanten die de [!UICONTROL People-Based Destinations] add-on hebben aangeschaft.

U maakt een [!UICONTROL Profile Merge Rule] door een selectie te maken van de opties die hieronder worden beschreven, in [!UICONTROL Profile Merge Rule Setup] .

![&#x200B; profiel-fusie-regel-opstelling &#x200B;](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Overzicht van opties {#overview}

[!UICONTROL Profile Merge Rules] staat voor een aantal regelcombinaties toe, elk gericht op specifieke gebruiksgevallen. Zie de tabel hieronder voor meer informatie over het gebruik van elke regelcombinatie.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Beschikbaarheid | Type evaluatie | [!UICONTROL Audience Lab] Ondersteuning | Gevallen gebruiken |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alle klanten | Realtime en batch | Ja | [&#x200B; Apparaat richtend &#x200B;](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Alle klanten | Realtime en batch | Nee | [&#x200B; Uitgebreid Apparaat richtend &#x200B;](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alle klanten | Alleen in realtime | Nee | [&#x200B; Gedeeld Apparaat richtend &#x200B;](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alle klanten | Realtime en batch | Ja | [&#x200B; Online/Off-line het richten &#x200B;](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alle klanten | Realtime en batch | Ja | [&#x200B; dwars-apparaat richtend &#x200B;](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Alle klanten | Realtime en batch | Nee | [&#x200B; Geavanceerde dwars-Apparaat richtend &#x200B;](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | NVT | Exclusief aan [&#x200B; op mensen-Gebaseerde klanten &#x200B;](../destinations/people-based-destinations-overview.md) | Alleen batch | Nee | [&#x200B; het richten voor op mensen-Gebaseerde Doelen &#x200B;](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Evaluatie {#segment-evaluation}

Afhankelijk van uw [!UICONTROL Profile Merge Rules] -configuratie kan [!DNL Audience Manager] de [!UICONTROL segment] -evaluatie in realtime, in batch of beide uitvoeren.

* [!UICONTROL segment] In realtime evaluatie vereist dat de [!DNL DCS] bezoekers in real-time toegang krijgen tot uw digitale eigenschappen om in aanmerking te komen voor de [!UICONTROL segment] .
* De batchevaluatie [!UICONTROL segment] wordt uitgevoerd op basis van eerder gekwalificeerde [!UICONTROL traits] .
* [!UICONTROL Profile Merge Rules] die zowel realtime als batchevaluatie ondersteunen, combineren de realtime bezoekersactiviteit met eerder gekwalificeerde [!UICONTROL segment] .[!UICONTROL traits]

## [!UICONTROL Profile Merge Rules] Latentie melden {#reporting-latency}

Real-time [!UICONTROL segment] evaluatie weerspiegelt direct in de [!UICONTROL Profile Merge Rules] -rapporten.

De evaluatie van de partij [!UICONTROL segment] kan tot 24 uren vergen om in de [&#x200B; rapporten van de Regels van de Fusie van het Profiel te bezigen &#x200B;](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

Met [!UICONTROL Cross-Device Options] kunt u geverifieerde en niet-geverifieerde gebruikers selecteren en hun profiel voor alle apparaten gebruiken voor segmentatie. Met deze opties kunt u specifieke gebruikers op een gedeeld apparaat identificeren en bereiken. Voor meer informatie over anonieme en voor authentiek verklaarde gebruikers, zie {de Staten van de Authentificatie van 0} Visitor in Audience Manager [.](../../reference/visitor-authentication-states.md)

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Optie voor meerdere apparaten </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geen profiel voor meerdere apparaten </span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager </span> om geen gegevens te gebruiken die van voor authentiek verklaarde gebruikers worden verzameld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Huidige geverifieerde profielen </span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager </span> om gegevens te lezen en te schrijven aan het voor authentiek verklaarde profiel als een bezoeker aan uw plaats heeft het programma geopend. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Laatst geverifieerde profielen </span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager </span> om gegevens van het voor authentiek verklaarde profiel van de gebruiker te lezen die het laatst op het apparaat het programma opende. </p> <p>Als deze optie is geselecteerd, schrijft <span class="keyword"> Audience Manager </span> geen nieuwe gegevens over de eigenschap naar het geverifieerde profiel als de gebruiker anoniem is. Bij verificatie worden nieuwe doelgegevens naar het geverifieerde profiel van de gebruiker geschreven. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle profielen voor meerdere apparaten </span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee wordt aan Audience Manager doorgegeven dat gegevens uit alle apparaatprofielen moeten worden gelezen, ongeacht de verificatiestatus. Deze optie is alleen beschikbaar voor Audience Manager-klanten die de invoegtoepassing voor op mensen gebaseerde doelen hebben aangeschaft.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

In [!UICONTROL Cross-Device Profile Options] wordt de lijst met [!UICONTROL cross-device data sources] weergegeven. Deze opties gebruiken de namen u verstrekte toen u a [!UICONTROL cross-device] [!UICONTROL data source] creeerde (zie [&#x200B; een Gegevens van het Interapparaat Source &#x200B;](merge-rules-start.md#create-data-source) creëren). U kunt maximaal 3 [!UICONTROL cross-device data sources] selecteren voor gebruik met elke profielregel. [!UICONTROL Authenticated Profile Options] zijn beschikbaar wanneer u **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** kiest.

## [!UICONTROL Device Options] {#device-options}

Met [!UICONTROL Device Options] kunt u het type *`device profile`* selecteren dat door een [!UICONTROL Profile Merge Rule] wordt gebruikt. Een apparaatprofiel is gemaakt op basis van [!UICONTROL traits] , dat is verzameld op basis van anonieme browseractiviteiten. Een [!UICONTROL profile merge rule] bevat minimaal een [!UICONTROL authenticated option] en een [!UICONTROL device option] .

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Apparaatoptie </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geen apparaatprofiel </span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager </span> om de eigenschappen in het anonieme profiel voor segmentatie niet te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatprofiel </span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager </span> om het anonieme apparatenprofiel voor segmentatie te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatgrafiek voor profielkoppeling </span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager </span> om de profielen van het huidige apparaat en tot 100 andere apparaten te lezen die de gebruiker van voor authentiek verklaard heeft. Deze apparatengrafiek wordt voortgebouwd op uw eigen, eerste-partijgegevens in <span class="keyword"> Audience Manager </span>. Dit is ideaal voor klanten die een hoog verificatieniveau hebben voor hun digitale eigenschappen. De <span class="wintitle"> het apparatengrafiek van de Verbinding van het Profiel </span> wordt bijgewerkt in echt - tijd. Deze optie is beschikbaar wanneer u <b><span class="uicontrol"> Huidig voor authentiek verklaard Profiel </span></b> of <b><span class="uicontrol"> Laatste voor authentiek verklaard Profiel </span></b> selecteert. Wanneer het gebruiken van deze optie, kunt u slechts één enkel voor authentiek verklaard profiel kiezen (<span class="keyword"> Audience Manager </span> grijst automatisch anderen). Zie ook, <a href="profile-link-use-case.md"> Gevallen van het Gebruik van de Grafiek van het Apparaat van de Verbinding van het Profiel </a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b> de Opties van de Grafiek van het Apparaat van de Derde </b> (Persoon en Huishouden) </p> </td>
   <td colname="col2"> <p>Met deze opties kunt u fusieregels samenstellen op basis van apparaatgrafiektechnologie die door een externe leverancier wordt geleverd. Een apparaatgrafiek van derden biedt de volgende mogelijkheden: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistische en/of deterministische gegevens. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Gegevens per persoon of per huishouden. </li> 
     </ul> </p> <p>Als u deze opties wilt gebruiken, moet u een klant zijn van een apparaatgrafiek die al is geïntegreerd met <span class="keyword"> Audience Manager </span> . Neem contact op met uw accountmanager voor meer informatie of om aan de slag te gaan. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

De segmenten van het publiek die automatisch van andere [!DNL Experience Cloud] oplossingen werden gecreeerd, die op fusieregels buiten [!DNL Audience Manager] worden bepaald worden gebaseerd, duidelijk zoals het gebruiken van [!UICONTROL External Merge Policy]. Bijvoorbeeld, zie [&#x200B; Publiek dat tussen Audience Manager en Adobe Experience Platform &#x200B;](../../integration/integration-aep/aam-aep-audience-sharing.md) deelt.

>[!MORELIKETHIS]
>
>* [&#x200B; Veelgestelde vragen van de Regels van de Fusie van het Profiel &#x200B;](../../faq/faq-profile-merge.md)
