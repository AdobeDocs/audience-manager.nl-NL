---
description: Signalen zijn de kleinste informatieeenheid binnen Audience Manager. Ze vertegenwoordigen gebruikersinteracties of gebruikersactiviteit op uw online eigenschappen en worden doorgegeven aan Audience Manager voor gebruik in de regels voor het gedrag.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Signalen begrijpen
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Signalen begrijpen

Signalen zijn de kleinste informatieeenheid binnen Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot Audience Manager om in gedragsregels worden gebruikt.

[!DNL Audience Manager] gebruikt sleutel-waardeparen om signalen te vertegenwoordigen. Het volgende signaal kan bijvoorbeeld aangeven dat een bezoeker een webpagina met elektronica heeft bereikt:

* `page = electronics`

Het [ dashboard van Signalen ](../../features/data-explorer/data-explorer-signals-dashboard.md) toont u veelvoudige types van signaalattributen die u kunt gebruiken om nieuwe eigenschappen tot stand te brengen. Hier is een gedetailleerde mening van de beschikbare signaaleigenschappen:

* *zeer belangrijk-waardepaar* toont u het zeer belangrijk-waardepaar van het signaal dat door [!DNL Audience Manager] wordt ontvangen.
* *Signaal type* beschrijft de categorie van elk signaal. Signalen behoren tot een van de volgende categorieën:
   * [ Handelbare logboekdossiers ](/help/using/integration/media-data-integration/actionable-log-files.md): signalen in real time die van uw het logboekdossiers van mediaprestaties worden ontvangen;
   * [!DNL Adobe Analytics]: real-time signalen die worden ontvangen van uw [!DNL Adobe Analytics] -account;
   * Algemene online gegevens: real-time gegevens die door uw publieksactiviteit worden geproduceerd en niet inbegrepen in actionable logboekdossiers en [!DNL Adobe Analytics];
   * Aan boord genomen records: gegevens die via batchgegevensoverdracht zijn ontvangen.
* *Source van het Signaal* hangt van het signaaltype af:
   * Voor signalen aan boord, is de signaalbron de naam van de gegevensbron.
   * Voor signalen die afkomstig zijn uit [!DNL Adobe Analytics] , is de gegevensbron altijd een rapportsuite.
   * Voor actionable logboekdossiers en algemene online gegevens, wordt geen informatie van de signaalbron getoond.
* *Totale Tellingen* toont u het totale aantal tijden een signaal in real time door [!DNL Audience Manager] in de afgelopen 7 dagen werd ontvangen.
* *inbegrepen in Bezit* toont u of het signaal deel van om het even welk bezit uitmaakt. Klik op de pijl om de kenmerken weer te geven die het bijbehorende signaal bevatten. Voor signalen die geen deel uitmaken van enige eigenschap, verandert de kolomwaarde in [!UICONTROL Create Onboarded Trait] of [!UICONTROL Create Rule-Based Trait].

## Vernieuwingsfrequentie signaalgegevens

Vanwege de grote hoeveelheid gegevens die Audience Manager dagelijks verwerkt, vernieuwt [!UICONTROL Data Explorer] de weergegeven signaalgegevens met vaste tijdsintervallen, afhankelijk van het signaaltype:

* Signaalgegevens in real time (actionable logboekdossiers, [!DNL Adobe Analytics] gegevens, en algemene online gegevens) worden verfrist om de 4 tot 6 uur.
* De gegevens van het aan boord gebrachte signaal worden elke 24 uur vernieuwd.

## Verwante concepten

[Signalen, eigenschappen en segmenten](/help/using/reference/signal-trait-segment.md)
