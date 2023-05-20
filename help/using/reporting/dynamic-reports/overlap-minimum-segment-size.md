---
description: Beschrijft de de grootte van het segment en de vereisten van de aanmaaktijd die door het proces van de het rapportupdate van de Overlapping worden vereist.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Plan voor bijwerken van rapporten overlappen en minimumsegmentgrootte
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Overlaprapporten: updateplanning en minimale segmentgrootte{#overlap-reports-update-schedule-and-minimum-segment-size}

Beschrijft de eigenschap en de segmentgrootte en de vereisten van de aanmaaktijd die door het proces van de het rapportupdate van de Overlapping worden vereist.

## Plan en vereisten bijwerken {#update-schedule}

[!UICONTROL Overlap] rapporten worden wekelijks bijgewerkt op zondag. Voorbewerking van rapporten begint op zaterdag. Dit beïnvloedt hoe de nieuwe of bestaande segmenten in een overlappend rapport op Maandag verschijnen. In een overlappend rapport op te nemen:

* Een segment moet minimaal 70.000 gebruikers in real-time gedurende de laatste 14 dagen bevatten.
* Een kenmerk moet 28.000 bevatten [unieke eigenschapresultaten](/help/using/features/traits/trait-and-segment-qualification-reference.md) in de laatste 14 dagen.
* Een segment moet vóór Donderdag UTC om 12.00 uur zijn gecreeerd (2 volledige dagen vóór het wekelijkse proces van de overlappende rapportupdate begint).
* Uw bedrijf moet volledig zijn [!DNL Audience Manager] klant. Neem contact op met uw [!DNL Audience Manager] consultant of klantenservice voor meer informatie.

## De grootte en/of de aanmaaktijd van het segment hebben invloed op de rapportage {#segment-size}

Als u geen segment ziet in een van de [!UICONTROL Overlap] kan het zijn dat het segment niet aan deze minimumvereisten voldoet.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gebruiksscenario </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentgrootte te klein</b> </p> </td> 
   <td colname="col2"> <p>Laten we zeggen dat u een segment maakt vóór donderdag UTC 12.00 uur, maar dat het minder dan 70.000 gebruikers in realtime bevat. Dit segment wordt niet weergegeven in een <span class="wintitle"> Rapport overlappen</span> totdat het voldoet aan de vereisten voor gebruikersdrempels. Nota, ook, moet het segment de vereiste gebruiker tellen op, of vóór, de periode van de Donderdslimiet. Als de wekelijkse deadline niet wordt gehaald, wordt het segment weergegeven in het dialoogvenster <span class="wintitle"> Rapporten overlappen</span> voor de week na de komende zondag gegevensrun. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment te laat gemaakt</b> </p> </td> 
   <td colname="col2"> <p>Laten we zeggen dat u op vrijdag een segment maakt en dat het meer dan 70.000 gebruikers in realtime bevat. Dit segment wordt niet weergegeven in het dialoogvenster <span class="wintitle"> Rapporten overlappen</span> voor de volgende week omdat deze minder dan twee dagen vóór de updateperiode van het rapport is gemaakt. Het segment wordt echter weergegeven in een <span class="wintitle"> Rapport overlappen</span> na de volgende wekelijkse update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Overlaprapport Eigenschap-naar-eigenschap](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Overlaprapport Segment-naar-eigenschap](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Overlaprapport Segment-naar-segment](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

