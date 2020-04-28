---
description: Een trendrapport retourneert trendgegevens over kenmerken en segmenten.
seo-description: Een trendrapport retourneert trendgegevens over kenmerken en segmenten.
seo-title: Trend Reports
solution: Audience Manager
title: Trend Reports
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 760818663ff3eb32c6de876c756697e1d9034369

---


# Trend Reports{#trend-reports}

Een trendrapport retourneert trendgegevens over kenmerken en segmenten.

## Overzicht {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] gebruikt [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) om gebruikers-groep toestemmingen tot de [!UICONTROL Trend] rapporten uit te breiden. De gebruikers kunnen slechts die eigenschappen en segmenten in het melden zien dat zij toestemmingen aan mening hebben. [!UICONTROL RBAC] Met functionaliteit kunt u bepalen welke rapportgegevens interne teams kunnen weergeven.

Bijvoorbeeld, kan een agentschap dat verschillende adverteerderrekeningen beheert gebruiker-groep toestemmingen vormen zodat een team dat de rekening van Advertiser A beheert niet de rapportgegevens van Advertiser B kan zien.

Voer een [!UICONTROL Trend] rapport uit wanneer u het volgende moet doen:

* De trendgegevens per kenmerk en segment evalueren.
* Traceer trends met intervallen van 1, 7, 14, 30, 60 en 90 dagen.
* Vergelijk de gedrags- en segmenttrends in de loop der tijd.
* Identificeer sterke of slechte prestatieseigenschappen en segmenten.
* Gegevens (.csv-indeling) exporteren voor verdere analyse en uitwisseling.

De volgende illustratie biedt een overzicht op hoog niveau van de belangrijkste elementen in het [!UICONTROL Trend] rapport.

![](assets/trend_reports.png)

1. Configureer de volgende opties:
   **Rapporttype:** Selecteer het gewenste rapporttype (Trait of Segment).
   **Datumbereik:** Geef het datumbereik voor het rapport op (begindatum en einddatum).
   **Weergaveinterval:** Geef het weergaveinterval op (intervallen van 1, 7, 14, 30, 60 en 90 dagen).
1. Zoek een kenmerk of segment op naam of id.
1. Sleep vanuit de mappenlijst de kenmerken of segmenten die u aan de rechterkant wilt melden naar het [!UICONTROL Selections] deelvenster.
1. Genereer het rapport dat u in grafische indeling wilt weergeven of exporteer het rapport naar de CSV-indeling.

## Een trendrapport uitvoeren {#run-trend-report}

Deze procedure beschrijft hoe te om een [!UICONTROL Trend] rapport in werking te stellen.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Klik in het **[!UICONTROL Analytics]** dashboard op **[!UICONTROL Trend Reports]**.
1. Selecteer het gewenste type in de **[!UICONTROL Report Type]** vervolgkeuzelijst: **[!UICONTROL Trait]** of **[!UICONTROL Segment]**.
1. Klik op de datumvakken om een kalender weer te geven en selecteer vervolgens de begin- en einddatum voor uw rapport.
1. Geef het weergaveinterval op: door 1, 7, 14, 30, 60 of 90 dagen.
1. Zoek een kenmerk of segment op naam of id.
1. Sleep vanuit de mappenlijst de kenmerken of segmenten die u aan de rechterkant wilt melden naar het [!UICONTROL Selections] deelvenster.
   * Voor beste prestaties, stel een [!UICONTROL Trend] rapport over minder dan 20 eigenschappen of segmenten tegelijkertijd in werking.
1. Klik **[!UICONTROL Graph Traits]** of **[!UICONTROL Graph Segments]**, afhankelijk van welk type van rapport u bekijkt (Treinen of Segmenten). Bij deze opties worden alle mappen en grafieken alleen genegeerd voor afzonderlijk geselecteerde kenmerken of segmenten.

   of

   Klik **[!UICONTROL Export to CSV]** om de eigenschap of segmentgegevens en alle omslagen in Csv formaat voor verdere analyse en het delen uit te voeren. Dit exporteert de [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]en [!UICONTROL Total Trait Population] voor alle dagbereiken.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] worden [!UICONTROL Rule-based Traits] alleen berekend.

1. (Optioneel) Plaats de muisaanwijzer op individuele kenmerken of segmenten om het aantal bezoeken en de datum voor elk gegevenspunt weer te geven. U kunt op de kolomkoppen in de tabel klikken om de resultaten in oplopende of aflopende volgorde te sorteren.

## Trend Report-resultaten voor sporen {#trend-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een rapport uitvoert [!UICONTROL Trend Report] en selecteert **[!UICONTROL Trait]** als rapporttype.

Wanneer het filtreren van de resultaten door [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal anonieme apparaatbezoekers dat de eigenschap binnen het geselecteerde tijdbereik aan hun profiel heeft toegevoegd.
* [!UICONTROL Total Trait Realization] is het totale aantal gerealiseerde anonieme eigenschap binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] Dit is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

Wanneer het filtreren van de resultaten door [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal geverifieerde bezoekers dat de eigenschap heeft toegevoegd aan hun profiel, binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Realization] is het totale aantal geverifieerde resultaten binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] Dit is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

![trendrapport-eigenschappen](assets/trend-report-traits.png)

Uit cijfers blijkt dat er voor die dag [!DNL Audience Manager] geen gegevens zijn verzameld. Lege vermeldingen geven aan dat de eigenschap niet bestond.

## Trend Report Resultaten voor segmenten {#segment-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een rapport uitvoert [!UICONTROL Trend Report] en selecteert **[!UICONTROL Segments]** als rapporttype.

* **[!UICONTROL Real-time Segment Population]**: het aantal bezoekers dat binnen het geselecteerde tijdbereik voor het segment in aanmerking kwam.
* **[!UICONTROL Total Segment Population]**: het totale aantal bezoekers dat voor het segment in aanmerking komt.

![trendverslagsegmenten](assets/trend-report-segments.png)