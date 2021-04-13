---
description: Met de opties voor samenvoegregels kunt u het type gegevens bepalen dat Audience Manager gebruikt voor segmentatie. Een fusieregel kan apparatenprofielen omvatten die door de het apparatengrafiek van de Verbinding van het Profiel, de Co-op van het Apparaat van Adobe Experience Cloud, en/of andere, derdeapparatengrafiekleveranciers worden in kaart gebracht die met Audience Manager zijn geïntegreerd. U kunt maximaal vier regels voor het samenvoegen van profielen maken.
seo-description: Met de opties voor samenvoegregels kunt u het type gegevens bepalen dat Audience Manager gebruikt voor segmentatie. Een fusieregel kan apparatenprofielen omvatten die door de het apparatengrafiek van de Verbinding van het Profiel, de Co-op van het Apparaat van Adobe Experience Cloud, en/of andere, derdeapparatengrafiekleveranciers worden in kaart gebracht die met Audience Manager zijn geïntegreerd. U kunt maximaal vier regels voor het samenvoegen van profielen maken.
seo-title: Definities van opties voor regels voor profielsamenvoeging.
solution: Audience Manager
title: Definities van opties voor regels voor profielsamenvoeging.
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profielsamenvoeging
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 2%

---

# [!UICONTROL Profile Merge Rules] Gedefinieerde opties  {#profile-merge-rule-options-defined}

Met de opties [!UICONTROL profile merge rule] kunt u het type gegevens bepalen dat [!DNL Audience Manager] gebruikt voor segmentatie. Een [!UICONTROL profile merge rule] kan apparaatprofielen bevatten die zijn toegewezen door de apparaatgrafiek [!UICONTROL Profile Link], de [!UICONTROL Adobe Experience Cloud Device Co-op] en/of andere externe apparaatgrafiekproviders die zijn geïntegreerd met [!DNL Audience Manager]. U kunt maximaal 4 [!UICONTROL Profile Merge Rules] maken. De vierde [!UICONTROL Profile Merge Rule] is uitsluitend beschikbaar voor klanten die de [!UICONTROL People-Based Destinations]-invoegtoepassing hebben aangeschaft.

