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
source-wordcount: '408'
ht-degree: 2%

---

# Overlap van advertentie-eenheid{#ad-unit-overlap}

De **[!UICONTROL Ad Unit Overlap]** -rapport wordt weergegeven als een warmtediagram dat hoge en lage overlappingen tussen uw advertentie-eenheden markeert.

## Gebruiksscenario {#use-cases}

Met de **[!UICONTROL Ad Unit Overlap]** rapport, kunt u inzicht krijgen in waar uw publiek over uw Web-eigenschappen overlapt. In het rapport worden uw 100 belangrijkste verwante eigenschappen besproken en wordt de overlapping tussen deze eigenschappen weergegeven.

## Het rapport Overlap toevoegen gebruiken {#using-the-report}

Gebruik de **[!UICONTROL Top N Base Ad Units]** en **[!UICONTROL Top N Overlapping Ad Units]** besturingselementen om het gewenste aantal advertentie-eenheden voor de overlapping te selecteren. U kunt maximaal 100 items selecteren voor elk item.

Gebruik de **Dagbereik** en **Datum tot** besturingselementen voor het aanpassen van het bereik van terugkijkers. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Gebruik de **[!UICONTROL Base Ad Unit]** en de **[!UICONTROL Overlap Ad Unit]** Hiermee selecteert u welke advertentie-eenheden u in het overlappende rapport wilt weergeven.

>[!IMPORTANT]
>
>Als u [!UICONTROL Audience Optimization for Publishers]moet u beschrijvende metagegevens opnemen voor [!UICONTROL Ad Unit IDs], zoals beschreven in stap 3 van [Google Ad Manager (voorheen DFP)-gegevensbestanden importeren in Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Door dit te doen verzekert u dat het rapport de Webbezit als detailleert [!UICONTROL Ad Unit] in plaats van de [!UICONTROL Ad Unit ID].

## De resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Ad Unit Overlap] het rapport kan er ongeveer zo uitzien als hieronder . Houd de muisaanwijzer boven een willekeurige cel voor meer informatie over die bepaalde overlapping. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

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
   <td colname="col2"> <p>De overlapping tussen uw gebruikers die een <span class="wintitle"> Basis AdEenheid</span> en <span class="wintitle"> Ad-eenheid overlappen</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Overlap percentage</span> </p> </td> 
   <td colname="col2"> <p>De overlapping tussen uw gebruikers die een <span class="wintitle"> Basis AdEenheid</span> en <span class="wintitle"> Ad-eenheid overlappen</span>. Dit is het <span class="wintitle"> Aantal overlappingen</span>, uitgedrukt als percentage van het <span class="wintitle"> Basis AdEenheid</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
