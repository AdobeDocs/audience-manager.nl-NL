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
source-wordcount: '847'
ht-degree: 0%

---

# Algemene rapporten{#general-reports}

A [!UICONTROL General] het rapport keert prestatiesgegevens over eigenschappen, segmenten, en bestemmingen terug.

## Overzicht {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] gebruik [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) om gebruikersgroepmachtigingen uit te breiden naar de [!UICONTROL General] rapporten. De gebruikers kunnen slechts die eigenschappen en segmenten in het melden zien dat zij toestemmingen aan mening hebben. [!UICONTROL RBAC] Met functionaliteit kunt u bepalen welke rapportgegevens interne teams kunnen weergeven. Bijvoorbeeld, kan een agentschap dat verschillende adverteerderrekeningen beheert gebruiker-groep toestemmingen vormen zodat een team dat de rekening van Advertiser A beheert niet de rapportgegevens van Advertiser B kan zien.

Een [!UICONTROL General] melden wanneer u het volgende moet doen:

* De prestaties van het overzicht door eigenschap, segment, of bestemming.
* Houd afbeeldingen (totaal en uniek) bij intervallen van 1, 7, 14, 30, 60 en 90 dagen bij.
* Het totale en unieke aantal laden controleren.
* Vergelijk de prestaties van de kenmerken en segmenten.
* Identificeer sterke of slechte prestatieseigenschappen en segmenten, analyseer vraag, of vergelijk lading/brand gegevens met derderapporten.
* Gegevens (.csv-indeling) exporteren voor verdere analyse en uitwisseling.

In de volgende afbeelding ziet u een overzicht op hoog niveau van de belangrijkste elementen in het dialoogvenster [!UICONTROL General] verslag.

![](assets/general_reports.png)

1. Configureer de volgende opties:

   * **Rapporttype:** Selecteer het gewenste rapporttype (Trait, Segment, of Bestemming).

   * **Voor datums tot en met:** Geef het datumbereik voor het rapport op.

2. Zoek naar een eigenschap, segment, of bestemming door naam of identiteitskaart
3. Sleep vanuit de mappenlijst de kenmerken, segmenten of doelen die u aan de [!UICONTROL Selections] aan de rechterkant.
4. Genereer het rapport dat u wilt weergeven in een tabel die kan worden geëxporteerd.

## Een algemeen rapport uitvoeren {#run-general-report}

In deze sectie wordt beschreven hoe u een [!UICONTROL General] rapport en vastgestelde tijd en andere prestatiesopties.

<!-- 

t_run_general_report.xml

 -->

1. In de **[!UICONTROL Analytics]** dashboard, klik **[!UICONTROL General Reports]**.
1. Van de **[!UICONTROL Report Type]** Selecteer het gewenste type in de vervolgkeuzelijst: Trait, Segment of Doel.
1. *Voorwaardelijk* Klik op het datumvak om een kalender weer te geven en selecteer vervolgens de einddatum voor uw rapport als u een andere datum dan vandaag wilt opgeven.
1. Zoek naar een eigenschap, segment, of bestemming door naam of identiteitskaart
1. Sleep vanuit de mappenlijst de kenmerken, segmenten of doelen die u aan de [!UICONTROL Selections] aan de rechterkant.
1. Klik op **[!UICONTROL Run Report]**.

   De resultaten worden weergegeven in een tabel die kan worden geëxporteerd. Klik op de kolomkoppen om de resultaten in oplopende of aflopende volgorde te sorteren.
1. Selecteer de gewenste optieknoop bij de bovenkant van het rapport aan filtergegevens door prestaties ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], of [!UICONTROL Total Trait Population]) of op tijd (bereik van 1, 7, 14, 30, 60 of 90 dagen).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] worden berekend voor [!UICONTROL Rule-based Traits] alleen.

1. *Optioneel* Klikken **[!UICONTROL Export to CSV]**. Dit exporteert de [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], en [!UICONTROL Total Trait Population] voor alle dagbereiken.

## Algemene resultaten van rapporten {#general-reports-explained}

De getallen in de [!UICONTROL General Reports] rechtstreeks worden gegenereerd vanuit onze [!UICONTROL User Profile Store]. De resultaten geven het aantal gebruikers weer dat [!DNL Audience Manager] in de achterzijde op het moment dat deze rapportagenummers werden gegenereerd.

