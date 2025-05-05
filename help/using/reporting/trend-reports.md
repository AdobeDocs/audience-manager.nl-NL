---
description: Een trendrapport retourneert trendgegevens over kenmerken en segmenten.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: Trendrapporten
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---

# Trendrapporten{#trend-reports}

Een trendrapport retourneert trendgegevens over kenmerken en segmenten.

## Overzicht {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] gebruik [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) om gebruikersgroepmachtigingen uit te breiden naar de [!UICONTROL Trend] rapporten. De gebruikers kunnen slechts die eigenschappen en segmenten in het melden zien dat zij toestemmingen aan mening hebben. [!UICONTROL RBAC] Met functionaliteit kunt u bepalen welke rapportgegevens interne teams kunnen weergeven.

Bijvoorbeeld, kan een agentschap dat verschillende adverteerderrekeningen beheert gebruiker-groep toestemmingen vormen zodat een team dat de rekening van Advertiser A beheert niet de rapportgegevens van Advertiser B kan zien.

Een [!UICONTROL Trend] melden wanneer u het volgende moet doen:

* De trendgegevens per kenmerken en segmenten evalueren.
* Traceer trends met intervallen van 1, 7, 14, 30, 60 en 90 dagen.
* Vergelijk de gedrags- en segmenttrends in de loop der tijd.
* Identificeer sterke of slechte prestatieseigenschappen en segmenten.
* Gegevens (.csv-indeling) exporteren voor verdere analyse en uitwisseling.

In de volgende afbeelding ziet u een overzicht op hoog niveau van de belangrijkste elementen in het dialoogvenster [!UICONTROL Trend] verslag.

![](assets/trend_reports.png)

1. Configureer de volgende opties:
   **Rapporttype:** Selecteer het gewenste rapporttype (Trait of Segment).
   **Datumbereik:** Geef het datumbereik voor het rapport op (begindatum en einddatum).
   **Weergaveinterval:** Geef het weergaveinterval op (intervallen van 1, 7, 14, 30, 60 en 90 dagen).
1. Zoek een kenmerk of segment op naam of id.
1. Sleep vanuit de mappenlijst de kenmerken of segmenten die u aan de [!UICONTROL Selections] aan de rechterkant.
1. Genereer het rapport dat u in grafische indeling wilt weergeven of exporteer het rapport naar de CSV-indeling.

## Een trendrapport uitvoeren {#run-trend-report}

In deze procedure wordt beschreven hoe u een [!UICONTROL Trend] verslag.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In de **[!UICONTROL Analytics]** dashboard, klik **[!UICONTROL Trend Reports]**.
1. Van de **[!UICONTROL Report Type]** Selecteer het gewenste type in de vervolgkeuzelijst: **[!UICONTROL Trait]** of **[!UICONTROL Segment]**.
1. Klik op de datumvakken om een kalender weer te geven en selecteer vervolgens de begin- en einddatum voor uw rapport.
1. Geef het weergaveinterval op: door 1, 7, 14, 30, 60 of 90 dagen.
1. Zoek een kenmerk of segment op naam of id.
1. Sleep vanuit de mappenlijst de kenmerken of segmenten die u aan de [!UICONTROL Selections] aan de rechterkant.
   * Voor de beste prestaties voert u een [!UICONTROL Trend] minder dan 20 kenmerken of segmenten tegelijk rapporteren.
1. Klikken **[!UICONTROL Graph Traits]** of **[!UICONTROL Graph Segments]**, afhankelijk van het type rapport dat u bekijkt (Traits of Segmenten). Bij deze opties worden alle mappen en grafieken alleen genegeerd voor afzonderlijk geselecteerde kenmerken of segmenten.

   of

   Klikken **[!UICONTROL Export to CSV]** om de eigenschap of segmentgegevens en alle omslagen in CSV formaat voor verdere analyse en het delen uit te voeren. Dit exporteert de [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], en [!UICONTROL Total Trait Population] voor alle dagbereiken.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] worden berekend voor [!UICONTROL Rule-based Traits] alleen.

1. (Optioneel) Plaats de muisaanwijzer op individuele kenmerken of segmenten om het aantal bezoeken en de datum voor elk gegevenspunt weer te geven. U kunt op de kolomkoppen in de tabel klikken om de resultaten in oplopende of aflopende volgorde te sorteren.

## Trend Report-resultaten voor sporen {#trend-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een [!UICONTROL Trend Report] en selecteert u **[!UICONTROL Trait]** als het rapporttype.

Wanneer het filtreren van de resultaten door [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal anonieme apparaatbezoekers dat de eigenschap binnen het geselecteerde tijdbereik aan hun profiel heeft toegevoegd.
* [!UICONTROL Total Trait Realization] is het totale aantal gerealiseerde anonieme eigenschap binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] Dit is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

Wanneer het filtreren van de resultaten door [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal geverifieerde bezoekers dat de eigenschap heeft toegevoegd aan hun profiel, binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Realization] is het totale aantal geverifieerde resultaten binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] Dit is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

![trendrapport-eigenschappen](assets/trend-report-traits.png)

Zeroes geven aan dat [!DNL Audience Manager] heeft voor die dag geen gegevens verzameld. Lege vermeldingen geven aan dat de eigenschap niet bestond.

Bekijk de onderstaande video voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=nl-NL)

## Trend Report Resultaten voor segmenten {#segment-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een [!UICONTROL Trend Report] en selecteert u **[!UICONTROL Segments]** als het rapporttype.

* **[!UICONTROL Real-time Segment Population]**: het aantal bezoekers dat binnen het geselecteerde tijdbereik voor het segment in aanmerking kwam.
* **[!UICONTROL Total Segment Population]**: het totale aantal bezoekers dat voor het segment in aanmerking komt.

![trendverslagsegmenten](assets/trend-report-segments.png)
