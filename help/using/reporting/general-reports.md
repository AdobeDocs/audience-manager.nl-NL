---
description: Een Algemeen rapport keert prestatiesgegevens over eigenschappen, segmenten, en bestemmingen terug.
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: Algemene rapporten
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---

# Algemene rapporten{#general-reports}

Een [!UICONTROL General] rapport keert prestatiesgegevens over eigenschappen, segmenten, en bestemmingen terug.

## Overzicht {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] gebruikt [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) om user-group toestemmingen tot de [!UICONTROL General] rapporten uit te breiden. De gebruikers kunnen slechts die eigenschappen en segmenten in het melden zien dat zij toestemmingen aan mening hebben. Met de functie [!UICONTROL RBAC] kunt u bepalen welke rapportgegevens interne teams kunnen weergeven. Bijvoorbeeld, kan een agentschap dat verschillende adverteerderrekeningen beheert gebruiker-groep toestemmingen vormen zodat een team dat de rekening van Advertiser A beheert niet de rapportgegevens van Advertiser B kan zien.

Voer een [!UICONTROL General] -rapport uit wanneer u dat nodig hebt:

* De prestaties van het overzicht door eigenschap, segment, of bestemming.
* Houd afbeeldingen (totaal en uniek) bij intervallen van 1, 7, 14, 30, 60 en 90 dagen bij.
* Het totale en unieke aantal laden controleren.
* Vergelijk de prestaties van de kenmerken en segmenten.
* Identificeer sterke of slechte prestatieseigenschappen en segmenten, analyseer vraag, of vergelijk lading/brand gegevens met derderapporten.
* Gegevens (.csv-indeling) exporteren voor verdere analyse en uitwisseling.

De volgende afbeelding biedt een overzicht op hoog niveau van de belangrijkste elementen in het [!UICONTROL General] -rapport.

![](assets/general_reports.png)

1. Configureer de volgende opties:

   * **Type van Rapport:** selecteer het gewenste rapporttype (Spoor, Segment, of Bestemming).

   * **voor Datums door:** specificeer de datumwaaier voor het rapport.

2. Zoek naar een eigenschap, segment, of bestemming door naam of identiteitskaart
3. Sleep vanuit de mappenlijst de kenmerken, segmenten of doelen die u wilt rapporteren aan het deelvenster [!UICONTROL Selections] aan de rechterkant.
4. Genereer het rapport dat u wilt weergeven in een tabel die u kunt exporteren.

## Een algemeen rapport uitvoeren {#run-general-report}

In deze sectie wordt beschreven hoe u een [!UICONTROL General] -rapport uitvoert en tijd en andere prestatieopties instelt.

<!-- 

t_run_general_report.xml

 -->

1. Klik in het dashboard van **[!UICONTROL Analytics]** op **[!UICONTROL General Reports]** .
1. Selecteer het gewenste type in de vervolgkeuzelijst **[!UICONTROL Report Type]** : Trait, Segment of Doel.
1. *Voorwaardelijk* klik de datumdoos om een kalender te tonen, dan selecteer de beëindigende datum voor uw rapport als u een datum buiten vandaag wilt specificeren.
1. Zoek naar een eigenschap, segment, of bestemming door naam of identiteitskaart
1. Sleep vanuit de mappenlijst de kenmerken, segmenten of doelen die u wilt rapporteren aan het deelvenster [!UICONTROL Selections] aan de rechterkant.
1. Klik op **[!UICONTROL Run Report]**.

   De resultaten worden weergegeven in een tabel die kan worden geëxporteerd. Klik op de kolomkoppen om de resultaten in oplopende of aflopende volgorde te sorteren.
1. Selecteer de gewenste optieknop boven aan het rapport om gegevens te filteren op prestaties ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], of [!UICONTROL Total Trait Population]) of op tijd (1, 7, 14, 30, 60, of 90 dagwaaier).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] worden alleen berekend voor [!UICONTROL Rule-based Traits] .

1. *Facultatieve* klik **[!UICONTROL Export to CSV]**. Hiermee worden de [!UICONTROL Unique Trait Realizations] , [!UICONTROL Total Trait Realizations] en [!UICONTROL Total Trait Population] voor alle dagbereiken geëxporteerd.

