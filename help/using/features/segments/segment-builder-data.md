---
description: Voeg en verwijder eigenschappen in de Bouwer van het Segment toe om daadwerkelijke vakpopulaties samen met daadwerkelijke en geschatte segmentpopulatiegegevens te zien. Met de geschatte bevolkingsgrootte kunt u het juiste segment voor uw campagne maken.
seo-description: Voeg en verwijder eigenschappen in de Bouwer van het Segment toe om daadwerkelijke vakpopulaties samen met daadwerkelijke en geschatte segmentpopulatiegegevens te zien. Met de geschatte bevolkingsgrootte kunt u het juiste segment voor uw campagne maken.
seo-title: Populatiedata van eigenschappen en segmenten in Segment Builder
solution: Audience Manager
title: Populatiedata van eigenschappen en segmenten in Segment Builder
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: 'Segmenten '
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1251'
ht-degree: 2%

---

# [!UICONTROL Trait] en  [!UICONTROL Segment] populatiegegevens in  [!UICONTROL Segment Builder] {#trait-and-segment-population-data-in-segment-builder}

Voeg [!UICONTROL traits] toe en verwijder  in [!UICONTROL Segment Builder] om werkelijke [!UICONTROL trait] populaties samen met werkelijke en geschatte segmentpopulatiegegevens te zien. Met de geschatte bevolkingsgrootte kunt u het juiste segment voor uw campagne maken.

## [!UICONTROL Trait] Populatiegegevens  {#trait-population-data}

[!UICONTROL Segment Builder] toont u  [!UICONTROL Total Trait Population] voor de laatste dag wanneer u een segment  [!UICONTROL trait] aan een segment toevoegt. Deze gegevens worden weergegeven in het blauwe veld rondom de geselecteerde [!UICONTROL trait] in de sectie [!UICONTROL Basic View].

![](assets/trait-size.png)

In de volgende tabel worden de maatstaven voor de doelpopulatie gedefinieerd:


| Metrisch | Beschrijving |
|---------|----------|
| [!UICONTROL Total Trait Population] | Het aantal unieke id&#39;s met de geselecteerde eigenschap in hun profiel. |


## Reële en geschatte segmentpopulaties berekenen {#calculating-real-estimated-populations}

Wanneer u een nieuw segment creeert, of een bestaand segment verandert, neemt de Audience Manager tot 24 uur aan vertoningsresultaten voor daadwerkelijke real time en totale segmentpopulaties.

Nochtans, kan de Audience Manager onmiddellijk de grootte in real time en de totale bevolking van uw segment schatten. Deze schattingen zijn gebaseerd op gesamplede historische gegevens en retourresultaten met een betrouwbaarheidsinterval van 95%.

![](assets/confidence-interval.png)

In [!UICONTROL Segment Builder] geeft een blauwe balk op de geschatte bevolkingsgrafieken de mogelijke boven- en onderbereiken voor de segmentgrootte aan. Hoewel de prestaties in het verleden geen garantie bieden voor toekomstige resultaten, kunnen de geschatte gegevens u helpen de potentiële grootte van een nieuw of bewerkt segment te begrijpen.

## Overzicht van segmentpopulatiegegevens {#segment-populations}

[!UICONTROL Segment Builder] toont u de gegevens van de segmentpopulatie aangezien u creeert en segmenten uitgeeft.

* Voor geschatte segmentpopulatiegegevens (real-time en totaal) werkt [!UICONTROL Segment Builder] de grafieken niet automatisch bij aangezien u eigenschappen in een segment toevoegt of verwijdert. Klik op **[!UICONTROL Calculate Estimates]** om de geschatte bevolkingsaantallen te zien (of te vernieuwen).

* Voor daadwerkelijke (echte) gegevens van de segmentpopulatie (in real time en totaal), werkt [!UICONTROL Segment Builder] automatisch de segmentgrafiek bij wanneer u een bestaand segment laadt. Voor nieuwe segmenten, of wanneer u nieuwe eigenschappen aan een bestaand segment toevoegt, worden de daadwerkelijke populatiegegevens niet bijgewerkt tot 24 uur nadat het segment wordt gecreeerd.

![](assets/segment-data.png)

Zie de definities hieronder voor meer informatie over geschatte en werkelijke gegevens over de segmentpopulatie.

## Geschatte populatiegegevens van segmenten gedefinieerd {#estimated-segment-population}

