---
description: Het rapport Overlap advertentie-eenheid wordt weergegeven als een hitteschema die hoge en lage overlap tussen uw advertentie-eenheden markeert.
seo-description: Het rapport Overlap advertentie-eenheid wordt weergegeven als een hitteschema die hoge en lage overlap tussen uw advertentie-eenheden markeert.
seo-title: Overlap van advertentie-eenheid
solution: Audience Manager
title: Overlap van advertentie-eenheid
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 3%

---


# Overlap van advertentie-eenheid{#ad-unit-overlap}

Het **[!UICONTROL Ad Unit Overlap]** rapport wordt weergegeven als een warmtediagram dat hoge en lage overlappingen tussen uw advertentie-eenheden markeert.

## Gebruiksscenario {#use-cases}

Met het **[!UICONTROL Ad Unit Overlap]** rapport kunt u meer inzicht krijgen in waar uw publiek de wegeigenschappen overlapt. In het rapport worden uw 100 belangrijkste verwante eigenschappen besproken en wordt de overlapping tussen deze eigenschappen weergegeven.

## Het rapport Overlap toevoegen gebruiken {#using-the-report}

Gebruik de besturingselementen **[!UICONTROL Top N Base Ad Units]** en **[!UICONTROL Top N Overlapping Ad Units]** besturingselementen om het gewenste aantal advertentie-eenheden voor de overlapping te selecteren. U kunt maximaal 100 items selecteren voor elk item.

Gebruik de controles van de Waaier **van de** Dag en van de **Datum door** om uw blik-achterwaaier aan te passen. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Gebruik de **[!UICONTROL Base Ad Unit]** besturingselementen en de **[!UICONTROL Overlap Ad Unit]** besturingselementen om aan te geven welke advertentie-eenheden u in het overlappende rapport wilt weergeven.

>[!IMPORTANT]
>
>Wanneer u deze optie inschakelt, moet u beschrijvende metagegevens voor [!UICONTROL Audience Optimization for Publishers]de bestanden opnemen, zoals wordt beschreven in stap 3 van Google Ad Manager (voorheen DFP)-gegevensbestanden [!UICONTROL Ad Unit IDs]importeren in Audience Manager [](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Door dit te doen, verzekert u dat het rapport de Webbezit als [!UICONTROL Ad Unit] in plaats van het [!UICONTROL Ad Unit ID].

## De resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Ad Unit Overlap] rapport kan er ongeveer zo uitzien als hieronder. Houd de muisaanwijzer boven een willekeurige cel voor meer informatie over die bepaalde overlapping. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Ad-eenheid overlappen</span> </p> </td> 
   <td colname="col2"> <p>De naam van je voorraadobject. Dit kan bijvoorbeeld een van uw websites of een artikel op uw website zijn. In de bovenstaande afbeelding zijn de basis en de eenheden de artikelen 9 tot en met 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basis AdEenheid</span> </p> </td> 
   <td colname="col2"> <p>De naam van je voorraadobject. Dit kan bijvoorbeeld een van uw websites of een artikel op uw website zijn. In de bovenstaande afbeelding zijn de basis en de eenheden de artikelen 1 tot en met 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal Unieke eenheden overlappen</span> </p> </td> 
   <td colname="col2"> <p>Het aantal gebruikers dat de advertentie-eenheid 9-18 heeft bezocht. Deze informatie is afkomstig uit de logboeken van Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal Unieke eenheden basiseenheid</span> </p> </td> 
   <td colname="col2"> <p>Het aantal gebruikers dat de advertentie-eenheid 1 - 8 heeft bezocht. Deze informatie is afkomstig uit de logboeken van Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal overlappingen</span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen uw gebruikers die een <span class="wintitle"> BasisAdvertentie Eenheid</span> en de Eenheid <span class="wintitle"></span>van de Overlapping hebben bezocht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap percentage</span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen uw gebruikers die een <span class="wintitle"> BasisAdvertentie Eenheid</span> en de Eenheid <span class="wintitle"></span>van de Overlapping hebben bezocht. Dit is de <span class="wintitle"> Overlap Aantal</span>Uniques, uitgedrukt als percentage van de <span class="wintitle"> Basis AdUnit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