## Algemene resultaten van rapporten {#general-reports-explained}

De getallen in de [!UICONTROL General Reports] worden direct gegenereerd vanuit onze [!UICONTROL User Profile Store] . De resultaten geven het aantal gebruikers weer dat [!DNL Audience Manager] in de back-end had op het moment dat deze rapportnummers werden gegenereerd.

* Deze aantallen omvatten bezoeker geen IDs met bovenmatig verkeer. Het verkeer van bots wordt gefilterd alvorens ons achterste systeem te bereiken. Ook, wordt wat bot verkeer verworpen tijdens een wekelijkse schoonmaakbaan die in het achterste gedeelte wordt in werking gesteld.
* Als u gegevens aan boord hebt via binnenkomende verwerking die van [!DNL Audience Manager] UUID is weggevaagd, en deze id&#39;s bevatten gebruikers die niet meer actief zijn in ons systeem, bereiken deze inactieve [!DNL Audience Manager] UUID&#39;s nooit de [!UICONTROL User Profile Store] en worden deze niet gerapporteerd.
* [!UICONTROL Total Trait Realizations] worden alleen berekend voor [!UICONTROL Rule-based Traits] .

## Algemene rapporten Resultaten voor sporen {#general-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een algemeen rapport uitvoert en **[!UICONTROL Trait]** selecteert als rapporttype.

Wanneer u de resultaten filtert met [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] is het aantal anonieme apparaatbezoekers dat de eigenschap aan hun profiel heeft toegevoegd binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Realization] is het totale aantal anonieme resultaten binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

![&#x200B; algemeen-rapport-eigenschap-apparaat &#x200B;](assets/general-report-traits-deviceid.png)

Wanneer u de resultaten filtert met [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] is het aantal geverifieerde bezoekers dat de eigenschap aan hun profiel heeft toegevoegd, binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Realization] is het totale aantal geverifieerde eigenschapresultaten binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

![&#x200B; algemeen-rapport-traits-dwars-apparaat &#x200B;](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## Algemene rapporten Resultaten voor segmenten {#general-report-results-segments}

De hieronder vermelde metriek is beschikbaar wanneer u een Algemeen rapport in werking stelt en **[!UICONTROL Segment]** als rapporttype selecteert:

### Realtime segmentpopulatie

Deze metrische waarde vertegenwoordigt het werkelijke aantal unieke bezoekers dat in real-time wordt gezien voor het opgegeven tijdbereik en dat in aanmerking kwam voor het segment op het moment dat ze door Audience Manager werden gezien.

### Totale segmentpopulatie

Deze metrische waarde vertegenwoordigt het totale aantal UUIDs van Audience Manager die voor het segment binnen de terugblik-achterperiode gekwalificeerd zijn u selecteerde. Uw 1 dag Totale Bevolking van het Segment vertegenwoordigt uw nauwkeurigste gebruikersbasis voor het richten.

>[!NOTE]
>
>Selecteer **[!UICONTROL Include Destination Mappings]** om een uitsplitsing van segmentpopulatie voor geactiveerde bestemmingen te zien.

In de onderstaande afbeelding ziet u de resultaten van het uitvoeren van een algemeen rapport voor het rapporttype Segment.

![](assets/general_reports_segment_metrics.png)

## Algemene rapporten Resultaten voor Doelen {#general-report-results-destinations}

De hieronder vermelde metriek is beschikbaar wanneer u een Algemeen rapport in werking stelt en **[!UICONTROL Destination]** als rapporttype selecteert:

**Bevolking van het segment in real time**

Deze metrische waarde vertegenwoordigt het werkelijke aantal unieke bezoekers dat in real-time wordt gezien voor het opgegeven tijdbereik en dat in aanmerking kwam voor het segment op het moment dat ze door Audience Manager werden gezien.

**Totale Bevolking van het Segment**

Deze metrische waarde vertegenwoordigt het totale aantal UUIDs van Audience Manager die tot een segment binnen de terugkijkperiode behoren, die naar een bestemming werden verzonden.

In de onderstaande afbeelding ziet u de resultaten van het uitvoeren van een algemeen rapport voor het rapporttype Doelen.

![](assets/general_reports_destinations.png)