In de volgende tabel worden de geschatte bevolkingscijfers weergegeven.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschatte Real-Time Bevolking (potentieel)  </span> </p> </td> 
   <td colname="col2"> <p>Het geschatte aantal unieke bezoekers dat in real time voor de gespecificeerde tijdwaaier werd gezien en die voor het segment werden gekwalificeerd op het ogenblik dat zij door Audience Manager werden gezien. </p> <p>In <span class="wintitle"> de Bouwer van het Segment</span>, kunnen de laatste 30 dagpopulaties voor eigenschappen (<span class="wintitle"> Totale Bevolking van het Beetje</span>), voor eigenschappen en segmenten verschillend zijn die in real time worden geëvalueerd. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">Voor eigenschappen, de laatste metrische tellingen van 30 dagen het aantal unieke gebruikers die voor dat bezit tijdens de laatste 30 dagen kwalificeerden. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">Voor segmenten die in real time worden geëvalueerd, tellen de laatste metrische tellingen van 30 dagen het aantal gebruikers die voor een eigenschap (in dat segment) op wat punt in het verleden hebben gekwalificeerd en opnieuw door Audience Manager binnen de laatste 30 dagen gezien. Stel dat u een gebruiker hebt die 60 dagen geleden voor een eigenschap in aanmerking kwam en tien dagen geleden opnieuw werd gezien. In de gegevens wordt deze gebruiker niet toegevoegd aan de telling van het kenmerk omdat hij meer dan 30 dagen geleden voor het eerst in aanmerking kwam voor de eigenschap. Nochtans, zullen zij in het laatste aantal van 30 dagen voor de segmenten worden omvat die in real time worden geëvalueerd. Dit is omdat zij voor het segment binnen het tijdinterval van 30 dagen gekwalificeerd hebben. </li>
     </ul> </p> <p> <p>Opmerking: De <span class="wintitle"> Geschatte Real-Time Population</span> metrisch omvat geen apparaten die voor een segment op verbindingen die door <span class="wintitle"> Regels van de Fusie van het Profiel </span> worden verstrekt die een <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> optie van de apparatengrafiek </a> gebruiken gekwalificeerd hebben. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geraamde totale populatie (potentieel)</span> </p> </td> 
   <td colname="col2"> <p>Het geschatte aantal unieke bezoekers dat zich in uw nieuwe of gewijzigde segment zou kunnen bevinden. Net als bij bijna elke schatting garanderen de prestaties uit het verleden geen toekomstige resultaten, maar u kunt het geschatte totaal gebruiken voor: </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">Zie hoeveel mensen een nieuw of herzien segment zou kunnen bereiken aangezien u een segment bouwt. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">Tune het segment afhankelijk van uw doelstellingen. Grote segmenten zijn bijvoorbeeld handig voor bewustmakingscampagnes en kleinere segmenten zijn handig voor doelgerichte of heroriënterende campagnes. </li> 
     </ul> </p> <p> <p>Opmerking: De <span class="wintitle"> Geschatte Totale Bevolking</span> metrisch omvat geen apparaten die voor een segment gekwalificeerd hebben die op verbindingen door <span class="wintitle"> Regels van de Fusie van het Profiel </span> worden verstrekt die een <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> optie van de apparatengrafiek </a> gebruiken. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bestaande (werkelijke) segmentpopulatiegegevens gedefinieerd {#existing-segment-population}

[!UICONTROL Profile Merge Rules] van invloed zijn op de werkelijke aantallen in real time en de totale bevolking. Deze totalen variëren afhankelijk van als [!UICONTROL Profile Merge Rule] een segment tot een optie van de apparatengrafiek behoort of niet. Zie ook: [Opties voor profielsamenvoegregel gedefinieerd](../../features/profile-merge-rules/merge-rule-definitions.md).

### Bevolkingsgegevens segment voor [!UICONTROL Merge Rules] zonder a [!UICONTROL Device Graph Option]

In de volgende tabel worden de werkelijke cijfers voor real-time en de totale bevolking gedefinieerd wanneer uw segmenten worden gebruikt door een [!UICONTROL Profile Merge Rule] die zonder een [!UICONTROL device graph]-optie is gemaakt. Dit zijn de instellingen voor apparaatopties **[!UICONTROL No Device Options]** en **[!UICONTROL Current Device Proflie]**.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Real-Time Population (bestaand)</span> </p> </td> 
   <td colname="col2"> <p>Het werkelijke aantal unieke bezoekers dat in real time voor het opgegeven tijdbereik werd gezien en dat op het moment dat ze door de Audience Manager werden gezien, in aanmerking kwam voor het segment. </p> <p>In <span class="wintitle"> de Bouwer van het Segment</span>, kunnen de laatste 30 dagpopulaties voor eigenschappen (<span class="wintitle"> Totale Bevolking van het Beetje</span>), voor eigenschappen en segmenten verschillend zijn die in real time worden geëvalueerd. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">Voor eigenschappen, de laatste metrische tellingen van 30 dagen het aantal unieke gebruikers die voor dat bezit tijdens de laatste 30 dagen kwalificeerden. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">Voor segmenten die in real time worden geëvalueerd, tellen de laatste metrische tellingen van 30 dagen het aantal gebruikers die voor een eigenschap (in dat segment) op wat punt in het verleden hebben gekwalificeerd en opnieuw door Audience Manager binnen de laatste 30 dagen gezien. Stel dat u een gebruiker hebt die 60 dagen geleden voor een eigenschap in aanmerking kwam en tien dagen geleden opnieuw werd gezien. In de gegevens wordt deze gebruiker niet toegevoegd aan de telling van het kenmerk omdat hij meer dan 30 dagen geleden voor het eerst in aanmerking kwam voor de eigenschap. Nochtans, zullen zij in het laatste aantal van 30 dagen voor de segmenten worden omvat die in real time worden geëvalueerd. Dit is omdat zij voor het segment binnen het tijdinterval van 30 dagen gekwalificeerd hebben. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Totale populatie (bestaand)</span> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke bezoekers dat vanaf gisteren voor het segment in aanmerking kwam. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Bevolkingsgegevens van segment voor [!UICONTROL Merge Rules] met een [!UICONTROL Device Graph] optie

In de volgende tabel worden de werkelijke cijfers voor real-time en de totale bevolking gedefinieerd wanneer uw segmenten worden gebruikt door een [!UICONTROL Profile Merge Rule] die is gemaakt met een [!DNL device graph]-optie. Dit zijn de instellingen voor apparaatopties voor de [!UICONTROL Profile Link Device Graph], de [!DNL Adobe] [!DNL device graph] en andere externe [!DNL device graph]-opties die voor u beschikbaar zijn.


| Kolom A | Kolom B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing) ] | Het werkelijke aantal apparaten dat in real time wordt gezien met huidige profielen die, wanneer samengevoegd met maximaal 100 andere apparaatprofielen die door de apparatengrafiek worden aangesloten, de eigenschappen bevatten om voor het segment in aanmerking te komen het ogenblik het door Audience Manager werd gezien. |
| [!UICONTROL Total Population (Existing)] | Het totale aantal apparaten met profielen dat, wanneer samengevoegd met maximaal 100 andere apparaatprofielen die door de apparaatgrafiek worden aangesloten, allemaal in aanmerking kwamen voor het segment. |

### Beperkingen als gevolg van recentie- en frequentieredsies bij het schatten van segmentpopulaties

[!UICONTROL Segment Builder] steunt de schattingen van de segmentgrootte voor segmentregels die tot 4 recentie en frequentiedragers bevatten. Als u bij het samenstellen van een segmentregel meer dan vier recentie- en frequentie-expressies kiest, wordt een fout weergegeven bij het schatten van de populatie.

### Beperkingen als gevolg van [!UICONTROL Merge Rules] bij schatting van segmentpopulaties

Momenteel is er een bekende beperking omdat onze schatting van de segmentgrootte niet voor [!UICONTROL profile merge rules] verantwoordelijk is. Kijk bijvoorbeeld naar segmenten met de **[!UICONTROL No Authenticated Profile + Current Device Profile]** [samenvoegregel](../../features/profile-merge-rules/merge-rule-definitions.md). Wegens de manier wij momenteel de aantallen van de segmentraming berekenen, zullen de geschatte populaties voor authentiek verklaarde profielen omvatten. De bestaande segmentpopulaties negeren geverifieerde profielen echter op de juiste wijze.

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken](../../faq/faq-profile-merge.md)
* [Profielkoppeling](../profile-merge-rules/merge-rules-overview.md)

