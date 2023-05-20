---
description: De componenten van de gegevensverwerking omvatten Hadoop, Snowflake, SOLR, en Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Onderdelen voor dataverwerking
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 3%

---

# Onderdelen voor dataverwerking{#data-processing-components}

De componenten van de gegevensverwerking omvatten Hadoop, Snowflake, SOLR, en Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager gebruikt de volgende componenten om gegevens te verwerken:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is het belangrijkste gegevensbestand dat alles bevat [!DNL Audience Manager] kent een gebruiker. Wanneer bijvoorbeeld [Profielcacheservers](../../reference/system-components/components-data-collection.md) Als u logbestanden maakt die gegevens over uw gebruikers bevatten, worden die gegevens naar de Hadoop verzonden voor opslag. Andere belangrijke Hadopen zijn onder meer:

* **Hive:** Een gegevenspakhuis voor Hadoop. Hive beheert ad hoc vragen aan de gegevens die in Hadoop worden opgeslagen.

* **HBase:** Een zeer grote database van Hadopen. Het verwerkt en beheert binnenkomende en uitgaande gegevens, kenmerkregels, algoritmische modelleringsinformatie, en voert vele andere functies met betrekking tot het opslaan en het bewegen van gegevens aan verschillende systemen uit.

Klanten hebben geen directe toegang tot deze systemen. Klanten werken echter indirect met hen samen, aangezien deze componenten belangrijke gegevens over hun sitebezoekers opslaan.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) is een enorme clouddatabase. Deze tabel bevat gegevens voor veel van de dashboardgrafieken en de bijbehorende tekstvakken waarin de procentuele wijziging voor elk item in de grafiek wordt weergegeven. Als u [!DNL Audience Manager] en bekijk de dashboardrapporten, u wisselt met gegevens die door worden verstrekt [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Dit is geenszins een uitgebreide lijst, maar sommige gemeenschappelijke dashboard meldt dat [!UICONTROL Snowflake] is verantwoordelijk voor het opnemen van:

* [Rapport Dagelijkse eigenschapvariatie](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Alle overlappende rapporten (zie [Interactieve rapporten](/help/using/reporting/dynamic-reports/dynamic-reports.md) voor informatie over elk overlappend rapport).
* [Ongebruikte-signalenrapport](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR is een open-source database en serversysteem van Apache. Het biedt robuuste en snelle zoekmogelijkheden voor onze grote gegevenssets. Als [!DNL Audience Manager] klant, kunt u SOLR in actie zien wanneer u segmenten bouwt. Het verstrekt gegevens aan [!UICONTROL Estimated Historic Segment Size] verslag. SOLR is vanwege zijn snelheid ideaal voor deze rol. Zo kunt u met SOLR de historische gegevens over grootte bijwerken terwijl u regels maakt en nieuwe kenmerken aan een segment toevoegen.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] gebruik [Tableau](https://www.tableausoftware.com/) om gegevens weer te geven in het dialoogvenster [Interactieve rapporten](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) en de [Audience Optimization-rapporten](../../reporting/audience-optimization-reports/audience-optimization-reports.md). De interactieve rapporten tonen prestaties en overlappen gegevens voor eigenschappen en segmenten. In plaats van getallen te gebruiken die in kolommen en rijen zijn gerangschikt, worden gegevens geretourneerd met verschillende vormen, kleuren en grootten. Bovendien, kunt u individueel of groepen gegevenspunten kiezen en neer in de rapportresultaten voor meer details boren. Deze visualisatietechnieken en de hulp van de rapportinteractiviteit maken grote hoeveelheden numerieke gegevens gemakkelijker te begrijpen.



![](assets/advertiser_analytics.png)