U maakt een [!UICONTROL Profile Merge Rule] door een selectie te maken van de hieronder beschreven opties, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Overzicht van opties  {#overview}

[!UICONTROL Profile Merge Rules] een aantal regelcombinaties mogelijk te maken, elk gericht op specifieke gebruiksgevallen. Zie de tabel hieronder voor meer informatie over het gebruik van elke regelcombinatie.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Beschikbaarheid | Type evaluatie | [!UICONTROL Audience Lab] Ondersteuning | Gevallen gebruiken |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alle klanten | Realtime en batch | Ja | [Apparaatgericht](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (inclusief  [!UICONTROL Co-op Device Graph]) | Alle klanten | Realtime en batch | Nee | [Uitgebreide doelapparaten](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alle klanten | Alleen in realtime | Nee | [Gedeelde apparaatdoelen](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alle klanten | Realtime en batch | Ja | [Online/offline gericht](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alle klanten | Realtime en batch | Ja | [Toewijzing op meerdere apparaten](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (inclusief  [!UICONTROL Co-op Device Graph]) | Alle klanten | Realtime en batch | Nee | [Geavanceerde interDevice-doelen](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N.v.t. | Exclusief naar [Op mensen gebaseerde Doelen](../destinations/people-based-destinations-overview.md) klanten | Alleen batch | Nee | [Doelen voor op mensen gebaseerde bestemmingen](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Evaluatie  {#segment-evaluation}

Afhankelijk van uw [!UICONTROL Profile Merge Rules] configuratie, [!DNL Audience Manager] kan [!UICONTROL segment] evaluatie in real time, in partij, of allebei uitvoeren.

* [!UICONTROL segment] evaluatie in real time vereist [!DNL DCS] om bezoekers toegang tot uw digitale eigenschappen in real time te zien, om voor [!UICONTROL segment] in aanmerking te komen.
* De batchevaluatie [!UICONTROL segment] wordt uitgevoerd tegen eerder gekwalificeerd [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] die zowel  [!UICONTROL segment] evaluatie in real time als partijevaluatie steunen combineert de activiteit van de bezoeker in real time met eerder gekwalificeerd  [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Rapportageachterstand  {#reporting-latency}

Real-time [!UICONTROL segment] evaluatie weerspiegelt onmiddellijk in [!UICONTROL Profile Merge Rules] rapporten.

De evaluatie van de partij [!UICONTROL segment] kan tot 24 uren vergen om in [rapporten van de Regels van de Fusie van het Profiel te weerspiegelen](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

Met [!UICONTROL Cross-Device Options] kunt u geverifieerde en niet-geverifieerde gebruikers selecteren en hun profiel voor alle apparaten gebruiken voor segmentatie. Met deze opties kunt u specifieke gebruikers op een gedeeld apparaat identificeren en bereiken. Voor meer informatie over anonieme en voor authentiek verklaarde gebruikers, zie [De Staten van de Authentificatie van de Bezoeker in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Optie voor meerdere apparaten </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geen profiel voor meerdere apparaten</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager</span> om geen gegevens te gebruiken die van voor authentiek verklaarde gebruikers worden verzameld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Huidige geverifieerde profielen</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager</span> om gegevens aan het voor authentiek verklaarde profiel te lezen en te schrijven als een bezoeker aan uw plaats heeft het programma geopend. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Laatst geverifieerde profielen</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager</span> om gegevens van het voor authentiek verklaarde profiel van de gebruiker te lezen die het laatst op het apparaat het programma opende. </p> <p>Als deze optie is geselecteerd, worden nieuwe gegevens over de eigenschap <span class="keyword"> niet naar het geverifieerde profiel geschreven als de gebruiker anoniem is. </span> Bij verificatie worden nieuwe doelgegevens naar het geverifieerde profiel van de gebruiker geschreven. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle profielen voor meerdere apparaten</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt Audience Manager om gegevens van alle cross-device profielen, ongeacht de authentificatiestatus te lezen. Deze optie is alleen beschikbaar voor klanten van Audience Managers die de invoegtoepassing voor op mensen gebaseerde doelen hebben aangeschaft.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

De [!UICONTROL Cross-Device Profile Options] geeft een lijst van uw [!UICONTROL cross-device data sources]. Deze opties gebruiken de namen u verstrekte toen u [!UICONTROL cross-device] [!UICONTROL data source] creeerde (zie [een Gegevensbron van het Apparaat van de Maken](merge-rules-start.md#create-data-source)). U kunt maximaal 3 [!UICONTROL cross-device data sources] selecteren om met elke profielregel te gebruiken. De [!UICONTROL Authenticated Profile Options] zijn beschikbaar wanneer u **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]** kiest.

## [!UICONTROL Device Options] {#device-options}

Met [!UICONTROL Device Options] kunt u het type *`device profile`* selecteren dat door een [!UICONTROL Profile Merge Rule] wordt gebruikt. Er wordt een apparaatprofiel gemaakt op basis van [!UICONTROL traits] die is verzameld op basis van anonieme browseractiviteiten. Een [!UICONTROL profile merge rule] bevat ten minste een [!UICONTROL authenticated option] en een [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Apparaatoptie </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geen apparaatprofiel</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager</span> om de eigenschappen in het anonieme profiel voor segmentatie niet te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatprofiel</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager</span> om het anonieme apparatenprofiel voor segmentatie te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatgrafiek profielkoppeling</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager</span> om de profielen van het huidige apparaat en tot 100 andere apparaten te lezen die de gebruiker van voor authentiek verklaard heeft. Deze apparatengrafiek wordt voortgebouwd op uw eigen, eerste-partijgegevens in <span class="keyword"> Audience Manager</span>. Dit is ideaal voor klanten die een hoog verificatieniveau hebben voor hun digitale eigenschappen. De <span class="wintitle"> Verbinding van het Profiel</span> apparatengrafiek wordt bijgewerkt in echt - tijd. Deze optie is beschikbaar wanneer u <b><span class="uicontrol"> Huidige geverifieerd Profiel</span></b> of <b><span class="uicontrol"> Laatste geverifieerd Profiel</span></b> selecteert. Wanneer u deze optie gebruikt, kunt u slechts één geverifieerd profiel kiezen (<span class="keyword"> Audience Manager</span> grijst automatisch de andere). Zie ook <a href="profile-link-use-case.md"> Gevallen van de Grafiek van het Apparaat van de Verbinding van het Profiel </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Afbeelding van apparaat voor coop</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt <span class="keyword"> Audience Manager</span> om de profielen van het huidige apparaat en tot 100 andere apparaten te lezen gebruikend de verbindingen die door <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Coop van het Apparaat van de Experience Cloud worden verstrekt </a>. </p> <p>De <span class="keyword"> Device Co-op</span> is een digitale coöperatie waar deelnemende klanten koppelingsinformatie over apparaten delen. De <span class="keyword"> ApparaatCo-op</span> verwerkt deze gegevens in een <span class="term"> apparatengrafiek</span>. Een apparaatgrafiek koppelt apparaten aan elkaar in apparaatclusters. Deze verbindingen worden gebouwd van <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> probabilistische en deterministische gegevens</a>. De clusters vertegenwoordigen een groep apparaten die door een onbekende persoon worden gebruikt. De <span class="keyword"> Device Co-op</span> deelt deze clusters onder zijn leden, wat hen helpt waardevolle en consistente ervaringen op verschillende apparaten aan hun klanten te bieden. </p> <p> Voor meer informatie over <span class="wintitle"> Apparaatcoop</span>, zie: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Samenvatting van apparaten</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Lidmaatschapseisen</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Apparaatgrafiek: Interne processen en uitvoer</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Grafiekopties</b>  voor apparatuur van derden (persoonlijk en huishoudelijk) </p> </td>
   <td colname="col2"> <p>Met deze opties kunt u fusieregels samenstellen op basis van apparaatgrafiektechnologie die door een externe leverancier wordt geleverd. Een apparaatgrafiek van derden biedt de volgende mogelijkheden: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistische en/of deterministische gegevens. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Gegevens per persoon of per huishouden. </li> 
     </ul> </p> <p>Als u deze opties wilt gebruiken, moet u een klant zijn van een apparaatgrafiek die al is geïntegreerd met <span class="keyword"> Audience Manager</span>. Neem contact op met uw accountmanager voor meer informatie of om aan de slag te gaan. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

De segmenten van het publiek die automatisch van andere [!DNL Experience Cloud] oplossingen werden gecreeerd, die op fusieregels buiten [!DNL Audience Manager] worden bepaald, worden duidelijk zoals het gebruiken van [!UICONTROL External Merge Policy]. Zie bijvoorbeeld [Poorten delen tussen Audience Manager en Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

