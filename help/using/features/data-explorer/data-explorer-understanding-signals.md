---
description: Signalen zijn de kleinste informatieeenheid binnen de Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot Audience Manager die in trekkenregels moet worden gebruikt.
seo-description: Signalen zijn de kleinste informatieeenheid binnen de Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot Audience Manager die in trekkenregels moet worden gebruikt.
seo-title: Inzicht in Signalen
title: Inzicht in Signalen
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 2%

---


# Inzicht in Signalen

Signalen zijn de kleinste informatieeenheid binnen de Audience Manager. Zij vertegenwoordigen gebruikersinteractie of gebruikersactiviteit op uw online eigenschappen, en worden overgegaan tot Audience Manager die in trekregels moet worden gebruikt.

[!DNL Audience Manager] gebruikt sleutel-waardeparen om signalen te vertegenwoordigen. Het volgende signaal kan bijvoorbeeld aangeven dat een bezoeker een webpagina met elektronica heeft bereikt:

* `page = electronics`

Het [Signals dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) toont u veelvoudige types van signaalattributen die u kunt gebruiken om nieuwe eigenschappen tot stand te brengen. Hier is een gedetailleerde mening van de beschikbare signaaleigenschappen:

* *Sleutel-waarde* toont u het zeer belangrijk-waardepaar van het signaal dat door wordt ontvangen  [!DNL Audience Manager].
* *Het* getypte signaal beschrijft de categorie van elk signaal. Signalen behoren tot een van de volgende categorieën:
   * [Werkbare logbestanden](/help/using/integration/media-data-integration/actionable-log-files.md): real-time signalen die zijn ontvangen van uw logbestanden met mediaprestaties;
   * [!DNL Adobe Analytics]: real-time signalen die van uw  [!DNL Adobe Analytics] account worden ontvangen;
   * Algemene online gegevens: real-time gegevens die worden gegenereerd door uw publieksactiviteit en niet zijn opgenomen in actioneerbare logbestanden en [!DNL Adobe Analytics];
   * Boekregisters: gegevens die via batchgegevensoverdracht zijn ontvangen.
* *De* bron van het signaal hangt van het signaaltype af:
   * Voor signalen aan boord, is de signaalbron de naam van de gegevensbron.
   * Voor signalen uit [!DNL Adobe Analytics], zal de gegevensbron altijd een rapportreeks zijn.
   * Voor actionable logboekdossiers en algemene online gegevens, wordt geen signaalbroninformatie getoond.
* *Totaal aantal* tellers toont u het totale aantal tijden een signaal in real time  [!DNL Audience Manager] in de afgelopen 7 dagen werd ontvangen.
* *Opgenomen in* Traitsshows u of het signaal deel van om het even welk bezit uitmaakt. Klik op de pijl om de kenmerken weer te geven die het bijbehorende signaal bevatten. Voor signalen die geen deel uitmaken van enige eigenschap, verandert de kolomwaarde in [!UICONTROL Create Onboarded Trait] of [!UICONTROL Create Rule-Based Trait].

## Vernieuwingsfrequentie signaalgegevens

Vanwege de grote hoeveelheid gegevens die Audience Manager dagelijks verwerkt, vernieuwt [!UICONTROL Data Explorer] de weergegeven signaalgegevens met vaste tijdsintervallen, afhankelijk van het signaaltype:

* De gegevens van het signaal in real time (actionable logboekdossiers, [!DNL Adobe Analytics] gegevens, en algemene online gegevens) worden verfrist om de 4 tot 6 uur.
* De gegevens van het aan boord gebrachte signaal worden elke 24 uur vernieuwd.

## Verwante concepten

[Signalen, eigenschappen en segmenten](/help/using/reference/signal-trait-segment.md)