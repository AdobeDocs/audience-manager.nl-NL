---
description: Beschrijft segmenten, hun samenstellende delen, en regelverwezenlijking met de Bouwer van het Segment.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Doel, samenstelling en regels van segmenten
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 2%

---

# Segmenten: doel, samenstelling en regels {#segments-purpose-composition-and-rules}

Beschrijft [!UICONTROL segments], de onderdelen waaruit ze bestaan en het maken van regels met [!UICONTROL Segment Builder].

## Doel van [!UICONTROL Segments]

A *`segment`* (of *`audience`*) is een set gebruikers die gemeenschappelijke kenmerken delen. In Audience Manager maakt u [!UICONTROL segments] met serverregels. Met deze regels kunt u publieksgroepen samenstellen op basis van kenmerken van sitebezoekers, zoals:

* Gedrag;
* Demografische gegevens (leeftijd, geslacht, inkomen, enz.);
* Andere kenmerken die u kunt definiëren in de gebruikersinterface.

## [!UICONTROL Segment] Samenstelling

Een Audience Manager [!UICONTROL segment] is een serverregel die bestaat uit individuele of groepen kenmerken. De sporen worden samengesteld uit gegevenselementen genoemd zeer belangrijk-waardeparen. Samen met de regels die u instelt op de [!UICONTROL segment] -niveau, bevatten deze sleutelwaardeparen de criteria die bezoekers in aanmerking komen voor kenmerk en [!UICONTROL segment] lidmaatschap.

## Overwegingen bij [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Toewijzing

Bij toewijzen Adobe Analytics [!UICONTROL segments] of rapporteer suites aan uw organisatie van de Experience Cloud, creeert de Audience Manager automatisch nieuwe, overeenkomstige, read-only [!UICONTROL segments] en kenmerken. U kunt de opslaglocatie van deze [!UICONTROL segments] uit Audience Manager. Alle wijzigingen die u echter uitvoert op de toegewezen Adobe Analytics [!UICONTROL segments] of rapportsuites weerspiegelen de Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] verschillen van [!DNL Adobe Analytics] [!UICONTROL segments]. Lezen [Segmenten begrijpen in Analytics en Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=nl-NL) voor een uitvoerige beschrijving van de verschillen.

## Op regels gebaseerd maken [!UICONTROL Segments] Met [!UICONTROL Segment Builder]

In tegenstelling tot traditionele pixels die in reactie op eenvoudige ja/nee-omstandigheden in brand steken, [!UICONTROL Segment Builder] maakt complexe [!UICONTROL segment] eisen. leuk [!UICONTROL traits], [!UICONTROL segments] gegevens evalueren met [!DNL Boolean] expressies ([!DNL AND], [!DNL OR], [!DNL NOT]), vergelijkingsoperatoren (groter dan, kleiner dan, gelijk aan, enz.) en recenentie-/frequentiecriteria. Deze functies helpen een doelgericht publiek te creëren [!UICONTROL segments] relevant voor uw bedrijfsbehoeften.

## Voordelen

[!UICONTROL Segments] verbetert op standaardpixel-gebaseerde publiekscreatie/segmenteringsprocessen omdat zij u laten:

* Bouw relevant, nuttig [!UICONTROL segments] met eerste- en derdekenmerken.
* Maak geavanceerde en complexe segmentatieregels met Booleaanse operatoren, vergelijkingsexpressies en criteria voor recentie en frequentie.
* Verzenden [!UICONTROL segment] gegevens aan een bestemmingspartner.
* De prestaties van de monitor met de rapporten van de Audience Manager.

>[!MORELIKETHIS]
>
>* [Signalen, eigenschappen en segmenten](../../reference/signal-trait-segment.md)

