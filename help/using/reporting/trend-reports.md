---
description: Een trendrapport retourneert trendgegevens over kenmerken en segmenten.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: Trend Reports
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 42f9b32edcde423369f7e8254b04fdc6162130d0
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Trend Reports{#trend-reports}

Een trendrapport retourneert trendgegevens over kenmerken en segmenten.

## Overzicht {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] gebruikt [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) om user-group toestemmingen tot de [!UICONTROL Trend] rapporten uit te breiden. De gebruikers kunnen slechts die eigenschappen en segmenten in het melden zien dat zij toestemmingen aan mening hebben. Met de functie [!UICONTROL RBAC] kunt u bepalen welke rapportgegevens interne teams kunnen weergeven.

Bijvoorbeeld, kan een agentschap dat verschillende adverteerderrekeningen beheert gebruiker-groep toestemmingen vormen zodat een team dat de rekening van Advertiser A beheert niet de rapportgegevens van Advertiser B kan zien.

Voer een [!UICONTROL Trend] -rapport uit wanneer u dat nodig hebt:

* De trendgegevens per kenmerken en segmenten evalueren.
* Traceer trends met intervallen van 1, 7, 14, 30, 60 en 90 dagen.
* Vergelijk de gedrags- en segmenttrends in de loop der tijd.
* Identificeer sterke of slechte prestatieseigenschappen en segmenten.
* Gegevens (.csv-indeling) exporteren voor verdere analyse en uitwisseling.

De volgende afbeelding biedt een overzicht op hoog niveau van de belangrijkste elementen in het [!UICONTROL Trend] -rapport.

![](assets/trend_reports.png)

1. Configureer de volgende opties:
   **Type van Rapport:** selecteer het gewenste rapporttype (Spoor of Segment).
   **de Waaier van de Datum:** specificeer de datumwaaier voor het rapport (begindatum en einddatum).
   **Interval van de Vertoning:** specificeer het vertoningsinterval (1, 7, 14, 30, 60, en 90 dagintervallen).
1. Zoek een kenmerk of segment op naam of id.
1. Sleep vanuit de mappenlijst de kenmerken of segmenten die u wilt rapporteren naar het deelvenster [!UICONTROL Selections] aan de rechterkant.
1. Genereer het rapport dat u in grafische indeling wilt weergeven of exporteer het rapport naar de CSV-indeling.

## Een trendrapport uitvoeren {#run-trend-report}

In deze procedure wordt beschreven hoe u een [!UICONTROL Trend] -rapport uitvoert.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Klik in het dashboard van **[!UICONTROL Analytics]** op **[!UICONTROL Trend Reports]** .
1. Selecteer in de vervolgkeuzelijst **[!UICONTROL Report Type]** het gewenste type: **[!UICONTROL Trait]** of **[!UICONTROL Segment]** .
1. Klik op de datumvakken om een kalender weer te geven en selecteer vervolgens de begin- en einddatum voor uw rapport.
1. Geef het weergaveinterval op: 1, 7, 14, 30, 60 of 90 dagen.
1. Zoek een kenmerk of segment op naam of id.
1. Sleep vanuit de mappenlijst de kenmerken of segmenten die u wilt rapporteren naar het deelvenster [!UICONTROL Selections] aan de rechterkant.
   * Voer voor de beste prestaties een [!UICONTROL Trend] -rapport uit over minder dan 20 kenmerken of segmenten tegelijk.
1. Klik op **[!UICONTROL Graph Traits]** of **[!UICONTROL Graph Segments]** , afhankelijk van het type rapport dat u bekijkt (Traits of Segmenten). Bij deze opties worden alle mappen en grafieken alleen genegeerd voor afzonderlijk geselecteerde kenmerken of segmenten.

   of

   Klik op **[!UICONTROL Export to CSV]** om de gegevens van de eigenschap of het segment en alle mappen in CSV-indeling te exporteren voor verdere analyse en delen. Hiermee worden de [!UICONTROL Unique Trait Realizations] , [!UICONTROL Total Trait Realizations] en [!UICONTROL Total Trait Population] voor alle dagbereiken geëxporteerd.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] worden alleen berekend voor [!UICONTROL Rule-based Traits] .

1. (Optioneel) Plaats de muisaanwijzer op individuele kenmerken of segmenten om het aantal bezoeken en de datum voor elk gegevenspunt weer te geven. U kunt op de kolomkoppen in de tabel klikken om de resultaten in oplopende of aflopende volgorde te sorteren.

## Trend Report-resultaten voor sporen {#trend-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een [!UICONTROL Trend Report] uitvoert en **[!UICONTROL Trait]** selecteert als rapporttype.

Wanneer u de resultaten filtert met [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] is het aantal anonieme apparaatbezoekers dat de eigenschap aan hun profiel heeft toegevoegd binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Realization] is het totale aantal realisaties van anonieme kenmerken binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

Wanneer u de resultaten filtert met [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] is het aantal geverifieerde bezoekers dat de eigenschap aan hun profiel heeft toegevoegd, binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Realization] is het totale aantal geverifieerde eigenschapresultaten binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

![ trend-rapport-eigenschappen ](assets/trend-report-traits.png)

De waarden geven aan dat [!DNL Audience Manager] geen gegevens heeft verzameld voor die dag. Lege vermeldingen geven aan dat de eigenschap niet bestond.

Bekijk de onderstaande video voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

[ Begrijpend dwars-apparatenmetriek in Audience Manager ](https://experienceleague.adobe.com/en/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager)

## Trend Report Resultaten voor segmenten {#segment-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een [!UICONTROL Trend Report] uitvoert en **[!UICONTROL Segments]** selecteert als rapporttype.

* **[!UICONTROL Real-time Segment Population]**: het aantal bezoekers dat in aanmerking kwam voor het segment binnen het geselecteerde tijdbereik.
* **[!UICONTROL Total Segment Population]**: het totale aantal bezoekers dat in aanmerking kwam voor het segment.

![ trend-rapport-segmenten ](assets/trend-report-segments.png)
