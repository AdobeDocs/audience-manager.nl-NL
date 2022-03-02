---
description: De vakkwalificatie, of de verwezenlijking van het bezit, wordt behandeld verschillend in Audience Manager, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
keywords: De Kwalificatie van het spoor, de realisatie van het Bedieningsspoor, de Unieke Redalisaties van het Bedieningsgebied, UTR, Totale Bevolking van het Verkeer, TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: Verwijzing naar beroepskwalificatie
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 1%

---

# Referenties voor eigenschap- en segmentkwalificaties {#trait-qualification-reference}

De vakkwalificatie, of de verwezenlijking van het bezit, wordt behandeld verschillend in Audience Manager, afhankelijk van het handelstype. Zie [Kwalificatie volgens type dienstreis](#trait-type) voor meer informatie over de kwalificatie van het type eigenschap.

Zie ook [Bevolking segment in realtime en totale segmentpopulatie](#real-time-segment) voor meer informatie over segmentkwalificatie.



## Kwalificatie volgens type dienstreis {#trait-type}

| Type overtrek | Kwalificatiecriteria |
|---|---|
| Op regels gebaseerde tradities | De vakkwalificatie gebeurt in real time, aangezien de gebruikers voor een eigenschap in hun browser kwalificeren. Uw gebruikers zullen ongeveer 4 uur na u beginnen in aanmerking te komen voor een op regels gebaseerde eigenschap [de eigenschap maken](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) in de gebruikersinterface. Met op regels gebaseerde kenmerken kunt u [recentie en frequentie](../segments/recency-and-frequency.md) besturingselementen voor ad-frequency capping en andere gevallen van gebruik. |
| Treinen aan boord | De kwalificatie van het spoor gebeurt nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier is [geïmporteerd in Audience Manager](../../faq/faq-inbound-data-ingestion.md) en dat is wanneer de kwalificatie van de eigenschap plaatsvindt . U moet ongeveer 4 uur wachten nadat u een ingebouwd kenmerk hebt gemaakt voordat u een binnenkomend bestand uploadt voor verwerking. Voor niet-geregistreerde kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Algorithmic Traits | Voor algoritmische kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Maptrajecten | Een mapkenmerk geeft een overzicht van de kwalificaties van de kenmerken die het bevat. Lezen [Maptraits: Info](about-folder-traits.md) voor meer informatie . |
| Actieve doelgroepeigenschappen en met databron gesynchroniseerde eigenschappen | An [!UICONTROL Active Audience] de eigenschap bevat alle apparaten die in uw rekening van de Audience Manager worden beheerd. [!UICONTROL Data Source Synced Traits] volgt alle gebruikers verbonden aan een gegevensbron. Meer informatie over [Actieve doelgroepen en gesynchroniseerde gegevensbronnen](client-activity-synced-audience-traits.md). |

## Unieke realisaties van sporen en totale populatie van trekkers {#unique-trait-realizations}

![uniek-eigenschap-realisatie](assets/trait-graph.png)

Afhankelijk van het type resultaten dat de grafiek moet weergeven (gefilterd op [!UICONTROL Device ID] of [!UICONTROL Cross-Device ID]), hebben de meetwaarden verschillende betekenissen:

Wanneer het filtreren van de resultaten door [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal anonieme apparaatbezoekers dat de eigenschap binnen verschillende tijdbereiken aan hun profiel heeft toegevoegd.
* [!UICONTROL Total Trait Population] Dit is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

Wanneer het filtreren van de resultaten door [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal geverifieerde bezoekers dat de eigenschap aan hun profiel heeft toegevoegd, binnen verschillende tijdbereiken.
* [!UICONTROL Total Trait Population] Dit is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

Denk aan de cijfers op deze manier. In de bovenstaande afbeelding, vanaf de [Informatie over track](../../features/traits/trait-details-page.md) view, 90.173 vertegenwoordigt het aantal actieve apparaten, die uw eigenschappen gisteren bezochten. De [!UICONTROL Total Trait Population] van 55.757 staat voor het aantal gebruikers dat momenteel voor dit kenmerk in aanmerking komt. De [!UICONTROL Total Trait Population] figuur is bedoeld om de totale hoeveelheid gebruikers weer te geven die voor segmentatie/doelgerichtheid kan worden gebruikt. Gebruikers blijven doorgaans 120 dagen deel uitmaken van een eigenschap.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, [!UICONTROL Total Trait Population] blijft achter bij de [!UICONTROL Unique Trait Realizations] 24 uur. In de bovenstaande grafiek zie je ongeveer 90.400 [!UICONTROL Unique Trait Realizations] en [!UICONTROL Total Trait Population] van ongeveer 90.300 voor 5 februari. De profielen 90.400 worden toegevoegd aan de profielen [!UICONTROL Total Trait Population] op de volgende dag.

Om het punt naar huis te blijven rijden, als je op dit moment een piek van 10.000 bezoekers zou ervaren, zouden ze in morgen verschijnen [!UICONTROL Unique Trait Realizations], maar pas 24 uur later in de [!UICONTROL Total Trait Population].

Elke verandering in de realisatie van de eigenschap weerspiegelt in segmentpopulaties.

## Bevolking segment in realtime en totale segmentpopulatie {#real-time-segment}

![uniek-eigenschap-realisatie](assets/segment-graph.png)

De [!UICONTROL Real-time Segment Population] telt het aantal apparaten die voor het geselecteerde segment gekwalificeerd zijn en uw eigenschappen, binnen het geselecteerde tijdinterval hebben bereikt.

De [!UICONTROL Total Segment Population] telt het aantal apparaten die voor het geselecteerde segment binnen de geselecteerde tijdwaaier gekwalificeerd hebben. De [!UICONTROL 1 Day] het rapport vertegenwoordigt het meest bijgewerkte aantal segmentpopulaties.

Denk aan de cijfers op deze manier. In de bovenstaande afbeelding, vanaf de [Segmentdetails](../../features/segments/segment-summary-view.md) view, 9.993 vertegenwoordigt het aantal actieve apparaten, die uw eigenschappen gisteren bezochten, en gekwalificeerd voor het segment. De [!UICONTROL Total Segment Population] van 699.532 staat voor het totale aantal apparaten dat momenteel voor dit segment is gekwalificeerd. De [!UICONTROL Total Segment Population] figuur is bedoeld om het totale aantal apparaten te tonen dat voor segmentatie/het richten zou kunnen worden gebruikt.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, [!UICONTROL Total Segment Population] blijft achter bij de [!UICONTROL Real-time Segment Population] 24 uur. In de bovenstaande grafiek zie je een 8.116 [!UICONTROL Real-time Segment Population] en [!UICONTROL Total Segment Population] van 742.000 voor 2 februari. De 8.116 profielen worden toegevoegd aan de [!UICONTROL Total Segment Population] op de volgende dag.

Om het punt naar huis te blijven rijden, als je op dit moment een piek van 10.000 bezoekers zou ervaren, zouden ze in morgen verschijnen [!UICONTROL Real-time Segment Population], maar pas 24 uur later in de [!UICONTROL Total Segment Population].

## Grenswaarde voor beroepskwalificatie {#trait-qualification-limit}

We stellen een limiet van 150.000 vakkwalificaties in voor elk gebruikersprofiel, of het nu gaat om een geverifieerd profiel ([DPUUID](../../reference/ids-in-aam.md)) of een apparaat-id ([UUID](../../reference/ids-in-aam.md)). Merk op dat hoewel DPUUIDs uniek aan een specifiek geval van zijn [!DNL Audience Manager], UUID&#39;s worden gedeeld door de [!DNL Audience Manager] platform. Voor [!UICONTROL UUID]We leggen dus een billijkheidsbeleid op bij het opslaan van beroepskwalificaties. Een algoritme zorgt ervoor dat een gelijk aandeel van [!UICONTROL UUID] profiel beschikbaar wordt gesteld voor elke instantie van [!DNL Audience Manager].
