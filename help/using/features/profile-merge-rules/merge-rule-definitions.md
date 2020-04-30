---
description: Met de opties voor samenvoegregels kunt u het type gegevens bepalen dat Audience Manager gebruikt voor segmentatie. Een samenvoegregel kan apparaatprofielen bevatten die zijn toegewezen door de apparaatgrafiek van de profielkoppeling, de Adobe Experience Cloud Device Co-op en/of andere apparaatgrafiekproviders van derden die zijn geïntegreerd met Audience Manager. U kunt maximaal vier regels voor het samenvoegen van profielen maken.
seo-description: Met de opties voor samenvoegregels kunt u het type gegevens bepalen dat Audience Manager gebruikt voor segmentatie. Een samenvoegregel kan apparaatprofielen bevatten die zijn toegewezen door de apparaatgrafiek van de profielkoppeling, de Adobe Experience Cloud Device Co-op en/of andere apparaatgrafiekproviders van derden die zijn geïntegreerd met Audience Manager. U kunt maximaal vier regels voor het samenvoegen van profielen maken.
seo-title: Opties voor regel voor samenvoegen van profiel gedefinieerd
solution: Audience Manager
title: Opties voor regel voor samenvoegen van profiel gedefinieerd
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Opties voor regels voor het samenvoegen van profielen gedefinieerd {#profile-merge-rule-options-defined}

Met de opties voor samenvoegregels kunt u het type gegevens bepalen dat Audience Manager gebruikt voor segmentatie. Een samenvoegregel kan apparaatprofielen bevatten die zijn toegewezen door de [!UICONTROL Profile Link] apparaatgrafiek, de leveranciers van apparaatgrafieken van derden [!UICONTROL Adobe Experience Cloud Device Co-op]en/of andere leveranciers die zijn geïntegreerd met Audience Manager. U kunt maximaal 4 maken [!UICONTROL Profile Merge Rules]. De vierde optie [!UICONTROL Profile Merge Rule] is uitsluitend beschikbaar voor klanten die de [!UICONTROL People-Based Destinations] invoegtoepassing hebben aangeschaft.

U maakt een definitie [!UICONTROL Profile Merge Rule] door een selectie te maken uit de opties die hieronder worden beschreven, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Overzicht van opties voor samenvoegingsregels voor profielen {#overview}

De Regels van de Fusie van het profiel staan voor een aantal regelcombinaties toe, elk gericht op specifieke gebruiksgevallen. Zie de tabel hieronder voor meer informatie over het gebruik van elke regelcombinatie.

| Optie voor meerdere apparaten | Apparaatoptie | Beschikbaarheid | Type evaluatie | Ondersteuning voor publiek Lab | Gevallen gebruiken |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| Geen profiel voor meerdere apparaten | Apparaatprofiel | Alle klanten | Realtime en batch | Ja | [Apparaatgericht](merge-rule-targeting-options.md#device-personalization) |
| Geen profiel voor meerdere apparaten | Grafiek extern apparaat (inclusief coopapparaatgrafiek) | Alle klanten | Realtime en batch | Nee | [Uitgebreide doelapparaten](external-graph-use-cases.md#audience-expansion) |
| Huidige geverifieerde profielen | Geen apparaatprofiel | Alle klanten | Alleen in realtime | Nee | [Gedeelde apparaatdoelen](merge-rule-targeting-options.md#target-shared-devices) |
| Laatst geverifieerde profielen | Apparaatprofiel | Alle klanten | Realtime en batch | Ja | [Online/offline gericht](merge-rule-targeting-options.md#device-household-targeting) |
| Laatst geverifieerde profielen | Apparaatgrafiek profielkoppeling | Alle klanten | Realtime en batch | Ja | [Toewijzing op meerdere apparaten](profile-link-use-case.md#cross-device-personalization) |
| Laatst geverifieerde profielen | Grafiek extern apparaat (inclusief coopapparaatgrafiek) | Alle klanten | Realtime en batch | Nee | [Geavanceerde interDevice-doelen](external-graph-use-cases.md#advanced-graph-expansion) |
| Alle profielen voor meerdere apparaten | N.v.t. | Exclusief voor [klanten met een persoonlijke bestemming](../destinations/people-based-destinations-overview.md) | Alleen batch | Nee | [Doelen voor op mensen gebaseerde bestemmingen](merge-rule-targeting-options.md#all-cross-device) |

## Evaluatie van segment van samenvoegingsregel {#segment-evaluation}

Afhankelijk van uw [!UICONTROL Profile Merge Rules] configuratie, kan de Manager van de Publiek de segmentevaluatie in real time, in partij, of allebei uitvoeren.

* De evaluatie van het segment in real time vereist de bezoekers [!DNL DCS] om tot uw digitale eigenschappen in real time toegang te hebben, om voor het segment te kwalificeren.
* De segmentbeoordeling van de partij wordt uitgevoerd tegen eerder gekwalificeerde eigenschappen.
* [!UICONTROL Profile Merge Rules] die zowel de evaluatie in real time als van het partijsegment steunen combineren de activiteit van de bezoeker in real time met eerder gekwalificeerde eigenschappen.

## Rapportvertraging voor regels voor samenvoegen van profielen {#reporting-latency}

De evaluatie van het segment in real time weerspiegelt onmiddellijk in de [!UICONTROL Profile Merge Rules] rapporten.

De de segmentevaluatie van de partij kan tot 24 uren vergen om in de rapporten [van de Regels van de Fusie van het](profile-link-metrics.md)Profiel te weerspiegelen.

## Opties voor meerdere apparaten {#auth-options}

Hiermee [!UICONTROL Cross-Device Options] kunt u geverifieerde en niet-geverifieerde gebruikers selecteren en hun apparaatprofiel gebruiken voor segmentatie. Met deze opties kunt u specifieke gebruikers op een gedeeld apparaat identificeren en bereiken. Voor meer informatie over anonieme en voor authentiek verklaarde gebruikers, zie de Staten van de Authentificatie van de [Bezoeker in de Manager](../../reference/visitor-authentication-states.md)van het Publiek.

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
   <td colname="col2"> <p>Hiermee geeft u aan dat <span class="keyword"> Audience Manager</span> geen gegevens mag gebruiken die zijn verzameld bij geverifieerde gebruikers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Huidige geverifieerde profielen</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee geeft u <span class="keyword"> Audience Manager</span> de opdracht gegevens te lezen en te schrijven naar het geverifieerde profiel als een bezoeker zich heeft aangemeld bij uw site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Laatst geverifieerde profielen</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt de Manager <span class="keyword"> van het</span> Publiek om gegevens van het voor authentiek verklaarde profiel van de gebruiker te lezen die het laatst op het apparaat het programma opende. </p> <p>Als deze optie is ingeschakeld, worden door Audience Manager <span class="keyword"></span> geen nieuwe gegevens over de eigenschap naar het geverifieerde profiel geschreven als de gebruiker anoniem is. Bij verificatie worden nieuwe doelgegevens naar het geverifieerde profiel van de gebruiker geschreven. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle profielen voor meerdere apparaten</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee geeft u Audience Manager de opdracht om gegevens van alle apparaatprofielen te lezen, ongeacht de verificatiestatus. Deze optie is alleen beschikbaar voor klanten van Audience Manager die de invoegtoepassing voor op mensen gebaseerde doelen hebben aangeschaft.</p> </td>
  </tr>
 </tbody>
</table>

## Opties profiel voor meerdere apparaten {#profile-options}

De [!UICONTROL Cross-Device Profile Options] gegevensbronnen op alle apparaten worden weergegeven. Bij deze opties worden de namen gebruikt die u hebt opgegeven toen u een gegevensbron voor meerdere apparaten hebt gemaakt (zie [Apparaatgegevensbron](merge-rules-start.md#create-data-source)maken). U kunt maximaal drie apparaatgegevensbronnen selecteren die u met elke profielregel wilt gebruiken. De [!UICONTROL Authenticated Profile Options] opties zijn beschikbaar wanneer u kiest **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]**.

## Apparaatopties {#device-options}

Hiermee [!UICONTROL Device Options] kunt u het type *`device profile`* selecteren dat door een [!UICONTROL Profile Merge Rule]. Een apparaatprofiel wordt samengesteld op basis van kenmerken die zijn verzameld op basis van anonieme browseractiviteiten. Een regel voor het samenvoegen van profielen bevat minimaal een geverifieerde optie en een apparaatoptie.

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
   <td colname="col2"> <p>Vertelt de Manager <span class="keyword"> van het</span> Publiek om de eigenschappen in het anonieme profiel voor segmentatie niet te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatprofiel</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt de Manager <span class="keyword"> van het</span> Publiek om het anonieme apparatenprofiel voor segmentatie te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatgrafiek profielkoppeling</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee geeft u aan <span class="keyword"> Audience Manager</span> de profielen van het huidige apparaat en maximaal 100 andere apparaten te lezen waaruit de gebruiker is geverifieerd. Deze apparaatgrafiek is gebaseerd op uw eigen gegevens van de eerste partij in <span class="keyword"> Audience Manager</span>. Dit is ideaal voor klanten die een hoog verificatieniveau hebben voor hun digitale eigenschappen. De het apparatengrafiek van de Verbinding <span class="wintitle"></span> van het Profiel wordt bijgewerkt in echt - tijd. Deze optie is beschikbaar wanneer u <b><span class="uicontrol"> Huidig geverifieerd profiel</span></b> of <b><span class="uicontrol"> Laatst geverifieerd profiel</span></b>selecteert. Als u deze optie gebruikt, kunt u slechts één geverifieerd profiel kiezen (<span class="keyword"> Audience Manager</span> grijst de andere profielen automatisch uit). Zie ook <a href="profile-link-use-case.md"> Kwesties voor grafiekgebruik van profielkoppeling</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Afbeelding van apparaat voor coop</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee geeft u aan <span class="keyword"> Audience Manager</span> de profielen van het huidige apparaat en maximaal 100 andere apparaten te lezen aan de hand van de koppelingen die worden geleverd door de <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p>De <span class="keyword"> Device Co-op</span> is een digitale coöperatie waar deelnemende klanten koppelingsinformatie over apparaten delen. De <span class="keyword"> -op-knop</span> van het apparaat verwerkt deze gegevens in een <span class="term"> apparaatgrafiek</span>. Een apparaatgrafiek koppelt apparaten aan elkaar in apparaatclusters. Deze verbindingen worden gebouwd van <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> probabilistische en deterministische gegevens</a>. De clusters vertegenwoordigen een groep apparaten die door een onbekende persoon worden gebruikt. De <span class="keyword"> Device Co-op</span> deelt deze clusters onder zijn leden, wat hen helpt waardevolle en verenigbare overkoepelende ervaringen aan hun klanten leveren. </p> <p> Raadpleeg de volgende bronnen voor meer informatie over de <span class="wintitle"> apparaatcoop</span>: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Samenvatting van apparaten</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Lidmaatschapseisen</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Apparaatgrafiek: Interne processen en uitvoer</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager en External Device Graphs</a> (PDF-download). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Grafiekopties</b> voor apparatuur van derden (persoonlijk en huishoudelijk) </p> </td>
   <td colname="col2"> <p>Met deze opties kunt u fusieregels samenstellen op basis van apparaatgrafiektechnologie die door een externe leverancier wordt geleverd. Een apparaatgrafiek van derden biedt de volgende mogelijkheden: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistische en/of deterministische gegevens. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Gegevens per persoon of per huishouden. </li> 
     </ul> </p> <p>Als u deze opties wilt gebruiken, moet u een klant zijn van een apparaatgrafiek die al is geïntegreerd met <span class="keyword"> Audience Manager</span>. Neem contact op met uw accountmanager voor meer informatie of om aan de slag te gaan. </p> </td>
  </tr>
 </tbody>
</table>

<!--Victor/Vlad: In the above table, you link to a .pdf file on marketing.adobe.com. Can you move that PDF into Git and link to it? This pdf might get blown away with the marketing.adobe.com decommission. -Bob-->

## Extern samenvoegingsbeleid {#external-merge-policies}

De segmenten van het publiek die automatisch van andere oplossingen van de Wolk van de Ervaring werden gecreeerd, die op fusieregels worden gebaseerd buiten de Manager van het Publiek worden bepaald, worden duidelijk zoals het gebruiken van [!UICONTROL External Merge Policy]. Zie bijvoorbeeld [Poortdeling tussen Audience Manager en Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

