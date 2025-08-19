---
description: Het rapport Overlap segment naar advertentie-eenheid wordt weergegeven als een hitteschema die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Overlap segment naar advertentie-eenheid
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 1%

---

# Overlap segment naar advertentie-eenheid{#segment-to-ad-unit-overlap}

Het rapport Overlap segment naar advertentie-eenheid wordt weergegeven als een hitteschema die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.

## Gebruiksscenario {#use-cases}

Met het [!UICONTROL Segment to Ad Unit Overlap] -rapport kunt u begrijpen welk publiek uw wegeigenschappen bezoekt. Het rapport geeft de overlapping tussen leden van uw [!DNL Audience Manager] -segmenten en het aantal bezoekers aan uw wegeigenschappen weer. Een hogere overlapping betekent dat veel leden van een segment uw webeigenschap bezoeken.

## Het segment gebruiken om het Rapport van de Overlap van de Eenheid toe te voegen {#using-the-report}

Gebruik de besturingselementen **[!UICONTROL Top N Ad Units]** en **[!UICONTROL Top N Segments]** om het gewenste aantal advertentie-eenheden en -segmenten voor de overlapping te selecteren. U kunt maximaal 100 items selecteren voor elk item.

Gebruik de **Waaier van de Dag** en **Datum door** controles om uw blik-achterwaaier aan te passen. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Gebruik de vakken **[!UICONTROL Segment Name]** en **[!UICONTROL Ad Unit]** om segmenten en eenheden te filteren.

>[!IMPORTANT]
>
>Wanneer het toelaten van [!UICONTROL Audience Optimization for Publishers], moet u beschrijvende meta-gegevens voor [!UICONTROL Ad Unit IDs] omvatten, zoals die in Stap 3 van [ wordt beschreven de Dossiers van de Gegevens van Google Ad Manager van de Invoer (vroeger DFP) in Audience Manager ](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Op deze manier zorgt u ervoor dat in het rapport de webeigenschap wordt weergegeven als [!UICONTROL Ad Unit] in plaats van als [!UICONTROL Ad Unit ID] .

## De resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Segment to Ad Unit Overlap] -rapport kan er ongeveer als volgt uitzien. Houd de muisaanwijzer boven een willekeurige cel voor meer informatie over die bepaalde overlapping. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Toegevoegde eenheid </span> </p> </td> 
   <td colname="col2"> <p>De naam van je voorraadobject. Dit kan bijvoorbeeld een van uw websites of een artikel op uw website zijn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Realtime aantal Uniques Segment </span> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke bezoekers die in real time voor de gespecificeerde tijdwaaier werden gezien en die voor het segment op het ogenblik gekwalificeerd waren zij door <span class="keyword"> Audience Manager </span> werden gezien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal unieke eenheden toevoegen </span> </p> </td> 
   <td colname="col2"> <p>Het aantal bezoekers voor deze specifieke advertentie-eenheid. Deze informatie is afkomstig uit de logboeken van Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal Uniques overlappen </span> </p> </td> 
   <td colname="col2"> <p>De leden van uw segment die aan het punt van de advertentie-eenheid werden blootgesteld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Percentage </span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen ad-unit en segmentpopulaties. Dit is het <span class="wintitle"> Aantal van Uniques van de Overlappen </span>, die als percentage van het <span class="wintitle"> Echte segment - tijdUniques </span> wordt uitgedrukt. </p> </td> 
  </tr> 
 </tbody> 
</table>
