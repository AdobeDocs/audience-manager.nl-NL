---
description: Beschrijft de de grootte van het segment en de vereisten van de aanmaaktijd die door het proces van de het rapportupdate van de Overlapping worden vereist.
seo-description: Beschrijft de de grootte van het segment en de vereisten van de aanmaaktijd die door het proces van de het rapportupdate van de Overlapping worden vereist.
seo-title: Plan en minimale segmentgrootte overlappen bij Update van rapporten
solution: Audience Manager
title: Plan en minimale segmentgrootte overlappen bij Update van rapporten
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# Rapporten overlappen: Plan en minimale segmentgrootte bijwerken{#overlap-reports-update-schedule-and-minimum-segment-size}

Beschrijft de de grootte van het segment en de vereisten van de aanmaaktijd die door het proces van de het rapportupdate van de Overlapping worden vereist.

## Plan en vereisten bijwerken {#update-schedule}

[!UICONTROL Overlap] rapporten worden wekelijks bijgewerkt op zondag. Voorbewerking van rapporten begint op zaterdag. Dit beïnvloedt hoe de nieuwe of bestaande segmenten in een overlappend rapport op Maandag verschijnen. In een overlappend rapport op te nemen:

* Een segment moet minimaal 70.000 gebruikers in real-time gedurende de laatste 14 dagen bevatten. Meer informatie over de [minimale unieke bezoekersvereisten voor reisdocumenten en segmenten](../../reporting/report-sampling.md#data-sampling-ratio).
* Een segment moet vóór Donderdag UTC om 12.00 uur zijn gecreeerd (2 volledige dagen vóór het wekelijkse proces van de overlappende rapportupdate begint).
* Uw bedrijf moet een Volledige [!DNL Audience Manager] klant zijn. Neem contact op met uw [!DNL Audience Manager] consultant of de klantenservice voor meer informatie.

## De grootte en/of de aanmaaktijd van het segment hebben invloed op de rapportage {#segment-size}

Als u geen segment in één van de [!UICONTROL Overlap] rapporten ziet, kan het zijn omdat het segment niet aan deze minimumvereisten voldoet.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hoofdletters gebruiken </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segmentgrootte te klein</b> </p> </td> 
   <td colname="col2"> <p>Laten we zeggen dat u een segment maakt vóór donderdag UTC 12.00 uur, maar dat het minder dan 70.000 gebruikers in realtime bevat. Dit segment zal niet in een <span class="wintitle"> Overlap Rapport</span> verschijnen tot het aan de vereisten van de gebruikersdrempel voldoet. Nota, ook, moet het segment de vereiste gebruiker tellen op, of vóór, de periode van de Donderdslimiet. Als het niet aan de wekelijkse termijn voldoet, zal het segment in de Rapporten <span class="wintitle"> van de</span> Overlappen voor de week na de aanstaande de gegevenslooppas van de Zondag verschijnen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment te laat gemaakt</b> </p> </td> 
   <td colname="col2"> <p>Laten we zeggen dat u op vrijdag een segment maakt en dat het meer dan 70.000 gebruikers in realtime bevat. Dit segment zal niet in de Rapporten <span class="wintitle"> van de</span> Overlapping voor de volgende week verschijnen omdat het minder dan 2 dagen vóór de periode van de rapportupdate werd gecreeerd. Nochtans, zal het segment in een <span class="wintitle"> Overlap Rapport</span> na de volgende wekelijkse update verschijnen. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapport overlappingen trait-to-Trait](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Overlap-rapport segment-naar-spoor](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Overlap-rapport segment-naar-segment](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

