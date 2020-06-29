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
ht-degree: 0%

---


# Segmenten: Doel, samenstelling en regels {#segments-purpose-composition-and-rules}

Beschrijft [!UICONTROL segments], hun samenstellende delen, en lijnverwezenlijking met [!UICONTROL Segment Builder].

## Doel van [!UICONTROL Segments]

Een *`segment`* (of een *`audience`*) is een set gebruikers die gemeenschappelijke kenmerken delen. In Audience Manager, creeert u [!UICONTROL segments] met server-zijregels. Met deze regels kunt u publieksgroepen samenstellen op basis van kenmerken van sitebezoekers, zoals:

* Gedrag;
* Demografische gegevens (leeftijd, geslacht, inkomen, enz.);
* Andere kenmerken die u kunt definiëren in de gebruikersinterface.

## [!UICONTROL Segment] Samenstelling

Een Audience Manager [!UICONTROL segment] is een server-zijregel die uit individuele of groepen eigenschappen bestaat. De sporen worden samengesteld uit gegevenselementen genoemd zeer belangrijk-waardeparen. Deze sleutelwaardeparen bevatten samen met de regels die u instelt op het [!UICONTROL segment] [!UICONTROL segment] niveau, de criteria die bezoekers in aanmerking komen voor deelname en deelname.

## Overwegingen bij [!UICONTROL Adobe Analytics][!UICONTROL Segment] toewijzen

Wanneer u Adobe Analytics toewijst [!UICONTROL segments] of pakketten rapporteert aan uw Experience Cloud-organisatie, maakt Audience Manager automatisch nieuwe, overeenkomende, alleen-lezen [!UICONTROL segments] en kenmerken. U kunt de opslaglocatie van deze bestanden niet bewerken of wijzigen [!UICONTROL segments] vanuit Audience Manager. Elke wijziging die u uitvoert op uw toegewezen Adobe Analytics [!UICONTROL segments] of rapportsuites, is echter in Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] verschilt van [!DNL Adobe Analytics][!UICONTROL segments]. Lees Segmenten [begrijpen in Analytics en Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) voor een diepgaande beschrijving van de verschillen.

## Regels maken [!UICONTROL Segments] met [!UICONTROL Segment Builder]

In tegenstelling tot traditionele pixels die in reactie op eenvoudige ja/nee-voorwaarden worden geactiveerd, kunt u [!UICONTROL Segment Builder] complexe [!UICONTROL segment] vereisten maken. Net als [!UICONTROL traits], [!UICONTROL segments] evalueer gegevens gebruikend [!DNL Boolean] uitdrukkingen ([!DNL AND], [!DNL OR], [!DNL NOT]), vergelijkingsexploitanten (groter dan, minder dan, gelijk aan, enz.), en recenentie/frequentiecriteria. Deze functies helpen een doelgericht publiek te creëren dat [!UICONTROL segments] relevant is voor uw bedrijfsbehoeften.

## Voordelen

[!UICONTROL Segments] verbetert op standaardpixel-gebaseerde publiekscreatie/segmenteringsprocessen omdat zij u laten:

* Bouw relevant, nuttig [!UICONTROL segments] met eerste en derdeeigenschappen.
* Maak geavanceerde en complexe segmentatieregels met Booleaanse operatoren, vergelijkingsexpressies en criteria voor recentie en frequentie.
* Verzend [!UICONTROL segment] gegevens naar een bestemmingspartner.
* De prestaties van de monitor met de rapporten van de Audience Manager.

>[!MORELIKETHIS]
>
>* [Signalen, Traits en Segmenten](../../reference/signal-trait-segment.md)

