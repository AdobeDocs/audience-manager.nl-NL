---
description: Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.
seo-description: Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.
seo-title: Overlap segment naar advertentie-eenheid
solution: Audience Manager
title: Overlap segment naar advertentie-eenheid
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---


# Overlap segment naar advertentie-eenheid{#segment-to-ad-unit-overlap}

Het rapport Segment to Ad Unit Overlap wordt weergegeven als een warmtegrafiek die hoge en lage overlap tussen uw advertentie-eenheden en Audience Manager-segmenten markeert.

## Hoofdletters gebruiken {#use-cases}

Met het [!UICONTROL Segment to Ad Unit Overlap] rapport kunt u begrijpen welk publiek uw wegeigenschappen bezoekt. Het rapport geeft de overlapping tussen leden van uw [!DNL Audience Manager] segmenten en het aantal bezoekers aan uw wegeigenschappen weer. Een hogere overlapping betekent dat veel leden van een segment uw webeigenschap bezoeken.

## Het segment gebruiken om het Rapport van de Overlap van de Eenheid toe te voegen {#using-the-report}

Gebruik de besturingselementen **[!UICONTROL Top N Ad Units]** en **[!UICONTROL Top N Segments]** besturingselementen om het gewenste aantal advertentie-eenheden en segmenten voor de overlapping te selecteren. U kunt maximaal 100 items selecteren voor elk item.

Gebruik de controles van de Waaier **van de** Dag en van de **Datum door** om uw blik-achterwaaier aan te passen. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Gebruik de **[!UICONTROL Segment Name]** vakken en de **[!UICONTROL Ad Unit]** vakken om segmenten en eenheden te filteren.

>[!IMPORTANT]
>
>Wanneer het toelaten [!UICONTROL Audience Optimization for Publishers], moet u beschrijvende meta-gegevens voor [!UICONTROL Ad Unit IDs], zoals die in Stap 3 van de Dossiers van Gegevens DFP van de [Invoer in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)wordt beschreven omvatten. Door dit te doen, verzekert u dat het rapport de Webbezit als [!UICONTROL Ad Unit] in plaats van het [!UICONTROL Ad Unit ID].

## De resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Segment to Ad Unit Overlap] rapport kan er ongeveer zo uitzien als hieronder. Houd de muisaanwijzer boven een willekeurige cel voor meer informatie over die bepaalde overlapping. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

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
   <td colname="col2"> <p>Het aantal unieke bezoekers dat in real time voor de gespecificeerde tijdwaaier werd gezien en die voor het segment werden gekwalificeerd op het ogenblik dat zij door <span class="keyword"> Audience Manager</span>werden gezien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal eenheden advertentie</span> </p> </td> 
   <td colname="col2"> <p>Het aantal bezoekers voor deze specifieke advertentie-eenheid. Deze informatie wordt uit de DFP-logboeken gehaald. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal overlappingen</span> </p> </td> 
   <td colname="col2"> <p>De leden van uw segment die aan het punt van de advertentie-eenheid werden blootgesteld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap percentage</span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen ad-unit en segmentpopulaties. Dit is de <span class="wintitle"> Overlappende Aantal</span>Uniques, uitgedrukt als percentage van het <span class="wintitle"> Realtime Uniques</span>van het Segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

