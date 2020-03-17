---
description: Antwoorden op veelgestelde vragen over de samenvoegregel van het profiel en de apparaatgrafiek.
keywords: Organization ID
seo-description: Antwoorden op veelgestelde vragen over de samenvoegregel van het profiel en de apparaatgrafiek.
seo-title: Veelgestelde vragen over regels voor samenvoegen van profielen en apparaatgrafiek
solution: Audience Manager
title: Veelgestelde vragen over regels voor samenvoegen van profielen en apparaatgrafiek
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Veelgestelde vragen over regels voor samenvoegen van profielen en apparaatgrafiek{#profile-merge-rules-and-device-graph-faq}

Antwoorden op veelgestelde vragen over de samenvoegregel van het profiel en de apparaatgrafiek.

<!-- profile-merge-faq.xml -->

## Grondbeginselen van apparaatgrafiek {#device-graph-basics}

**Wat is een apparaatgrafiek?**

Een apparaatgrafiek is een set id-toewijzingen die groepen anonieme apparaten definieert. Het associeert deze apparaten aan een persoon of een huishouden die op gemeenschappelijke elementen in de signalen wordt gebaseerd die van elk apparaat worden verzameld. Deze signalen helpen apparaten op individueel of huiselijk niveau identificeren.

 

**Wat is een externe apparaatgrafiek?**

Een externe apparaatgrafiek is een apparaatgrafiek in [!DNL Audience Manager] die niet uitsluitend op basis van uw eigen apparaatgegevensbronnen is gemaakt. Wanneer u bijvoorbeeld een regel voor het samenvoegen van [profielen maakt en de grafiekopties voor apparaten](../features/profile-merge-rules/merge-rules-start.md) [!UICONTROL Co-op Device Graph] of apparaten van derden kiest, werkt u met een externe apparaatgrafiek. Zie [Apparaatopties](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Wat zijn enkele gangbare gebruiksgevallen voor het gebruik van een externe apparaatgrafiek in een[!UICONTROL Profile Merge Rule]grafiek?**

Het belangrijkste doel van het gebruik van een apparaatgrafiek in een [!UICONTROL Profile Merge Rule] is het evalueren en kwalificeren van meerdere apparaten die tot één persoon of huishouden behoren voor een bepaald segment. Het segment zelf kan veelvoudige toepassingen bijvoorbeeld hebben, richtend een publiek van vooruitzichten met een advertentie die door DSP wordt gediend of personaliserend de ervaring van een klant op-plaats via een onsite verpersoonlijkingsplatform. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Biedt Audience Manager algemene ondersteuning voor externe apparaatgrafieken?**

Nee. Externe apparaatgrafieken zijn alleen beschikbaar in de Verenigde Staten en Canada.

 

**Hoe vaak worden de externe gegevens van de apparaatgrafiek[!DNL Audience Manager]bijgewerkt?**

Eenmaal per week.

 

## Apparaatgrafieken en regels voor het samenvoegen van profielen {#device-graph-profile-merge-rules}

**Hoe wordt een apparaatgrafiek[!DNL Audience Manager]gebruikt?**

In [!DNL Audience Manager], verschijnen de apparatengrafieken als configuratieopties wanneer u een Regel [van de Fusie van het Profiel](../features/profile-merge-rules/merge-rules-start.md)creeert. Aan de hand van deze apparaatgrafieken [!UICONTROL Profile Merge Rules]kunt u [!DNL Audience Manager]het volgende doen:

* Voeg meerdere apparaatprofielen samen. Hierdoor wordt één superset van kenmerken gemaakt.
* Evalueer de eigenschap superset voor segmentkwalificatie (eerder dan evaluerend elk apparatenprofiel individueel).
* Voeg gekwalificeerde apparaten toe aan beschikbare segmenten.

 

**Hoeveel[!UICONTROL Profile Merge Rules]kan ik maken?**

U kunt op dit moment maximaal 4 [!UICONTROL Profile Merge Rules]maken. De vierde regel voor het samenvoegen van profielen ([!UICONTROL All Cross-Device Profiles]) is alleen beschikbaar voor klanten die de [!UICONTROL People-Based Destinations] invoegtoepassing aanschaffen.

 

**Hoeveel apparaatprofielen worden[!DNL Audience Manager]samengevoegd en gelezen wanneer een apparaatgrafiek in een[!UICONTROL Profile Merge Rule]afbeelding wordt gebruikt?**

Als u een apparaat kwalificeert voor een segment met behulp van een [!UICONTROL Profile Merge Rule]Audience Manager, wordt het huidige apparaatprofiel en maximaal 99 andere aanvullende apparaatprofielen samengevoegd en gelezen die zijn gekoppeld door de geselecteerde grafiekoptie van het apparaat.

 

**Welke apparaten kwalificeren voor een segment wanneer het gebruiken van een apparatengrafiek in een[!UICONTROL Profile Merge Rule]?**

De apparaten [!DNL Audience Manager] voegen samen en lezen zijn de zelfde apparaten die voor een segment worden gekwalificeerd.

 

**Waar kan segmenten[!DNL Audience Manager]verzenden die door een[!UICONTROL Profile Merge Rule]die apparatengrafiek zijn gekwalificeerd?**

[!DNL Audience Manager] U kunt segmenten naar een doel verzenden in batchbestanden of in realtime.

 

## Segmenten, apparaatgrafieken en regels voor het samenvoegen van profielen {#segments-device-graphs-rules}

**Hoe maakt u het segment van een apparaat ongedaan wanneer het niet meer gekwalificeerd is voor een segment met een[!DNL Audience Manager][!UICONTROL Profile Merge Rule]apparaat dat een apparaatgrafiek gebruikt?**

Audience Manager voegt maximaal 100 apparaten samen wanneer u segmenten evalueert met een grafiek [!UICONTROL Profile Merge Rule] die een apparaatgrafiek gebruikt. Als het unsegment signaal wordt uitgegeven, zullen het huidige apparaat en tot 99 extra apparaten uit het segment in de bestemming worden verwijderd. Voor meer informatie over unsegmentation, zie de Regels van de Fusie van het [Profiel en de Processen van de Apparaat Un-Segmentatie](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**Als een bestemming apparaten kan ontsegmenteren, zullen de apparaten uit segmenten door[!UICONTROL Profile Merge Rules]die een apparatengrafiek worden verwijderd?**

Ja. Zie de bovenstaande uitleg.

 

**Als ik een segment met een segment bouwt[!UICONTROL Profile Merge Rule]die een apparatengrafiek gebruikt en het segment zowel gegevens in real time als gegevens op-board gebruikt, zal mijn segment worden bijgewerkt aangezien de gegevens op-boted veranderen?**

Ja.

 

**Omvatten de de schattingen van de segmentgrootte apparaten die voor een segment kwalificeren dat op verbindingen wordt gebaseerd die door een[!UICONTROL Profile Merge Rule]die een optie van de apparatengrafiek wordt verstrekt?**

Nee. Zie de definities voor [!UICONTROL Estimated Real-Time Population] en [!UICONTROL Estimated Total Population] in de Gegevens van de Bevolking van het [Spoor en van het Segment in de Bouwer](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html)van het Segment.

 

**Omvat[!UICONTROL Addressable Audiences]apparaten die voor een segment kwalificeren dat op verbindingen wordt gebaseerd die door een[!UICONTROL Profile Merge Rule]die een optie van de apparatengrafiek wordt verstrekt?**

Ja.

 

**Als een segment[!UICONTROL Profile Merge Rule]met gebruikt[!UICONTROL No Cross-Device Profile]en de eigenschappen die apparaten voor het segment kwalificeren slechts op het dwars-apparatenprofiel worden opgeslagen, zal de totale bevolking van het segment 0 zijn?**

Ja. De Manager van de publiek zal niet de eigenschappen tellen die op het dwars-apparatenprofiel in de segmentevaluatie worden opgeslagen wanneer de Regel van de Fusie van het Profiel aan [!UICONTROL No Cross-Device Profile]. wordt geplaatst.

 

## Trait Frequency, Device Graphs en Profile Merge Rules {#trait-freq-device-rules}

**Hoe[!DNL Audience Manager]berekent u de frequentie van de eigenschap met een[!UICONTROL Profile Merge Rule]apparaatgrafiek?**

De vakfrequentie wordt gedefinieerd door de som van het aantal kwalificaties voor een specifiek kenmerk voor meerdere apparaten. Om u dit te helpen begrijpen, neem een blik bij het volgende gebruiksgeval.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hoofdletters gebruiken </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Voorwaarden</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Apparaat A en Apparaat B worden verbonden door een apparatengrafiek. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">U hebt een <span class="wintitle"> regel</span> voor het samenvoegen van profielen waarin een optie voor apparaatgrafieken wordt gebruikt. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Eén segment (segment 1) bestaande uit één enkel kenmerk (Trait 1), waarbij Trait 1 een frequentie van 8 heeft. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Handelingen</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> leest de apparaatprofielen voor Device A en Device B en voegt deze samen. Hieruit zien we het volgende: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Apparaat A heeft drie keer gekwalificeerd voor Trait. Het heeft een frequentie van 3 voor Trait 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Apparaat B heeft vijf keer gekwalificeerd voor Trait. Het heeft een frequentie van 5 voor Trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultaten</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> somt de frequentie voor Trait 1 op en gebruikt 8 (3 + 5 = 8) om segmentkwalificatie te bepalen. Apparaat A en Apparaat B komen in aanmerking voor Segment 1 omdat het een frequentie van 8 heeft. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Rapporten, Apparaatgrafieken en Regels voor het samenvoegen van profielen {#reports-device-graphs-rules}

**Kan ik het aantal apparaten zien dat kan worden bereikt door een[!UICONTROL Profile Merge Rule]apparaatgrafiek?**

Ja. Hiermee worden gegevens op [!UICONTROL Profile Merge Rule] niveau geretourneerd. De rapportgegevens worden dagelijks bijgewerkt. De gegevens zijn gebaseerd op de apparaten in uw account, niet op de apparaten die zijn gekoppeld door een apparaatgrafiek. Zie Metriek [rapporteren voor regels](../features/profile-merge-rules/profile-link-metrics.md)voor het samenvoegen van profielen.

 

**Kan ik het aantal apparaten zien die voor een specifiek segment in *real time*met[!UICONTROL Profile Merge Rules]die een apparatengrafiek worden gekwalificeerd?**

Ja. Met de metrische gegevens voor realtime-populaties worden segmentkwalificaties voor het huidige apparaat (het apparaat dat in real-time wordt gezien) vastgelegd met behulp van de profielen van alle apparaten die zijn gekoppeld door een apparaatgrafiek.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hoofdelement gebruiken </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Voorwaarden</b> </p> </td> 
   <td colname="col2"> <p>Veronderstel wij hebben: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 is gebaseerd op deze kenmerken en kwalificatielogica: Segment 1 = Trait A en Trait B en Trait C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 apparaatprofielen: Device 1 (huidige apparaat), Device 2 (apparaatgrafiek), Device 3 (apparaatgrafiek). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Handelingen</b> </p> </td> 
   <td colname="col2"> <p>Elk beschikbaar kenmerk is gekoppeld aan een apparaat: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Apparaat 1: Trait A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Apparaat 2: Vak B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Apparaat 3: Vak C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultaten</b> </p> </td> 
   <td colname="col2"> <p>Gezien de voorgaande elementen is de totale populatie voor segment 1 één. </p> <p>In dit geval, gebruikt de Regel <span class="wintitle"> van de Fusie van het</span> Profiel alle apparaten en hun eigenschappen om segmentkwalificatie te beslissen. Dit betekent Apparaten 1, 2, en 3 kwalificeren voor Segment 1, maar, zoals hierboven vermeld, is slechts Apparaat 1 inbegrepen in de segmentpopulatie in real time. Dit komt omdat: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Apparaat 1 is het huidige apparaat dat met de Servers <span class="wintitle"> van de Inzameling van Gegevens van de Manager van de Auditie (</span> DCS<span class="wintitle"></span>) in real time in wisselwerking staat. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Apparaten 2 en 3 worden aan Apparaat 1 geassocieerd door een apparatengrafiek maar zij communiceren niet met DCS tezelfdertijd zoals Apparaat 1. </li> 
     </ul> </p> <p>Dientengevolge, zijn de Apparaten 2 en 3 niet inbegrepen in de metrische populatie in real time. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Kan ik het totale aantal apparaten zien die voor een specifiek segment met een[!UICONTROL Profile Merge Rule]die apparatengrafiek worden gekwalificeerd?**

Ja. De totale metrische segmentpopulatie omvat de extra apparaten die voor een segment gekwalificeerd hebben dat op de verbindingen van een apparatengrafiek wordt gebaseerd.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hoofdelement gebruiken </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Voorwaarden</b> </p> </td> 
   <td colname="col2"> <p>Veronderstel wij hebben: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 is gebaseerd op deze kenmerken en kwalificatielogica: Segment 1 = Trait A en Trait B en Trait C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 apparaatprofielen: Device 1 (huidige apparaat), Device 2 (apparaatgrafiek), Device 3 (apparaatgrafiek). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associaties</b> </p> </td> 
   <td colname="col2"> <p>Elk beschikbaar kenmerk is gekoppeld aan een apparaat: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Apparaat 1: Trait A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Apparaat 2: Vak B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Apparaat 3: Vak C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultaten</b> </p> </td> 
   <td colname="col2"> <p>Gezien de voorgaande elementen bedraagt de totale populatie voor segment 1 drie (3). </p> <p>In dit geval, gebruikt de Regel <span class="wintitle"> van de Fusie van het</span> Profiel alle apparaten en hun eigenschappen om segmentkwalificatie te beslissen. Dit betekent Apparaten 1, 2, en 3 kwalificeren voor Segment 1 en alle drie zijn inbegrepen in de totale bevolking. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Zijn de apparaten die voor een segment met een segment kwalificeren[!UICONTROL Profile Merge Rule]die een apparatengrafiek gebruikt inbegrepen in de[!UICONTROL Interactive]rapporten,[!UICONTROL Overlap]rapporten en[!UICONTROL Audience Optimization]rapporten?**

Nee.

>[!MORELIKETHIS]
>
>* [Profielkoppeling](../features/profile-merge-rules/profile-link-use-case.md)

