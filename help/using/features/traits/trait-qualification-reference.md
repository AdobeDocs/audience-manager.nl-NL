---
description: De kwalificatie van het spoor, of de realisatie van het bezit, wordt behandeld verschillend in de Manager van de Auditie, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: De kwalificatie van het spoor, of de realisatie van het bezit, wordt behandeld verschillend in de Manager van de Auditie, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.
seo-title: Verwijzing naar beroepskwalificatie
solution: Audience Manager
title: Verwijzing naar beroepskwalificatie
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 40ac91af26ed4a95492dde872288dc2e9059cdf9

---


# Verwijzing naar beroepskwalificatie {#trait-qualification-reference}

De kwalificatie van het spoor, of de realisatie van het bezit, wordt behandeld verschillend in de Manager van de Auditie, afhankelijk van het handelstype. Zie de onderstaande tabel voor meer informatie over de kwalificatie van het kenmerk.

## Kwalificatie volgens type dienstreis {#trait-type}

| Type overtrek | Kwalificatiecriteria |
|---|---|
| Op regels gebaseerde tradities | De vakkwalificatie gebeurt in real time, aangezien de gebruikers voor een eigenschap in hun browser kwalificeren. Uw gebruikers zullen ongeveer 4 uur na het [creëren van de eigenschap](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) in UI beginnen in aanmerking te komen voor een op regel-gebaseerde eigenschap. De op regel-gebaseerde eigenschappen staan u toe om [recentie en frequentiecontroles](../segments/recency-and-frequency.md) voor het afschilderen van de frequentie en andere gebruiksgevallen te gebruiken. |
| Treinen aan boord | De kwalificatie van het spoor gebeurt nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier wordt [ingevoerd in de Manager](../../faq/faq-inbound-data-ingestion.md) van het Publiek en dat is wanneer de vakkwalificatie gebeurt. U moet ongeveer 4 uur wachten nadat u een ingebouwd kenmerk hebt gemaakt voordat u een binnenkomend bestand uploadt voor verwerking. Voor niet-geregistreerde kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Algorithmic Traits | Voor algoritmische kenmerken is het maximumaantal kwalificaties voor een gebruikersprofiel 1. |
| Maptrajecten | Een mapkenmerk geeft een overzicht van de kwalificaties van de kenmerken die het bevat. Leesmaptraits [: Informatie over](about-folder-traits.md) meer informatie. |
| Actieve doelgroepen en gesynchroniseerde gegevensbronnen | Een [!UICONTROL Active Audience] kenmerk bevat alle apparaten die worden beheerd in uw account van Audience Manager. [!UICONTROL Data Source Synced Traits] volgt alle gebruikers verbonden aan een gegevensbron. Lees meer over de Traits van het [Actieve Publiek en Gegevensbron de Gesynchroniseerde Tanden](client-activity-synced-audience-traits.md). |

## Unieke realisaties van sporen en totale populatie van trekkers {#unique-trait-realizations}

![uniek-eigenschap-realisatie](assets/trait-graph.png)

Het [!UICONTROL Unique Trait Realizations] aantal bezoekers dat de eigenschap aan hun profiel heeft toegevoegd, binnen verschillende tijdbereiken.

Het [!UICONTROL Total Trait Population] geeft het aantal bezoekers aan dat deze eigenschap in hun profiel heeft.