* Deze aantallen omvatten bezoeker geen IDs met bovenmatig verkeer. Het verkeer van bots wordt gefilterd alvorens ons achterste systeem te bereiken. Ook, wordt wat bot verkeer verworpen tijdens een wekelijkse schoonmaakbaan die in het achterste gedeelte wordt in werking gesteld.
* Als u gegevens aan boord hebt via binnenkomende verwerking, moet u de [!DNL Audience Manager] UUID, en deze id&#39;s bevatten gebruikers die niet meer actief zijn in ons systeem, deze inactieve gebruikers [!DNL Audience Manager] UUID&#39;s bereiken nooit de [!UICONTROL User Profile Store] en worden niet gerapporteerd.
* [!UICONTROL Total Trait Realizations] worden berekend voor [!UICONTROL Rule-based Traits] alleen.

## Algemene rapporten Resultaten voor sporen {#general-report-results-traits}

De onderstaande filters zijn beschikbaar wanneer u een algemeen rapport uitvoert en **[!UICONTROL Trait]** als het rapporttype.

Wanneer het filtreren van de resultaten door [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal anonieme apparaatbezoekers dat de eigenschap binnen het geselecteerde tijdbereik aan hun profiel heeft toegevoegd.
* [!UICONTROL Total Trait Realization] is het totale aantal anonieme eigenlijke realisaties binnen de geselecteerde tijdwaaier.
* [!UICONTROL Total Trait Population] Dit is het aantal anonieme apparaatbezoekers dat deze eigenschap in hun profiel heeft.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Wanneer het filtreren van de resultaten door [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] Dit is het aantal geverifieerde bezoekers dat de eigenschap heeft toegevoegd aan hun profiel, binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Realization] is het totale aantal geverifieerde resultaten binnen het geselecteerde tijdbereik.
* [!UICONTROL Total Trait Population] Dit is het aantal geverifieerde bezoekers dat deze eigenschap in hun profiel heeft.

![algemeen-rapport-eigenschappen-dwars-apparaat](assets/general-report-traits-cross-device.png)

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

De onderstaande cijfers zijn beschikbaar wanneer u een algemeen rapport uitvoert en **[!UICONTROL Segment]** als rapporttype:

### Realtime segmentpopulatie

Deze metrisch vertegenwoordigt het daadwerkelijke aantal unieke bezoekers die in real time voor de gespecificeerde tijdwaaier worden gezien en die voor het segment op het ogenblik gekwalificeerd waren dat zij door Audience Manager werden gezien.

### Totale segmentpopulatie

Deze metrisch vertegenwoordigt het totale aantal Audience Manager UUIDs die voor het segment binnen de terugblik-achterperiode gekwalificeerd zijn u selecteerde. Uw 1 dag Totale Bevolking van het Segment vertegenwoordigt uw nauwkeurigste gebruikersbasis voor het richten.

>[!NOTE]
>
>Selecteren **[!UICONTROL Include Destination Mappings]** een uitsplitsing te zien van de segmentpopulatie voor geactiveerde bestemmingen.

In de onderstaande afbeelding ziet u de resultaten van het uitvoeren van een algemeen rapport voor het rapporttype Segment.

![](assets/general_reports_segment_metrics.png)

## Algemene rapporten Resultaten voor Doelen {#general-report-results-destinations}

De onderstaande cijfers zijn beschikbaar wanneer u een algemeen rapport uitvoert en **[!UICONTROL Destination]** als rapporttype:

**Realtime segmentpopulatie**

Deze metrisch vertegenwoordigt het daadwerkelijke aantal unieke bezoekers die in real time voor de gespecificeerde tijdwaaier worden gezien en die voor het segment op het ogenblik gekwalificeerd waren dat zij door Audience Manager werden gezien.

**Totale segmentpopulatie**

Deze metrisch vertegenwoordigt het totale aantal Audience Manager UUIDs die tot een segment binnen de terugkijkperiode behoren, die werden verzonden naar een bestemming.

In de onderstaande afbeelding ziet u de resultaten van het uitvoeren van een algemeen rapport voor het rapporttype Doelen.

![](assets/general_reports_destinations.png)
