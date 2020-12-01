---
description: Antwoorden op veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken.
keywords: Organization ID
seo-description: Antwoorden op veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken.
seo-title: Veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken
solution: Audience Manager
title: Veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 86%

---


# Veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken {#profile-merge-rules-and-device-graph-faq}

Antwoorden op veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken.

<!-- profile-merge-faq.xml -->

## Basisbeginselen van apparaatgrafieken {#device-graph-basics}

**Wat is een apparaatgrafiek?**

Een apparaatgrafiek is een set id-toewijzingen waarmee groepen van anonieme apparaten worden gedefinieerd. De grafiek koppelt deze apparaten aan één persoon of één huishouden op basis van gemeenschappelijke elementen in de signalen die van elk apparaat worden verzameld. Deze signalen helpen apparaten te identificeren op individueel of huishoudelijk niveau.

 

**Wat is een externe apparaatgrafiek?**

Een externe apparaatgrafiek is een apparaatgrafiek in [!DNL Audience Manager] die niet uitsluitend op basis van uw eigen cross-device databronnen is gemaakt. Wanneer u bijvoorbeeld een [regel voor profielsamenvoeging ](../features/profile-merge-rules/merge-rules-start.md) maakt en de opties voor de [!UICONTROL Co-op Device Graph] of de externe apparaatgrafiek selecteert, werkt u met een externe apparaatgrafiek. Zie [Apparaatopties](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Wat zijn gangbare gebruiksscenario’s voor het gebruik van een externe apparaatgrafiek in een [!UICONTROL Profile Merge Rule]?**

Het belangrijkste doel van het gebruik van een apparaatgrafiek in een [!UICONTROL Profile Merge Rule] is het evalueren en kwalificeren van meerdere apparaten die tot één persoon of huishouden behoren voor een bepaald segment. Het segment zelf kan op meerdere manieren worden gebruikt: het kan bijvoorbeeld zijn getarget op een doelgroep van prospects met een advertentie die beschikbaar wordt gemaakt door een DSP, of de onsite ervaring van een klant personaliseren via een onsite personalisatieplatform. Zie [Gebruiksscenario’s voor externe apparaatgrafieken](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Biedt Audience Manager globale ondersteuning voor externe apparaatgrafieken?**

Nee. Externe apparaatgrafieken zijn alleen beschikbaar in de Verenigde Staten en Canada.

 

**Hoe vaak worden externe apparaatgrafieken in [!DNL Audience Manager] bijgewerkt?**

Eenmaal per week.

 

## Apparaatgrafieken en regels voor profielsamenvoeging {#device-graph-profile-merge-rules}

**Hoe wordt een apparaatgrafiek in [!DNL Audience Manager] gebruikt?**

In [!DNL Audience Manager] verschijnen apparaatgrafieken als configuratieopties wanneer u een [regel voor profielsamenvoeging maakt](../features/profile-merge-rules/merge-rules-start.md). Aan de hand van uw [!UICONTROL Profile Merge Rules] helpen deze apparaatgrafieken [!DNL Audience Manager] met het volgende:

* Meerdere apparaatprofielen samenvoegen. Hierdoor wordt één superset van eigenschappen gemaakt.
* De superset van eigenschappen evalueren voor segmentkwalificatie (in plaats van elk apparaatprofiel afzonderlijk te evalueren).
* Gekwalificeerde apparaten toevoegen aan beschikbare segmenten.

 

**Hoeveel [!UICONTROL Profile Merge Rules] kan ik maken?**

U kunt op dit moment maximaal vier [!UICONTROL Profile Merge Rules] maken. De vierde regel voor profielsamenvoeging ([!UICONTROL All Cross-Device Profiles]) is alleen beschikbaar voor klanten die de invoegtoepassing [!UICONTROL People-Based Destinations] aanschaffen.

 

**Hoeveel apparaatprofielen worden in [!DNL Audience Manager] samengevoegd en gelezen wanneer een apparaatgrafiek in een [!UICONTROL Profile Merge Rule] wordt gebruikt?**

Als Audience Manager een apparaat kwalificeert voor een segment met behulp van een [!UICONTROL Profile Merge Rule], leest en combineert Audience Manager het huidige apparaatprofiel en maximaal 99 andere apparaatprofielen die met elkaar zijn verbonden via de door u geselecteerde apparaatgrafiekoptie.

 

**Welke apparaten kwalificeren voor een segment bij gebruik van een apparaatgrafiek in een [!UICONTROL Profile Merge Rule]?**

De apparaten die [!DNL Audience Manager] samenvoegt en leest, zijn dezelfde apparaten die voor een segment worden gekwalificeerd.

 

**Waar kan [!DNL Audience Manager] segmenten naartoe verzenden die zijn gekwalificeerd door een [!UICONTROL Profile Merge Rule] die een apparaatgrafiek gebruikt?**

[!DNL Audience Manager] kan segmenten naar een bestemming verzenden in batchbestanden of in real time.

 

## Segmenten, apparaatgrafieken en regels voor profielsamenvoeging {#segments-device-graphs-rules}

**Hoe desegmenteert [!DNL Audience Manager] een apparaat wanneer het niet langer kwalificeert voor een segment met een [!UICONTROL Profile Merge Rule] die een apparaatgrafiek gebruikt?**

Audience Manager voegt maximaal 100 apparaten samen bij de evaluatie van segmenten met een [!UICONTROL Profile Merge Rule] die een apparaatgrafiek gebruikt. Als het desegmentatiesignaal wordt gegeven, worden het huidige apparaat en maximaal 99 andere apparaten uit het segment in de bestemming verwijderd. Raadpleeg [Regels voor profielsamenvoeging en processen voor apparaatdesegmentatie](../features/profile-merge-rules/merge-rule-unsegment.md) voor meer informatie over desegmentatie.

 

**Als een bestemming apparaten kan desegmenteren, worden apparaten dan verwijderd uit segmenten door [!UICONTROL Profile Merge Rules] die een apparaatgrafiek gebruiken?**

Ja. Zie de bovenstaande uitleg.

 

**Als ik een segment maak met een [!UICONTROL Profile Merge Rule] die een apparaatgrafiek gebruikt, en het segment zowel realtimedata als onboarded data gebruikt, wordt mijn segment dan bijgewerkt wanneer de onboarded data worden gewijzigd?**

Ja.

 

**Omvatten de schattingen van de segmentgrootte apparaten die voor een segment kwalificeren op basis van verbindingen geleverd door een [!UICONTROL Profile Merge Rule] die een apparaatgrafiekoptie gebruikt?**

Nee. Zie de definities voor [!UICONTROL Estimated Real-Time Population] en [!UICONTROL Estimated Total Population] in [Populatiedata van eigenschappen en segmenten in Segment Builder](https://docs.adobe.com/content/help/nl-NL/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**Omvat [!UICONTROL Addressable Audiences] apparaten die kwalificeren voor een segment op basis van verbindingen die worden verstrekt door een [!UICONTROL Profile Merge Rule] die een apparaatgrafiekoptie gebruikt?**

Ja.

 

**Als een segment een [!UICONTROL Profile Merge Rule] gebruikt met een [!UICONTROL No Cross-Device Profile], en de eigenschappen die apparaten voor het segment kwalificeren alleen in het cross-device profiel zijn opgeslagen, is de totale populatie van het segment dan 0?**

Ja. In Audience Manager worden voor de segmentevaluatie geen eigenschappen meegeteld die zijn opgeslagen in het cross-device profiel wanneer de regel voor profielsamenvoeging is ingesteld op [!UICONTROL No Cross-Device Profile].

 

## Eigenschapfrequentie, apparaatgrafieken en regels voor profielsamenvoeging {#trait-freq-device-rules}

**Hoe berekent [!DNL Audience Manager] de frequentie van eigenschappen met een [!UICONTROL Profile Merge Rule] die gebruikmaakt van een apparaatgrafiek?**

De eigenschapfrequentie wordt gedefinieerd door de som van het aantal kwalificaties voor een bepaalde eigenschap op meerdere apparaten. Bestudeer het volgende gebruiksscenario om dit beter te kunnen begrijpen.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gebruiksscenario </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Voorwaarden</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Apparaat A en apparaat B zijn gekoppeld door een apparaatgrafiek. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">U hebt een <span class="wintitle">regel voor profielsamenvoeging</span> die gebruikmaakt van een apparaatgrafiekoptie. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Eén segment (segment 1) bestaande uit één eigenschap (eigenschap 1), waarbij eigenschap 1 een frequentie van 8 heeft. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acties</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword">Audience Manager</span> leest de apparaatprofielen voor apparaat A en apparaat B en voegt deze samen.Hierna zien we het volgende: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Apparaat A kwalificeert drie keer voor eigenschap 1. Het heeft een frequentie van 3 voor eigenschap 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Apparaat B kwalificeert vijf keer voor eigenschap 1. Het heeft een frequentie van 5 voor eigenschap 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultaten</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> telt de frequentie voor eigenschap 1 en gebruikt 8 (3 + 5 = 8) om de segmentkwalificatie te bepalen. Apparaat A en apparaat B kwalificeren voor segment 1 omdat dit een frequentie van 8 heeft. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Rapporten, apparaatgrafieken en regels voor profielsamenvoeging {#reports-device-graphs-rules}

**Kan ik het aantal apparaten zien dat kan worden bereikt door een [!UICONTROL Profile Merge Rule] die gebruikmaakt van een apparaatgrafiek?**

Ja. Rapporten retourneren data op [!UICONTROL Profile Merge Rule]-niveau. Rapportdata worden dagelijks bijgewerkt. De data zijn gebaseerd op de apparaten die worden gedetecteerd in uw account, niet op de apparaten die zijn gekoppeld door een apparaatgrafiek. Zie [Cijfers rapporteren voor regels voor profielsamenvoeging](../features/profile-merge-rules/profile-link-metrics.md).

 

**Kan ik in *real time* het aantal apparaten zien dat kwalificeert voor een specifiek segment met [!UICONTROL Profile Merge Rules] die gebruikmaken van een apparaatgrafiek?**

Ja. Met de realtime-populatiecijfers worden segmentkwalificaties vastgelegd voor het huidige apparaat (het apparaat dat in real time wordt gezien) aan de hand van de profielen van alle apparaten die door een apparaatgrafiek zijn gekoppeld.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gebruiksscenario-element </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Voorwaarden</b> </p> </td> 
   <td colname="col2"> <p>Laten we uitgaan van het volgende: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 is gebaseerd op deze eigenschappen en kwalificatielogica: segment 1 = eigenschap A en eigenschap B en eigenschap C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 apparaatprofielen: apparaat 1 (huidige apparaat), apparaat 2 (apparaatgrafiek), apparaat 3 (apparaatgrafiek). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Acties</b> </p> </td> 
   <td colname="col2"> <p>Elke beschikbare eigenschap is gekoppeld aan een apparaat: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Apparaat 1: eigenschap A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Apparaat 2: eigenschap B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Apparaat 3: eigenschap C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultaten</b> </p> </td> 
   <td colname="col2"> <p>Gezien de voorgaande elementen is de totale populatie voor segment 1 één. </p> <p>In dit geval gebruikt de <span class="wintitle">regel voor profielsamenvoeging</span> alle apparaten en hun eigenschappen om de segmentkwalificatie te bepalen. Dit betekent dat apparaten 1, 2 en 3 kwalificeren voor segment 1, maar zoals hierboven vermeld, is alleen apparaat 1 inbegrepen in de realtime-segmentpopulatie. Dat komt hierdoor: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Apparaat 1 is het huidige apparaat dat in real time communiceert met de <span class="wintitle">servers voor dataverzameling</span> (<span class="wintitle">DCS</span>) van Audience Manager. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Apparaten 2 en 3 zijn aan apparaat 1 gekoppeld door een apparaatgrafiek, maar communiceren niet met de DCS op hetzelfde moment als apparaat 1. </li> 
     </ul> </p> <p>Daardoor worden apparaten 2 en 3 niet opgenomen in de cijfers van de realtime-segmentpopulatie. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Kan ik het totale aantal apparaten zien dat kwalificeert voor een specifiek segment met een [!UICONTROL Profile Merge Rule] die gebruikmaakt van een apparaatgrafiek?**

Ja. Het cijfer van de totale segmentpopulatie omvat de extra apparaten die kwalificeren voor een segment op basis van de verbindingen van een apparaatgrafiek.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gebruiksscenario-element </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Voorwaarden</b> </p> </td> 
   <td colname="col2"> <p>Laten we uitgaan van het volgende: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 is gebaseerd op deze eigenschappen en kwalificatielogica: segment 1 = eigenschap A en eigenschap B en eigenschap C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 apparaatprofielen: apparaat 1 (huidige apparaat), apparaat 2 (apparaatgrafiek), apparaat 3 (apparaatgrafiek). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Koppelingen</b> </p> </td> 
   <td colname="col2"> <p>Elke beschikbare eigenschap is gekoppeld aan een apparaat: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Apparaat 1: eigenschap A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Apparaat 2: eigenschap B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Apparaat 3: eigenschap C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultaten</b> </p> </td> 
   <td colname="col2"> <p>Gezien de voorgaande elementen is de totale populatie voor segment 1 drie (3). </p> <p>In dit geval gebruikt de <span class="wintitle">regel voor profielsamenvoeging</span> alle apparaten en hun eigenschappen om de segmentkwalificatie te bepalen. Dit betekent dat apparaten 1, 2 en 3 kwalificeren voor segment 1 en dat ze alle drie zijn opgenomen in de totale populatie. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Zijn apparaten die kwalificeren voor een segment met een [!UICONTROL Profile Merge Rule] die gebruikmaakt van een apparaatgrafiek, opgenomen in de [!UICONTROL Interactive] rapporten, [!UICONTROL Overlap] rapporten en [!UICONTROL Audience Optimization]-rapporten?**

Nee.

**Waarom zie ik geen segmentpopulatie voor segmentexport naar Adobe Campaign na 16 maart 2020?**

Eind 2019 hebben we een aantal verbeteringen in de regels voor het samenvoegen van profielen gepubliceerd om de nauwkeurigheid van batchbestanden die met id&#39;s voor meerdere apparaten zijn gegenereerd, te verbeteren. Deze verbeteringen worden strikt nageleefd in uw Audience Manager-exemplaar vanaf maandag 16 maart 2020. Dientengevolge, zullen de segmenten die aan een bestemming worden in kaart gebracht gebruikend cross-device IDs ophouden producerend de uitvoer in sommige configuraties van de Regels van de Fusie van het Profiel.

Om de correcte integratie tussen uw instantie van de Audience Manager en bestemmingen te verzekeren gebruikend dwars-apparaat IDs, zoals Adobe Campaign, zorg ervoor u aan de volgende vereisten voldoet:

1. Controleer de regel voor het samenvoegen van profielen die wordt gebruikt door de segmenten die zijn toegewezen aan de bestemming van de door Adobe Campaign aangegeven id. De regel voor het samenvoegen van profielen moet de optie [!UICONTROL Last Authenticated Profile] gebruiken, zodat alle geverifieerde profielen kunnen worden opgenomen in de exportbewerking. Als de regel voor het samenvoegen van profielen een andere optie gebruikt, schakelt u deze over naar [!UICONTROL Last Authenticated Profile].
2. Selecteer de gegevensbron voor de Adobe Campaign-declaratie-id in de instellingen voor de regel voor het samenvoegen van profielen.

>[!NOTE]
>
> Wij hebben de grens van de Regel van de Fusie van het Profiel met 1 voor klanten verhoogd die deze situatie onder ogen zien, zodat u een specifieke Regel van de Fusie van het Profiel voor de segmenten kunt tot stand brengen die aan de Adobe Campaign Verklaarde bestemming van identiteitskaart worden in kaart gebracht, zonder de Regels van de Fusie van het Profiel voor andere gebruiksgevallen te veranderen.

>[!MORELIKETHIS]
>
>* [Profielkoppeling](../features/profile-merge-rules/profile-link-use-case.md)

