---
description: Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.
seo-description: Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.
seo-title: Overlap van segment naar advertentie-eenheid
solution: Audience Manager
title: Overlap van segment naar advertentie-eenheid
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization-rapporten
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Overlap van segment naar advertentie-eenheid{#segment-to-ad-unit-overlap}

Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.

## Gebruiksscenario {#use-cases}

Met het [!UICONTROL Segment to Ad Unit Overlap] rapport, kunt u begrijpen welk publiek uw Webeigenschappen bezoekt. Het rapport geeft de overlapping tussen leden van uw [!DNL Audience Manager]-segmenten en het aantal bezoekers aan uw wegeigenschappen weer. Een hogere overlapping betekent dat veel leden van een segment uw webeigenschap bezoeken.

## Rapport {#using-the-report} voor overlap van segment toevoegen

Gebruik de besturingselementen **[!UICONTROL Top N Ad Units]** en **[!UICONTROL Top N Segments]** om het gewenste aantal advertentie-eenheden en -segmenten voor de overlapping te selecteren. U kunt maximaal 100 items selecteren voor elk item.

Gebruik de besturingselementen **Dagbereik** en **Datum tot en met** om het bereik van de terugblik aan te passen. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Met de vakken **[!UICONTROL Segment Name]** en **[!UICONTROL Ad Unit]** kunt u alle segmenten en eenheden filteren.

>[!IMPORTANT]
>
>Wanneer u [!UICONTROL Audience Optimization for Publishers] inschakelt, moet u beschrijvende metagegevens voor [!UICONTROL Ad Unit IDs] opnemen, zoals beschreven in stap 3 van [Google Ad Manager (voorheen DFP)-gegevensbestanden importeren in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Door dit te doen, verzekert u dat het rapport de Webbezit als [!UICONTROL Ad Unit] in plaats van [!UICONTROL Ad Unit ID] detailleert.

## Resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Segment to Ad Unit Overlap]-rapport kan er ongeveer als volgt uitzien. Houd de muisaanwijzer boven een willekeurige cel voor meer informatie over die bepaalde overlapping. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

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
   <td colname="col1"> <p><span class="wintitle"> AdEenheid  </span> </p> </td> 
   <td colname="col2"> <p>De naam van je voorraadobject. Dit kan bijvoorbeeld een van uw websites of een artikel op uw website zijn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal in realtime-Uniques-segmenten</span> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke bezoekers dat in real time voor de gespecificeerde tijdwaaier werd gezien en die voor het segment op het ogenblik gekwalificeerd waren zij door <span class="keyword"> Audience Manager </span> werden gezien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal eenheden advertentie</span> </p> </td> 
   <td colname="col2"> <p>Het aantal bezoekers voor deze specifieke advertentie-eenheid. Deze informatie is afkomstig uit de logboeken van Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal overlappingen</span> </p> </td> 
   <td colname="col2"> <p>De leden van uw segment die aan het punt van de advertentie-eenheid werden blootgesteld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap percentage</span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen ad-unit en segmentpopulaties. Dit is <span class="wintitle"> het Aantal van Uniques van de Overlappen</span>, uitgedrukt als percentage van <span class="wintitle"> Realtime Uniques van het Segment </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
