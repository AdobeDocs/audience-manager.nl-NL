---
description: Het rapport Overlap advertentie-eenheid wordt weergegeven als een hitteschema die hoge en lage overlap tussen uw advertentie-eenheden markeert.
seo-description: The Ad Unit Overlap report is displayed as a heat chart that highlights high and low overlaps between your Ad Units.
seo-title: Ad Unit Overlap
solution: Audience Manager
title: Overlap van advertentie-eenheid
uuid: e4467e81-acbf-474e-b501-89d57395651f
feature: Audience Optimization Reports
exl-id: 08b219c6-bf0c-4473-9459-83b3657dfb15
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 0%

---

# Overlap van advertentie-eenheid{#ad-unit-overlap}

Het rapport **[!UICONTROL Ad Unit Overlap]** wordt weergegeven als een hitteschema die hoge en lage overlappingen tussen uw advertentie-eenheden markeert.

## Gebruiksscenario {#use-cases}

Met het **[!UICONTROL Ad Unit Overlap]** -rapport kunt u insight laten zien waar uw publiek de wegeigenschappen overlapt. In het rapport worden uw 100 belangrijkste verwante eigenschappen besproken en wordt de overlapping tussen deze eigenschappen weergegeven.

## Het rapport Overlap toevoegen gebruiken {#using-the-report}

Gebruik de besturingselementen **[!UICONTROL Top N Base Ad Units]** en **[!UICONTROL Top N Overlapping Ad Units]** om het gewenste aantal advertentie-eenheden voor de overlapping te selecteren. U kunt maximaal 100 items selecteren voor elk item.

Gebruik de **Waaier van de Dag** en **Datum door** controles om uw blik-achterwaaier aan te passen. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Gebruik de besturingselementen **[!UICONTROL Base Ad Unit]** en **[!UICONTROL Overlap Ad Unit]** om te selecteren welke advertentie-eenheden u in het overlappende rapport wilt weergeven.

>[!IMPORTANT]
>
>Wanneer het toelaten van [!UICONTROL Audience Optimization for Publishers], moet u beschrijvende meta-gegevens voor [!UICONTROL Ad Unit IDs] omvatten, zoals die in Stap 3 van [ wordt beschreven de Dossiers van de Gegevens van Google Ad Manager van de Invoer (vroeger DFP) in Audience Manager ](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Op deze manier zorgt u ervoor dat in het rapport de webeigenschap wordt weergegeven als [!UICONTROL Ad Unit] in plaats van als [!UICONTROL Ad Unit ID] .

## De resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Ad Unit Overlap] -rapport kan er ongeveer als volgt uitzien. Houd de muisaanwijzer boven een willekeurige cel voor meer informatie over die bepaalde overlapping. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

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
   <td colname="col1"> <p><span class="wintitle"> Eenheid voor overlappen en toevoegen </span> </p> </td> 
   <td colname="col2"> <p>De naam van je voorraadobject. Dit kan bijvoorbeeld een van uw websites of een artikel op uw website zijn. In de bovenstaande afbeelding zijn de basis en de eenheden de artikelen 9 tot en met 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Basis en eenheid </span> </p> </td> 
   <td colname="col2"> <p>De naam van je voorraadobject. Dit kan bijvoorbeeld een van uw websites of een artikel op uw website zijn. In de bovenstaande afbeelding zijn de basis en de eenheden de artikelen 1 tot en met 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal Uniques voor overlappen en eenheden </span> </p> </td> 
   <td colname="col2"> <p>Het aantal gebruikers dat de advertentie-eenheid 9-18 heeft bezocht. Deze informatie is afkomstig uit de logboeken van Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal Uniques van basis- en eenheden </span> </p> </td> 
   <td colname="col2"> <p>Het aantal gebruikers dat de advertentie-eenheid 1 - 8 heeft bezocht. Deze informatie is afkomstig uit de logboeken van Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Aantal Uniques overlappen </span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen uw gebruikers die een <span class="wintitle"> Eenheid van de Basis en van de Advertentie </span> hebben bezocht en <span class="wintitle"> overlap en Eenheid </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap Percentage </span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen uw gebruikers die een <span class="wintitle"> Eenheid van de Basis en van de Advertentie </span> hebben bezocht en <span class="wintitle"> overlap en Eenheid </span>. Dit is de <span class="wintitle"> Aantal van Uniques van de Overlappen </span>, die als percentage van de <span class="wintitle"> Eenheid van de Basis Ad </span> wordt uitgedrukt. </p> </td> 
  </tr> 
 </tbody> 
</table>
