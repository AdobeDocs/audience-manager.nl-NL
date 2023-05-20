---
description: Signalen zijn de kleinste informatieeenheid binnen de Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot Audience Manager die in trekkenregels moet worden gebruikt.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Inzicht in Signalen
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 2%

---

# Inzicht in Signalen

Signalen zijn de kleinste informatieeenheid binnen de Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot Audience Manager die in trekregels moet worden gebruikt.

[!DNL Audience Manager] gebruikt sleutel-waardeparen om signalen te vertegenwoordigen. Het volgende signaal kan bijvoorbeeld aangeven dat een bezoeker een webpagina met elektronica heeft bereikt:

* `page = electronics`

De [Signaaldashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) toont u veelvoudige types van signaalattributen die u kunt gebruiken om nieuwe eigenschappen tot stand te brengen. Hier is een gedetailleerde mening van de beschikbare signaaleigenschappen:

* *Sleutelwaardepaar* toont u het zeer belangrijk-waardepaar van het signaal dat door wordt ontvangen [!DNL Audience Manager].
* *Type signaal* beschrijft de categorie van elk signaal. Signalen behoren tot een van de volgende categorieën:
   * [Werkbare logbestanden](/help/using/integration/media-data-integration/actionable-log-files.md): real-time signalen die zijn ontvangen van uw logbestanden met mediaprestaties;
   * [!DNL Adobe Analytics]: signalen in real time die van uw worden ontvangen [!DNL Adobe Analytics] rekening;
   * Algemene online gegevens: real-time gegevens die worden gegenereerd door uw publieksactiviteit en niet zijn opgenomen in actioneerbare logbestanden en [!DNL Adobe Analytics];
   * Boekregisters: gegevens die via batchgegevensoverdracht zijn ontvangen.
* *Signaalbron* is afhankelijk van het signaaltype:
   * Voor signalen aan boord, is de signaalbron de naam van de gegevensbron.
   * Voor signalen die afkomstig zijn van [!DNL Adobe Analytics], zal de gegevensbron altijd een rapportreeks zijn.
   * Voor actionable logboekdossiers en algemene online gegevens, wordt geen signaalbroninformatie getoond.
* *Totaal aantal tellingen* toont u het totale aantal tijden een signaal in real time werd ontvangen door [!DNL Audience Manager] in de afgelopen 7 dagen.
* *Opgenomen in treinen* toont u of het signaal deel van om het even welk bezit uitmaakt. Klik op de pijl om de kenmerken weer te geven die het bijbehorende signaal bevatten. Voor signalen die geen deel uitmaken van enige eigenschap, verandert de kolomwaarde in [!UICONTROL Create Onboarded Trait] of [!UICONTROL Create Rule-Based Trait].

## Vernieuwingsfrequentie signaalgegevens

Gezien de grote hoeveelheid gegevens die Audience Manager dagelijks verwerkt, [!UICONTROL Data Explorer] vernieuwt de getoonde signaalgegevens bij vaste tijdintervallen, afhankelijk van het signaaltype:

* Signaalgegevens in realtime (uitvoerbare logbestanden) [!DNL Adobe Analytics] gegevens, en algemene online gegevens) om de 4 tot 6 uur worden vernieuwd.
* De gegevens van het aan boord gebrachte signaal worden elke 24 uur vernieuwd.

## Verwante concepten

[Signalen, eigenschappen en segmenten](/help/using/reference/signal-trait-segment.md)