Denk aan de cijfers op deze manier. In de bovenstaande afbeelding geeft 90.173 uit de weergave [Details](../../features/traits/trait-details-page.md) over spoor het aantal actieve apparaten aan dat uw eigenschappen gisteren heeft bezocht. Het [!UICONTROL Total Trait Population] aantal van 55.757 staat voor het aantal gebruikers dat momenteel voor dit kenmerk in aanmerking komt. Het [!UICONTROL Total Trait Population] cijfer is bedoeld om de totale hoeveelheid gebruikers te tonen die voor segmentatie/het richten zou kunnen worden gebruikt. Gebruikers blijven doorgaans 120 dagen deel uitmaken van een eigenschap.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, loopt de groep [!UICONTROL Total Trait Population] altijd 24 uur achter op de [!UICONTROL Unique Trait Realizations] groep. In de bovenstaande grafiek zie je ongeveer 90.400 [!UICONTROL Unique Trait Realizations] en een [!UICONTROL Total Trait Population] van ongeveer 90.300 voor 5 februari. De volgende dag worden de profielen 90.400 aan de [!UICONTROL Total Trait Population] pagina toegevoegd.

Om het punt naar huis te rijden, als je op dit moment een piek van 10.000 bezoekers zou ervaren, zouden ze morgen verschijnen [!UICONTROL Unique Trait Realizations], maar pas 24 uur later in de [!UICONTROL Total Trait Population]stad.

Elke verandering in de realisatie van de eigenschap weerspiegelt in segmentpopulaties.

## Bevolking segment in realtime en totale segmentpopulatie {#real-time-segment}

![uniek-eigenschap-realisatie](assets/segment-graph.png)

Het [!UICONTROL Real-time Segment Population] telt het aantal apparaten die voor het geselecteerde segment hebben gekwalificeerd en uw eigenschappen, binnen het geselecteerde tijdinterval hebben bereikt.

De [!UICONTROL Total Segment Population] tellingen het aantal apparaten die voor het geselecteerde segment binnen de geselecteerde tijdwaaier gekwalificeerd hebben. Het [!UICONTROL 1 Day] rapport vertegenwoordigt het meest bijgewerkte aantal segmentpopulaties.

Denk aan de cijfers op deze manier. In de bovenstaande afbeelding staat in de weergave [Segmentdetails](../../features/segments/segment-summary-view.md) 9.993 voor het aantal actieve apparaten dat gisteren uw eigenschappen heeft bezocht en dat is gekwalificeerd voor het segment. Het aantal [!UICONTROL Total Segment Population] van 699.532 vertegenwoordigt het totale aantal apparaten momenteel gekwalificeerd voor dit segment. Het [!UICONTROL Total Segment Population] cijfer moet het totale aantal apparaten tonen dat voor segmentatie/het richten zou kunnen worden gebruikt.

Omdat we twee verschillende computertaken uitvoeren om de twee populaties te berekenen, loopt de groep [!UICONTROL Total Segment Population] altijd 24 uur achter op de [!UICONTROL Real-time Segment Population] groep. In de bovenstaande grafiek zie je een 8.116 [!UICONTROL Real-time Segment Population] en een [!UICONTROL Total Segment Population] van 742.000 voor 2 februari. De volgende dag worden de 8.116 profielen toegevoegd aan de [!UICONTROL Total Segment Population] lijst.

Om het punt naar huis te rijden, als je op dit moment een piek van 10.000 bezoekers zou ervaren, zouden ze morgen verschijnen [!UICONTROL Real-time Segment Population], maar pas 24 uur later in de [!UICONTROL Total Segment Population]stad.

## Grenswaarde voor beroepskwalificatie {#trait-qualification-limit}

Voor elk gebruikersprofiel geldt een limiet van 150.000 vakkwalificaties, of het nu gaat om een geverifieerd profiel ([DPUUID](../../reference/ids-in-aam.md)) of een apparaat-id ([UUID](../../reference/ids-in-aam.md)). Merk op dat hoewel DPUUIDs voor een specifiek geval van [!DNL Audience Manager], UUIDs uniek zijn over het [!DNL Audience Manager] platform wordt gedeeld. Voor [!UICONTROL UUID]ons leggen we een billijkheidsbeleid op bij het opslaan van beroepskwalificaties. Een algoritme zorgt ervoor dat een gelijk aandeel van het [!UICONTROL UUID] profiel voor elke instantie van beschikbaar wordt gemaakt [!DNL Audience Manager].
