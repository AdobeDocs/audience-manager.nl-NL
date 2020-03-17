---
description: Signalen zijn de kleinste gegevenseenheid binnen Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot de Manager van het Publiek om in trekkenregels worden gebruikt.
seo-description: Signalen zijn de kleinste gegevenseenheid binnen Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot de Manager van het Publiek om in trekkenregels worden gebruikt.
seo-title: Signalen begrijpen
title: Signalen begrijpen
uuid: 04a0554e-954e-484a-8838-9161ef416872
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signalen begrijpen

Signalen zijn de kleinste gegevenseenheid binnen Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot de Manager van het Publiek die in trekregels moet worden gebruikt.

[!DNL Audience Manager] gebruikt sleutel-waardeparen om signalen te vertegenwoordigen. Het volgende signaal kan bijvoorbeeld aangeven dat een bezoeker een webpagina met elektronica heeft bereikt:

* `page = electronics`

Het dashboard [](../../features/data-explorer/data-explorer-signals-dashboard.md) Signalen toont u veelvoudige types van signaalattributen die u kunt gebruiken om nieuwe eigenschappen tot stand te brengen. Hier is een gedetailleerde mening van de beschikbare signaaleigenschappen:

* *Sleutel-waarde paar* toont u het zeer belangrijk-waardepaar van het signaal dat door wordt ontvangen [!DNL Audience Manager].
* *Het signaaltype* beschrijft de categorie van elk signaal. Signalen behoren tot een van de volgende categorieën:
   * [Werkbare logbestanden](/help/using/integration/media-data-integration/actionable-log-files.md): real-time signalen die zijn ontvangen van uw logbestanden met mediaprestaties;
   * [!DNL Adobe Analytics]: real-time signalen die van uw [!DNL Adobe Analytics] account worden ontvangen;
   * Algemene online gegevens: real-time gegevens die door uw publieksactiviteit worden geproduceerd en niet inbegrepen in actionable logboekdossiers en [!DNL Adobe Analytics];
   * Boekregisters: gegevens die via batchgegevensoverdracht zijn ontvangen.
* *De Bron* van het signaal hangt van het signaaltype af:
   * Voor signalen aan boord, is de signaalbron de naam van de gegevensbron.
   * Voor signalen uit [!DNL Adobe Analytics], zal de gegevensbron altijd een rapportreeks zijn.
   * Voor actionable logboekdossiers en algemene online gegevens, wordt geen signaalbroninformatie getoond.
* *De Totale Tellingen* toont u het totale aantal tijden een signaal in real time werd ontvangen door [!DNL Audience Manager] in de afgelopen 7 dagen.
* *In Traits* ziet u of het signaal deel uitmaakt van een eigenschap. Klik op de pijl om de kenmerken weer te geven die het bijbehorende signaal bevatten. Voor signalen die geen deel uitmaken van enig bezit, verandert de kolomwaarde in [!UICONTROL Create Onboarded Trait] of [!UICONTROL Create Rule-Based Trait].

## Vernieuwingsfrequentie signaalgegevens

Vanwege de grote hoeveelheid gegevens die Audience Manager dagelijks verwerkt, [!UICONTROL Data Explorer] vernieuwt u de weergegeven signaalgegevens met vaste tijdsintervallen, afhankelijk van het signaaltype:

* Signaalgegevens in real time (actionable logboekdossiers, [!DNL Adobe Analytics] gegevens, en algemene online gegevens) worden verfrist om de 4 tot 6 uur.
* De gegevens van het aan boord gebrachte signaal worden elke 24 uur vernieuwd.

## Verwante concepten

[Signalen, Traits en Segmenten](/help/using/reference/signal-trait-segment.md)