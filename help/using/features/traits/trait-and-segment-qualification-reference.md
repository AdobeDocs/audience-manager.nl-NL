---
description: De kwalificatie van het spoor, of de verwezenlijking van het bezit, wordt behandeld verschillend in Audience Manager, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
keywords: De Kwalificatie van het spoor, de realisatie van het Bedieningsgebied, Unieke Redalisaties van het Bedieningsgebied, UTR, Totale Bevolking van het Bedieningsgebied, TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Verwijzing naar beroepskwalificatie
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# Verwijzing naar de kwalificatie van het spoor en het segment {#trait-qualification-reference}

De kwalificatie van het spoor, of de verwezenlijking van het bezit, wordt behandeld verschillend in Audience Manager, afhankelijk van het handelstype. Zie [ Kwalificatie van het Beetje door Type van het Spoor ](#trait-type) voor details over het type van eigenschap kwalificatie.

Bovendien, zie &lbrace;de Bevolking van het segment in real time en de Totale Bevolking van het Segment [ voor details over segmentkwalificatie.](#real-time-segment)



## Kwalificatie volgens type dienstreis {#trait-type}

| Type overtrek | Kwalificatiecriteria |
|---|---|
| Op regels gebaseerde tradities | De vakkwalificatie gebeurt in real time, aangezien de gebruikers voor een eigenschap in hun browser kwalificeren. Uw gebruikers zullen beginnen kwalificerend voor een op regel-gebaseerd bezit ongeveer 4 uren nadat u [ het spoor ](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) in UI creeert. Op regel-gebaseerde treinen staan u toe om [ recentie en frequentie ](../segments/recency-and-frequency.md) controles voor het afvangen van frequentie en andere gebruiksgevallen te gebruiken. |
| Treinen aan boord | De kwalificatie van het spoor gebeurt nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier wordt ingevoerd in Audience Manager [&#128279;](../../faq/faq-inbound-data-ingestion.md) en dat is wanneer de vakkwalificatie gebeurt. U moet ongeveer 4 uur wachten nadat u een ingebouwd kenmerk hebt gemaakt voordat u een binnenkomend bestand uploadt voor verwerking. Voor niet-geregistreerde kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Algorithmic Traits | Voor algoritmische kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Maptrajecten | Een mapkenmerk geeft een overzicht van de kwalificaties van de kenmerken die het bevat. Lees [ de Tanden van de Omslag: Ongeveer ](about-folder-traits.md) voor meer informatie. |
| Actieve doelgroepen en gesynchroniseerde gegevensstromen van Source | Een [!UICONTROL Active Audience] -kenmerk bevat alle apparaten die in uw Audience Manager-account worden beheerd. [!UICONTROL Data Source Synced Traits] houdt alle gebruikers bij die aan een gegevensbron zijn gekoppeld. Lees meer over [ de Actieve Traits van het Publiek en Gegevens Source Gesynchroniseerde Tanden ](client-activity-synced-audience-traits.md). |

## Unieke realisaties van sporen en totale populatie van trekkers {#unique-trait-realizations}

![ uniek-eigenschap-realisatie ](assets/trait-graph.png)

Afhankelijk van het type resultaten dat de grafiek moet weergeven (gefilterd door [!UICONTROL Device ID] of [!UICONTROL Cross-Device ID] ), hebben de meetgegevens verschillende betekenissen:

Wanneer u de resultaten filtert met [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] is het aantal anonieme apparaatbezoekers dat de eigenschap binnen verschillende tijdbereiken aan hun profiel heeft toegevoegd.
* [!UICONTROL Total Trait Population] is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

Wanneer u de resultaten filtert met [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] is het aantal geverifieerde bezoekers dat de eigenschap aan hun profiel heeft toegevoegd, binnen verschillende tijdbereiken.
* [!UICONTROL Total Trait Population] is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

Denk aan de cijfers op deze manier. In het beeld hierboven, van de [ mening van de Details van het Tonen ](../../features/traits/trait-details-page.md), vertegenwoordigt 90.173 het aantal actieve apparaten, die uw eigenschappen gisteren bezochten. De [!UICONTROL Total Trait Population] van 55.757 vertegenwoordigt de hoeveelheid gebruikers die momenteel voor deze eigenschap in aanmerking komen. De [!UICONTROL Total Trait Population] figuur is bedoeld om de totale hoeveelheid gebruikers weer te geven die voor segmentatie/doelframes kan worden gebruikt. Gebruikers blijven doorgaans 120 dagen deel uitmaken van een eigenschap.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, loopt [!UICONTROL Total Trait Population] altijd 24 uur achter op de [!UICONTROL Unique Trait Realizations] . In de bovenstaande grafiek zie je ongeveer 90.400 [!UICONTROL Unique Trait Realizations] en een [!UICONTROL Total Trait Population] van ongeveer 90.300 voor 5 februari. De volgende dag worden de 90.400 profielen toegevoegd aan [!UICONTROL Total Trait Population] .

Om het punt naar huis verder te rijden, als je op dit moment een piek van 10.000 bezoekers zou ervaren, zouden ze in de 24 uur later verschijnen in de [!UICONTROL Unique Trait Realizations] .[!UICONTROL Total Trait Population]

Elke verandering in de realisatie van de eigenschap weerspiegelt in segmentpopulaties.

## Bevolking segment in realtime en totale segmentpopulatie {#real-time-segment}

![ uniek-eigenschap-realisatie ](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population] telt het aantal apparaten die voor het geselecteerde segment gekwalificeerd zijn en uw eigenschappen, binnen het geselecteerde tijdinterval hebben bereikt.

[!UICONTROL Total Segment Population] telt het aantal apparaten die voor het geselecteerde segment binnen de geselecteerde tijdwaaier gekwalificeerd hebben. Het [!UICONTROL 1 Day] rapport vertegenwoordigt het meest bijgewerkte aantal segmentpopulaties.

Denk aan de cijfers op deze manier. In het beeld hierboven, van de [ mening van de Details van het 1&rbrace; Segment ](../../features/segments/segment-summary-view.md), vertegenwoordigt 9.993 het aantal actieve apparaten, die uw eigenschappen gisteren bezochten, en voor het segment gekwalificeerd. De [!UICONTROL Total Segment Population] van 699.532 staat voor het totale aantal apparaten dat momenteel voor dit segment is gekwalificeerd. De [!UICONTROL Total Segment Population] figuur is bedoeld om het totale aantal apparaten te tonen dat voor segmentatie/het richten zou kunnen worden gebruikt.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, loopt [!UICONTROL Total Segment Population] altijd 24 uur achter op de [!UICONTROL Real-time Segment Population] . In de bovenstaande grafiek ziet u een [!UICONTROL Real-time Segment Population] van 742.000  en een [!UICONTROL Total Segment Population] van 742.000 voor 2 februari. De volgende dag worden de 8.116 profielen toegevoegd aan [!UICONTROL Total Segment Population] .

Om het punt naar huis verder te rijden, als je op dit moment een piek van 10.000 bezoekers zou ervaren, zouden ze in de 24 uur later verschijnen in de [!UICONTROL Real-time Segment Population] .[!UICONTROL Total Segment Population]

## Grenswaarde voor beroepskwalificatie {#trait-qualification-limit}

Wij dwingen een grens van 150.000 vakkwalificaties voor elk gebruikersprofiel af, of het een voor authentiek verklaard profiel ([ DPUUID ](../../reference/ids-in-aam.md)) of een apparatenidentiteitskaart ([ UUID ](../../reference/ids-in-aam.md)) is. Hoewel de DPUUID&#39;s uniek zijn voor een specifieke instantie van [!DNL Audience Manager] , worden UUID&#39;s gedeeld door het [!DNL Audience Manager] -platform. Voor [!UICONTROL UUID] s, leggen wij een billijkheidsbeleid op wanneer het opslaan van baankwalificaties. Een algoritme zorgt ervoor dat een gelijk deel van het [!UICONTROL UUID] -profiel beschikbaar wordt gemaakt voor elke instantie van [!DNL Audience Manager] .
