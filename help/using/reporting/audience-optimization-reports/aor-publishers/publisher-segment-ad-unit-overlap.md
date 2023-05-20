---
description: Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.
seo-description: The Segment to Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units and Audience Manager segments.
seo-title: Segment to Ad Unit Overlap
solution: Audience Manager
title: Overlap van segment naar advertentie-eenheid
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Overlap van segment naar advertentie-eenheid{#segment-to-ad-unit-overlap}

Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.

## Gebruiksscenario {#use-cases}

Met de [!UICONTROL Segment to Ad Unit Overlap] rapport, kunt u begrijpen welk publiek uw Web-eigenschappen bezoekt. Het rapport geeft de overlapping tussen leden van uw [!DNL Audience Manager] segmenten en het aantal bezoekers van uw wegeigenschappen. Een hogere overlapping betekent dat veel leden van een segment uw webeigenschap bezoeken.

## Het segment gebruiken om het Rapport van de Overlap van de Eenheid toe te voegen {#using-the-report}

Gebruik de **[!UICONTROL Top N Ad Units]** en **[!UICONTROL Top N Segments]** besturingselementen om het gewenste aantal advertentie-eenheden en -segmenten voor de overlapping te selecteren. U kunt maximaal 100 items selecteren voor elk item.

Gebruik de **Dagbereik** en **Datum tot** besturingselementen voor het aanpassen van het bereik van terugkijkers. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Gebruik de **[!UICONTROL Segment Name]** en de **[!UICONTROL Ad Unit]** vakjes om om het even welk van segmenten en ad eenheden te filtreren.

>[!IMPORTANT]
>
>Als u [!UICONTROL Audience Optimization for Publishers]moet u beschrijvende metagegevens opnemen voor [!UICONTROL Ad Unit IDs], zoals beschreven in stap 3 van [Google Ad Manager (voorheen DFP)-gegevensbestanden importeren in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Door dit te doen verzekert u dat het rapport de Webbezit als detailleert [!UICONTROL Ad Unit] in plaats van de [!UICONTROL Ad Unit ID].

## De resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Segment to Ad Unit Overlap] het rapport kan er ongeveer zo uitzien als hieronder . Houd de muisaanwijzer boven een willekeurige cel voor meer informatie over die bepaalde overlapping. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

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
   <td colname="col1"> <p><span class="wintitle"> AdEenheid </span> </p> </td> 
   <td colname="col2"> <p>De naam van je voorraadobject. Dit kan bijvoorbeeld een van uw websites of een artikel op uw website zijn. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal in realtime-Uniques-segmenten</span> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke bezoekers dat in real time voor de gespecificeerde tijdwaaier werd gezien en die voor het segment op het ogenblik werden gekwalificeerd zij gezien door <span class="keyword"> Audience Manager</span>. </p> </td> 
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
   <td colname="col2"> <p>De overlapping tussen ad-unit en segmentpopulaties. Dit is het <span class="wintitle"> Aantal overlappingen</span>, uitgedrukt als percentage van het <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
