---
description: In het rapport Segmentprestaties worden de in kaart gebrachte en niet-toegewezen segmenten vergeleken op basis van indrukkingen en conversiesnelheden. Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten. Het vergelijken van deze verschillende segmenttypes binnen en tussen rapporten helpt u bestaande campagnes optimaliseren en over het hoofd gezien segmenten vinden die u naar een bestemming voor het richten kunt verzenden.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Segmentprestatierapport
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 1%

---

# Segmentprestatierapport{#segment-performance-report}

De [!UICONTROL Segment Performance] het rapport vergelijkt in kaart gebrachte en unmapped segmenten door beelden en omzettingspercentages. Een in kaart gebracht segment is een segment u creeert en naar een bestemming verzendt voor het richten. Een niet in kaart gebracht segment is een segment dat u hebt gecreeerd maar niet verzonden naar een bestemming voor het richten. Het vergelijken van deze verschillende segmenttypes binnen en tussen rapporten helpt u bestaande campagnes optimaliseren en over het hoofd gezien segmenten vinden die u naar een bestemming voor het richten kunt verzenden.

## De resultaten van uw toegewezen segment lezen {#read-mapped-segment-results}

De toegewezen [!UICONTROL Segment Performance] het rapport toont alle segmenten u creeerde en naar een bestemming voor het richten verzond.De positie van uw in kaart gebrachte segmenten in een rapport kan u veel vertellen over welke segmenten goed presteren en waar u sommige aanpassingen zou kunnen moeten maken.

Als u het rapport wilt lezen, kunt u de resultaten opsplitsen in vier secties met denkbeeldige lijnen (in rood) en de categorieën die in het voorbeeldrapport hieronder worden weergegeven.

![](assets/mapped-segment-performance.png)

De labels in het voorbeeld en de volgende tabel kunnen u helpen de prestaties van segmenten te begrijpen en te reageren op deze resultaten.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Positie </th> 
   <th colname="col2" class="entry"> Plaatsing geeft aan </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Linksboven</b> </p> </td> 
   <td colname="col2"> <p>Goede omrekeningskoersen. </p> <p>U kunt meer omzettingen krijgen door indrukken te verhogen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Linksonder</b> </p> </td> 
   <td colname="col2"> <p>Lage conversietarieven. </p> <p>U kunt deze segmenten beter niet als doelsegmenten opgeven. De segmenten in deze sectie maken grote kandidaten voor vergelijking met die in de unmapped segmentresultaten. Sommige van uw niet in kaart gebrachte segmenten kunnen beter presteren dan de segmenten u reeds richt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Rechtsboven</b> </p> </td> 
   <td colname="col2"> <p>Sterke prestaties. Laat deze segmenten alleen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Rechtsonder</b> </p> </td> 
   <td colname="col2"> <p>Lage conversiesnelheden en hoge indrukken. </p> <p>Segmenten in deze sectie presteren niet goed. Wellicht wilt u het budget van deze segmenten en segmenten in het linkerbovenkwadrant van het rapport verschuiven. Dit zal helpen de indruk verminderen en kan helpen omrekeningskoersen voor segmenten in deze bodem juiste sectie verbeteren. Vergelijk deze toegewezen segmenten ook met de niet-toegewezen segmenten. Sommige van uw niet in kaart gebrachte segmenten kunnen beter presteren dan de segmenten u reeds richt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## De resultaten van het niet-toegewezen segment lezen {#read-unmapped-segment-results}

Niet-toegewezen segmenten in een [!UICONTROL Segment Performance] het rapport is een grote manier om nieuwe segmenten te vinden u voor het richten niet overwogen hebt. In feite, kunnen sommige van deze segmenten uw in kaart gebrachte segmenten overtreffen. Dit komt omdat een segment zonder toewijzing moet voldoen aan een reeks kwalificatiecriteria die in dit rapport moeten worden opgenomen. Om in dit rapport te worden opgenomen, moet een niet in kaart gebracht segment:

* Omzettingen hebben groter dan het gemiddelde van al uw in kaart gebrachte segmenten.
* U bevindt zich in de bovenste 100 niet-toegewezen segmenten volgens de conversiesnelheid.

Als u dit rapport wilt lezen, kunt u de resultaten opsplitsen in vier secties met denkbeeldige lijnen (in rood) en categorieën die in het voorbeeldrapport hieronder worden weergegeven.

![](assets/unmapped-segment-performance.png)

In dit rapport wilt u zich alleen richten op die niet-toegewezen segmenten in de linkerbovensectie. Deze niet in kaart gebrachte segmenten vertonen hoge omzettingssnelheden voor een laag niveau van indrukking in vergelijking met segmenten in de andere drie secties.

>[!NOTE]
>
>De terugkijkperiodes van 7 dagen en 30 dagen zijn slechts beschikbaar voor Zondag **[!UICONTROL Date Through]** datums.
