---
description: Gegevensverwerkingscomponenten omvatten Hadoop, Snowflake, SOLR en Tableau.
seo-description: Gegevensverwerkingscomponenten omvatten Hadoop, Snowflake, SOLR en Tableau.
seo-title: Componenten gegevensverwerking
solution: Audience Manager
title: Componenten gegevensverwerking
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Componenten gegevensverwerking{#data-processing-components}

Gegevensverwerkingscomponenten omvatten Hadoop, Snowflake, SOLR en Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager gebruikt de volgende componenten om gegevens te verwerken:

## Hadoop {#hadoop}

In [!DNL Audience Manager], is Hadoop het hoofdgegevensbestand dat alles bevat [!DNL Audience Manager] weet over een gebruiker. Wanneer de [profielcacheservers](../../reference/system-components/components-data-collection.md) bijvoorbeeld logbestanden maken die gegevens over uw gebruikers bevatten, worden die gegevens naar Hadoop verzonden voor opslag. Andere belangrijke Hadoop-elementen zijn:

* **Hive:** Een data-entrepot voor Hadoop. Hive beheert ad-hocquery&#39;s voor de gegevens die in Hadoop zijn opgeslagen.

* **HBase:** Een zeer grote Hadoop-database. Het verwerkt en beheert binnenkomende en uitgaande gegevens, kenmerkregels, algoritmische modelleringsinformatie, en voert vele andere functies met betrekking tot het opslaan en het bewegen van gegevens aan verschillende systemen uit.

Klanten hebben geen directe toegang tot deze systemen. Klanten werken echter indirect met hen samen, aangezien deze componenten belangrijke gegevens over hun sitebezoekers opslaan.

## Sneeuwvlok {#snowflake}

[Sneeuwvlok](https://www.snowflake.net/) is een enorme clouddatabase. Deze tabel bevat gegevens voor veel van de dashboardgrafieken en de bijbehorende tekstvakken waarin de procentuele wijziging voor elk item in de grafiek wordt weergegeven. Als u de dashboardrapporten gebruikt [!DNL Audience Manager] en bekijkt, communiceert u met gegevens die door worden verstrekt [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Dit is geenszins een uitgebreide lijst, maar een aantal gemeenschappelijke dashboardrapporten die verantwoordelijk [!UICONTROL Snowflake] zijn voor:

* [Dagelijks verslag over de variatie van het reisdoel](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Leverings- en prestatierapport](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* Alle overlappende rapporten (zie de [Interactieve sectie van Rapporten](/help/using/reporting/dynamic-reports/dynamic-reports.md) voor informatie over elk overlappend rapport).
* [Rapport Ongebruikte signalen](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR is een open-source database en serversysteem van Apache. Het biedt robuuste en snelle zoekmogelijkheden voor onze grote gegevenssets. Als [!DNL Audience Manager] klant, kunt u SOLR in actie zien wanneer u segmenten bouwt. Het verstrekt gegevens aan het [!UICONTROL Estimated Historic Segment Size] rapport. SOLR is vanwege zijn snelheid ideaal voor deze rol. Zo kunt u met SOLR de historische gegevens over grootte bijwerken terwijl u regels maakt en nieuwe kenmerken aan een segment toevoegen.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] gebruikt [Tableau](https://www.tableausoftware.com/) om gegevens in de [Interactieve Rapporten](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) en de Rapporten [van de Optimalisering van de](../../reporting/audience-optimization-reports/audience-optimization-reports.md)Publiek te tonen. De interactieve rapporten tonen prestaties en overlappen gegevens voor eigenschappen en segmenten. In plaats van getallen te gebruiken die in kolommen en rijen zijn gerangschikt, worden gegevens geretourneerd met verschillende vormen, kleuren en grootten. Bovendien, kunt u individueel of groepen gegevenspunten kiezen en neer in de rapportresultaten voor meer details boren. Deze visualisatietechnieken en de hulp van de rapportinteractiviteit maken grote hoeveelheden numerieke gegevens gemakkelijker te begrijpen.



![](assets/advertiser_analytics.png)

