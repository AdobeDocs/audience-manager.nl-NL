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
source-wordcount: '303'
ht-degree: 1%

---

# Segmenten: Doel, Samenstelling en Regels {#segments-purpose-composition-and-rules}

Beschrijft [!UICONTROL segments], hun samenstellende delen, en regelverwezenlijking met [!UICONTROL Segment Builder].

## Doel van [!UICONTROL Segments]

Een *`segment`* (of een *`audience`* ) is een set gebruikers die gemeenschappelijke kenmerken delen. In Audience Manager maakt u [!UICONTROL segments] met regels voor de server. Met deze regels kunt u publieksgroepen samenstellen op basis van kenmerken van sitebezoekers, zoals:

* Gedrag;
* Demografische gegevens (leeftijd, geslacht, inkomen, enz.);
* Andere kenmerken die u kunt definiëren in de gebruikersinterface.

## [!UICONTROL Segment] Compositie

Een Audience Manager [!UICONTROL segment] is een serverregel die bestaat uit afzonderlijke of groepen kenmerken. De sporen worden samengesteld uit gegevenselementen genoemd zeer belangrijk-waardeparen. Samen met de regels die u instelt op [!UICONTROL segment] -niveau, bevatten deze sleutelwaardeparen de criteria die bezoekers in aanmerking laten komen voor doel en [!UICONTROL segment] -lidmaatschap.

## Overwegingen bij [!UICONTROL Adobe Analytics] [!UICONTROL Segment] Toewijzen

Wanneer u Adobe Analytics [!UICONTROL segments] toewijst of suites rapporteert aan uw Experience Cloud-organisatie, maakt Audience Manager automatisch nieuwe, overeenkomende, alleen-lezen [!UICONTROL segments] en kenmerken. U kunt de opslaglocatie van deze [!UICONTROL segments] niet bewerken of wijzigen vanuit Audience Manager. Elke wijziging die u uitvoert op de toegewezen Adobe Analytics [!UICONTROL segments] of de rapportsuites, is echter ook van toepassing op Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] verschilt van [!DNL Adobe Analytics] [!UICONTROL segments] . Lees [ Begrip Segmenten in Analytics en Audience Manager ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=nl-NL) voor een diepgaande beschrijving van de verschillen.

## Op regels gebaseerde [!UICONTROL Segments] maken met [!UICONTROL Segment Builder]

In tegenstelling tot traditionele pixels die worden geactiveerd als reactie op eenvoudige ja/nee-voorwaarden, kunt u met [!UICONTROL Segment Builder] complexe [!UICONTROL segment] -vereisten maken. Net als bij [!UICONTROL traits] evalueert [!UICONTROL segments] gegevens met behulp van [!DNL Boolean] -expressies ([!DNL AND] , [!DNL OR] , [!DNL NOT] ), vergelijkingsoperatoren (groter dan, kleiner dan, gelijk aan, enz.) en criteria voor recentie/frequentie. Deze functies helpen een doelgericht publiek [!UICONTROL segments] te creëren dat relevant is voor uw bedrijfsbehoeften.

## Voordelen

[!UICONTROL Segments] verbetert de standaardprocessen voor het maken/segmenteren van publiek op basis van pixels, omdat u hiermee:

* Bouw relevant, nuttig [!UICONTROL segments] met eerste en derdeattributen.
* Maak geavanceerde en complexe segmentatieregels met Booleaanse operatoren, vergelijkingsexpressies en criteria voor recentie en frequentie.
* Verzend [!UICONTROL segment] gegevens naar een bestemmingspartner.
* Prestaties bewaken met Audience Manager-rapporten.

>[!MORELIKETHIS]
>
>* [Signalen, eigenschappen en segmenten](../../reference/signal-trait-segment.md)
