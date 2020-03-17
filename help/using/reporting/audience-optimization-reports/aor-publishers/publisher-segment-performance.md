---
description: Het rapport van de Prestaties van het Segment vergelijkt in kaart gebrachte en unmapped segmenten door impressies en in real time de Uniques van het Segment. Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten. Het vergelijken van deze verschillende segmenttypes binnen en tussen rapporten helpt u bestaande campagnes optimaliseren en over het hoofd gezien segmenten vinden die u naar een bestemming voor het richten kunt verzenden.
seo-description: Het rapport van de Prestaties van het Segment vergelijkt in kaart gebrachte en unmapped segmenten door impressies en in real time de Uniques van het Segment. Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten. Het vergelijken van deze verschillende segmenttypes binnen en tussen rapporten helpt u bestaande campagnes optimaliseren en over het hoofd gezien segmenten vinden die u naar een bestemming voor het richten kunt verzenden.
seo-title: Rapport Segmentprestaties
solution: Audience Manager
title: Rapport Segmentprestaties
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Rapport Segmentprestaties{#segment-performance-report}

Het rapport van de Prestaties van het Segment vergelijkt in kaart gebrachte en unmapped segmenten door impressies en in real time de Uniques van het Segment.

Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten.

Het vergelijken van deze verschillende segmenttypes binnen en tussen rapporten helpt u bestaande campagnes optimaliseren en over het hoofd gezien segmenten vinden die u naar een bestemming voor het richten kunt verzenden.

## Gevallen gebruiken {#use-cases}

Met het [!UICONTROL Segment Performance] rapport kunt u:

* Omlijnde publiekssegmenten identificeren die de drijvende kracht achter schaal of prestaties zijn.
* Identificeer niet in kaart gebrachte segmenten om in toekomstige campagnes te introduceren, die op de bijdrage van een publiek aan vroegere prestaties worden gebaseerd.

## Het rapport Segmentprestaties gebruiken {#using-segment-performance-report}

Schakel tussen **[!UICONTROL Mapped]** en **[!UICONTROL Unmapped]** om segmenten te selecteren die wel of niet aan een doel zijn toegewezen. Selecteer **[!UICONTROL All]** om al uw segmenten in het rapport op te nemen.

Gebruik de controles van de Waaier **van de** Dag en van de **Datum door** om uw blik-achterwaaier aan te passen. De terugkijkperioden van 7 en 30 dagen zijn alleen beschikbaar voor zondag-datums.

Gebruik het **[!UICONTROL Line Item]** drop-down vakje om de Web-eigenschappen te selecteren waarvoor u informatie wilt terugkeren.

In de **[!UICONTROL Segment Data Source]** drop-down doos, selecteer de gegevensbronnen die de segmenten bevatten u in het rapport wilt zien.

Gebruik de **[!UICONTROL Segment]** drop-down doos om te selecteren welke segmenten u in het rapport wilt zien.

>[!IMPORTANT]
>
>Wanneer het toelaten [!UICONTROL Audience Optimization for Publishers], moet u beschrijvende meta-gegevens voor [!UICONTROL Line Item IDs], zoals die in Stap 3 van de Dossiers van Gegevens DFP van de [Invoer in de Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)van de Publiek wordt beschreven omvatten. Door dit te doen, verzekert u dat het rapport de Webbezit als [!UICONTROL Line Item] in plaats van het [!UICONTROL Line Item ID].

## De resultaten interpreteren {#interpreting-results}

Uw [!UICONTROL Segment Performance] rapport kan er ongeveer zo uitzien als hieronder. Klik in uw rapport op een ballon om de onderliggende gegevens weer te geven. Zie beschrijvingen voor de aanvullende informatie in de tabel onder het voorbeeldrapport.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segment </p> </td> 
   <td colname="col2"> <p>De alfanumerieke naam die u aan dit segment hebt toegewezen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Segment-id </p> </td> 
   <td colname="col2"> <p>De unieke id van dit segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lijnitem </p> </td> 
   <td colname="col2"> <p>De webeigenschap waarvoor u dit rapport ziet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Klikken </p> </td> 
   <td colname="col2"> <p>Het aantal keren dat leden van deze eigenschap op items in uw webeigenschap hebben geklikt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressies </p> </td> 
   <td colname="col2"> <p>Het aantal keren dat leden van deze eigenschap aan uw voorraad zijn blootgesteld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Doorklikfrequentie. </p> <p>Met deze metrische waarde wordt het percentage van de afbeeldingen weergegeven dat wordt gevolgd door klikken. Verdeel Klikken door Impressies om deze metrische waarde te verkrijgen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Realtime segmentpopulatie </p> </td> 
   <td colname="col2"> <p>Het daadwerkelijke aantal unieke bezoekers die in real time voor de gespecificeerde tijdwaaier werden gezien en die voor het segment werden gekwalificeerd op het ogenblik dat zij door de Manager <span class="keyword"> van het</span>Publiek werden gezien. </p> </td> 
  </tr> 
 </tbody> 
</table>

## De resultaten van uw toegewezen segment lezen {#read-mapped-segment}

De positie van uw in kaart gebrachte segmenten in een rapport kan u veel vertellen over welke segmenten goed presteren en waar u sommige aanpassingen zou kunnen moeten maken.

Als u het rapport wilt lezen, kunt u de resultaten opsplitsen in vier secties met denkbeeldige lijnen (in rood) en de categorieën die in het voorbeeldrapport hieronder worden weergegeven. De labels in het voorbeeld kunnen u helpen de prestaties van segmenten te begrijpen en op deze resultaten te reageren.

![](assets/publisher_segment_performance_mapped.png)

## De resultaten van het niet-toegewezen segment lezen {#read-unmapped-segment}

Het bekijken van unmapped segmenten in een [!UICONTROL Segment Performance] rapport is een grote manier om nieuwe segmenten te vinden u niet voor het richten hebt overwogen. In feite, kunnen sommige van deze segmenten uw in kaart gebrachte segmenten overtreffen.

Als u dit rapport wilt lezen, kunt u de resultaten opsplitsen in vier secties met denkbeeldige lijnen (in rood) en categorieën die in het voorbeeldrapport hieronder worden weergegeven.

![](assets/publisher_segment_performance_unmapped.png)
