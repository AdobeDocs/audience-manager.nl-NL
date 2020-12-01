---
description: Beschrijft segmenten, hun samenstellende delen, en regelverwezenlijking met de Bouwer van het Segment.
seo-description: Beschrijft segmenten, hun samenstellende delen, en regelverwezenlijking met de Bouwer van het Segment.
seo-title: Doel, samenstelling en regels van segmenten
solution: Audience Manager
title: Doel, samenstelling en regels van segmenten
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 5%

---


# Segmenten: doel, samenstelling en regels {#segments-purpose-composition-and-rules}

Beschrijft [!UICONTROL segments], hun samenstellende delen, en regelverwezenlijking met [!UICONTROL Segment Builder].

## Doel van [!UICONTROL Segments]

Een *`segment`* (of een *`audience`*) is een reeks gebruikers die gemeenschappelijke attributen delen. In Audience Manager, creeert u [!UICONTROL segments] met server-zijregels. Met deze regels kunt u publieksgroepen samenstellen op basis van kenmerken van sitebezoekers, zoals:

* Gedrag;
* Demografische gegevens (leeftijd, geslacht, inkomen, enz.);
* Andere kenmerken die u in de gebruikersinterface kunt definiëren.

## [!UICONTROL Segment] Samenstelling

Een Audience Manager [!UICONTROL segment] is een serverregel die uit individuele of groepen eigenschappen bestaat. De sporen worden samengesteld uit gegevenselementen genoemd zeer belangrijk-waardeparen. Samen met regels die u instelt op het niveau [!UICONTROL segment], bevatten deze sleutel-waarde paren de criteria die bezoekers in aanmerking komen voor eigenschap en [!UICONTROL segment] lidmaatschap.

## Overwegingen bij [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Toewijzing

Bij het toewijzen van Adobe Analytics [!UICONTROL segments] of het rapporteren van reeksen aan uw organisatie van de Experience Cloud, leidt de Audience Manager automatisch tot nieuwe, overeenkomstige, read-only [!UICONTROL segments] en trekken. U kunt de opslaglocatie van deze [!UICONTROL segments] niet wijzigen vanuit Audience Manager. Elke wijziging die u op uw toegewezen Adobe Analytics [!UICONTROL segments] of rapportsuites uitvoert, wordt echter weerspiegeld in de Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] is anders dan [!DNL Adobe Analytics] [!UICONTROL segments]. Lees [Segmenten in Analytics en Audience Manager](https://docs.adobe.com/content/help/nl-NL/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) voor een diepgaande beschrijving van de verschillen.

## Op regels gebaseerde [!UICONTROL Segments] maken met [!UICONTROL Segment Builder]

In tegenstelling tot traditionele pixels die worden geactiveerd als reactie op eenvoudige ja/nee-voorwaarden, kunt u met [!UICONTROL Segment Builder] complexe [!UICONTROL segment]-vereisten maken. Net als [!UICONTROL traits], [!UICONTROL segments] evalueert gegevens gebruikend [!DNL Boolean] uitdrukkingen ([!DNL AND], [!DNL OR], [!DNL NOT]), vergelijkingsexploitanten (groter dan, minder dan, gelijk aan, enz.), en recency/frequentiecriteria. Deze functies helpen doelgericht publiek [!UICONTROL segments] te creëren dat relevant is voor uw bedrijfsbehoeften.

## Voordelen

[!UICONTROL Segments] verbetert op standaardpixel-gebaseerde publiekscreatie/segmenteringsprocessen omdat zij u laten:

* Bouw relevant, nuttig [!UICONTROL segments] met eerste en derdeeigenschappen.
* Maak geavanceerde en complexe segmentatieregels met Booleaanse operatoren, vergelijkingsexpressies en criteria voor recentie en frequentie.
* Verzend [!UICONTROL segment] gegevens naar een bestemmingspartner.
* De prestaties van de monitor met de rapporten van de Audience Manager.

>[!MORELIKETHIS]
>
>* [Signalen, eigenschappen en segmenten](../../reference/signal-trait-segment.md)

