---
description: De vakkwalificatie, of de verwezenlijking van het bezit, wordt behandeld verschillend in Audience Manager, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
keywords: De Kwalificatie van het spoor, de realisatie van het Bedieningsspoor, de Unieke Redalisaties van het Bedieningsgebied, UTR, Totale Bevolking van het Verkeer, TTP
seo-description: De vakkwalificatie, of de verwezenlijking van het bezit, wordt behandeld verschillend in Audience Manager, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
seo-title: Verwijzing naar beroepskwalificatie
solution: Audience Manager
title: Verwijzing naar beroepskwalificatie
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,223f5fc6-c939-4bc6-94a3-5d953abc601a
translation-type: tm+mt
source-git-commit: e13f81df9b0d59cd958f4c2a615c31df00ce2cc5
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 1%

---

# Referenties voor eigenschap- en segmentkwalificaties {#trait-qualification-reference}

De vakkwalificatie, of de verwezenlijking van het bezit, wordt behandeld verschillend in Audience Manager, afhankelijk van het handelstype. Zie [Kwalificatie door Type spoor](#trait-type) voor details over het type van eigenschap kwalificatie.

Bovendien, zie [Bevolking van het segment in real time en de Totale Bevolking van het Segment](#real-time-segment) voor details over segmentkwalificatie.



## Kwalificatie van het dienstreis door Type {#trait-type}

| Type overtrek | Kwalificatiecriteria |
|---|---|
| Op regels gebaseerde tradities | De vakkwalificatie gebeurt in real time, aangezien de gebruikers voor een eigenschap in hun browser kwalificeren. Uw gebruikers zullen beginnen in aanmerking te komen voor een op regel-gebaseerde eigenschap ongeveer 4 uur nadat u [de eigenschap ](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) in UI creeert. Op regel-gebaseerde eigenschappen staan u toe om [recency en frequentie](../segments/recency-and-frequency.md) controles voor het afvangen van de ad frequentie en andere gebruiksgevallen te gebruiken. |
| Treinen aan boord | De kwalificatie van het spoor gebeurt nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier is [ingevoerd in Audience Manager](../../faq/faq-inbound-data-ingestion.md) en dat is wanneer de vakkwalificatie gebeurt. U moet ongeveer 4 uur wachten nadat u een ingebouwd kenmerk hebt gemaakt voordat u een binnenkomend bestand uploadt voor verwerking. Voor niet-geregistreerde kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Algorithmic Traits | Voor algoritmische kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Maptrajecten | Een mapkenmerk geeft een overzicht van de kwalificaties van de kenmerken die het bevat. [Maptraits: Informatie over](about-folder-traits.md) voor meer informatie. |
| Actieve doelgroepeigenschappen en met databron gesynchroniseerde eigenschappen | Een [!UICONTROL Active Audience]-kenmerk bevat alle apparaten die in uw Audience Manager-account worden beheerd. [!UICONTROL Data Source Synced Traits] volgt alle gebruikers verbonden aan een gegevensbron. Lees meer over [Actieve treinen van het Publiek en Gegevensbron Gesynchroniseerde Tanden](client-activity-synced-audience-traits.md). |

## Unieke trainingsrealisaties en totale trainingspopulatie {#unique-trait-realizations}

![uniek-eigenschap-realisatie](assets/trait-graph.png)

Afhankelijk van het type resultaten dat u wilt weergeven in de grafiek (gefilterd door [!UICONTROL Device ID] of [!UICONTROL Cross-Device ID]), hebben de meetwaarden verschillende betekenissen:

Wanneer het filtreren van de resultaten door [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal anonieme apparaatbezoekers dat de eigenschap binnen verschillende tijdbereiken aan hun profiel heeft toegevoegd.
* [!UICONTROL Total Trait Population] Dit is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

Wanneer het filtreren van de resultaten door [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal geverifieerde bezoekers dat de eigenschap aan hun profiel heeft toegevoegd, binnen verschillende tijdbereiken.
* [!UICONTROL Total Trait Population] Dit is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

Denk aan de cijfers op deze manier. In de bovenstaande afbeelding geeft 90.173 uit de weergave [Details overtrekken](../../features/traits/trait-details-page.md) het aantal actieve apparaten aan dat uw eigenschappen gisteren heeft bezocht. De [!UICONTROL Total Trait Population] van 55.757 vertegenwoordigt de hoeveelheid gebruikers momenteel gekwalificeerd voor dit bezit. Het cijfer [!UICONTROL Total Trait Population] is bedoeld om de totale hoeveelheid gebruikers te tonen die voor segmentatie/gericht kon worden gebruikt. Gebruikers blijven doorgaans 120 dagen deel uitmaken van een eigenschap.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, blijft de [!UICONTROL Total Trait Population] altijd 24 uur achter op de [!UICONTROL Unique Trait Realizations]. In de bovenstaande grafiek ziet u ongeveer 90.400 [!UICONTROL Unique Trait Realizations] en een [!UICONTROL Total Trait Population] van ongeveer 90.300 voor 5 februari. De profielen 90.400 worden op de volgende dag toegevoegd aan [!UICONTROL Total Trait Population].

Om het punt thuis verder te rijden, als je op dit moment een piek van 10.000 bezoekers had ervaren, zouden ze opdagen in [!UICONTROL Unique Trait Realizations] van morgen, maar zouden ze slechts 24 uur later opdagen in [!UICONTROL Total Trait Population].

Elke verandering in de realisatie van de eigenschap weerspiegelt in segmentpopulaties.

## Bevolking segment in realtime en totale segmentpopulatie {#real-time-segment}

![uniek-eigenschap-realisatie](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population] telt het aantal apparaten die voor het geselecteerde segment gekwalificeerd hebben en uw eigenschappen, binnen het geselecteerde tijdinterval hebben bereikt.

[!UICONTROL Total Segment Population] telt het aantal apparaten die voor het geselecteerde segment binnen de geselecteerde tijdwaaier gekwalificeerd hebben. Het [!UICONTROL 1 Day] rapport vertegenwoordigt het meest bijgewerkte aantal segmentpopulaties.

Denk aan de cijfers op deze manier. In de bovenstaande afbeelding wordt in de weergave [Segmentdetails](../../features/segments/segment-summary-view.md) het aantal actieve apparaten weergegeven dat gisteren uw eigenschappen heeft bezocht en dat is gekwalificeerd voor het segment. [!UICONTROL Total Segment Population] van 699.532 vertegenwoordigt het totale aantal apparaten momenteel gekwalificeerd voor dit segment. Het cijfer [!UICONTROL Total Segment Population] is bedoeld om het totale aantal apparaten te tonen dat voor segmentatie/gericht kon worden gebruikt.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, blijft de [!UICONTROL Total Segment Population] altijd 24 uur achter op de [!UICONTROL Real-time Segment Population]. In de grafiek hierboven, kunt u 8.116 [!UICONTROL Real-time Segment Population] en [!UICONTROL Total Segment Population] van 742.000 voor 2 februari zien. De 8.116 profielen worden toegevoegd aan [!UICONTROL Total Segment Population] op de volgende dag.

Om het punt thuis verder te rijden, als je op dit moment een piek van 10.000 bezoekers had ervaren, zouden ze opdagen in [!UICONTROL Real-time Segment Population] van morgen, maar zouden ze slechts 24 uur later opdagen in [!UICONTROL Total Segment Population].

## Limiet voor beroepskwalificatie {#trait-qualification-limit}

Voor elk gebruikersprofiel geldt een limiet van 150.000 vakkwalificaties. Dit is een geverifieerd profiel ([DPUUID](../../reference/ids-in-aam.md)) of een apparaat-id ([UUID](../../reference/ids-in-aam.md)). Merk op dat hoewel DPUUIDs voor een specifiek geval van [!DNL Audience Manager] uniek zijn, UUIDs over het [!DNL Audience Manager] platform wordt gedeeld. Voor [!UICONTROL UUID]s, leggen wij een billijkheidsbeleid op wanneer het opslaan van baankwalificaties. Een algoritme zorgt ervoor dat een gelijk aandeel van het [!UICONTROL UUID] profiel voor elke instantie van [!DNL Audience Manager] ter beschikking wordt gesteld.
