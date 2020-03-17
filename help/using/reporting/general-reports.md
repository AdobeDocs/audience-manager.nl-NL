---
description: Een Algemeen rapport keert prestatiesgegevens over eigenschappen, segmenten, en bestemmingen terug.
seo-description: Een Algemeen rapport in de Manager van de Publiek keert prestatiesgegevens over eigenschappen, segmenten, en bestemmingen terug.
seo-title: Algemene rapporten in Audience Manager
solution: Audience Manager
title: Algemene rapporten
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
translation-type: tm+mt
source-git-commit: 1c626c770208150d209d93f666b581113ada8de9

---


# Algemene rapporten{#general-reports}

Een [!UICONTROL General] rapport keert prestatiesgegevens over eigenschappen, segmenten, en bestemmingen terug.

## Overzicht {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] gebruikt [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) om gebruikers-groep toestemmingen tot de [!UICONTROL General] rapporten uit te breiden. De gebruikers kunnen slechts die eigenschappen en segmenten in het melden zien dat zij toestemmingen aan mening hebben. [!UICONTROL RBAC] Met functionaliteit kunt u bepalen welke rapportgegevens interne teams kunnen weergeven. Bijvoorbeeld, kan een agentschap dat verschillende adverteerderrekeningen beheert gebruiker-groep toestemmingen vormen zodat een team dat de rekening van Advertiser A beheert niet de rapportgegevens van Advertiser B kan zien.

Voer een [!UICONTROL General] rapport uit wanneer u het volgende moet doen:

* De prestaties van het overzicht door eigenschap, segment, of bestemming.
* Houd afbeeldingen (totaal en uniek) bij intervallen van 1, 7, 14, 30, 60 en 90 dagen bij.
* Het totale en unieke aantal laden controleren.
* Vergelijk de prestaties van de kenmerken en segmenten.
* Identificeer sterke of slechte prestatieseigenschappen en segmenten, analyseer vraag, of vergelijk lading/brand gegevens met derderapporten.
* Gegevens (.csv-indeling) exporteren voor verdere analyse en uitwisseling.

De volgende illustratie biedt een overzicht op hoog niveau van de belangrijkste elementen in het [!UICONTROL General] rapport.

![](assets/general_reports.png)

1. Configureer de volgende opties:

   * **Rapporttype:** Selecteer het gewenste rapporttype (Trait, Segment, of Bestemming).

   * **Voor datums tot en met:** Geef het datumbereik voor het rapport op.

2. Zoek naar een eigenschap, segment, of bestemming door naam of identiteitskaart
3. Sleep vanuit de mappenlijst de kenmerken, segmenten of doelen die u aan de rechterkant aan het [!UICONTROL Selections] deelvenster wilt rapporteren, en zet deze neer.
4. Genereer het rapport dat u wilt weergeven in een tabel die kan worden geëxporteerd.

## Een algemeen rapport uitvoeren {#run-general-report}

Deze sectie beschrijft hoe te om een [!UICONTROL General] rapport in werking te stellen en tijd en andere prestatiesopties te plaatsen.

<!-- 

t_run_general_report.xml

 -->

1. Klik in het **[!UICONTROL Analytics]** dashboard op **[!UICONTROL General Reports]**.
1. Selecteer het gewenste type in de **[!UICONTROL Report Type]** vervolgkeuzelijst: Trait, Segment of Doel.
1. *Voorwaardelijk* Klik de datumdoos om een kalender te tonen, dan selecteer de beëindigende datum voor uw rapport als u een andere datum dan vandaag wilt specificeren.
1. Zoek naar een eigenschap, segment, of bestemming door naam of identiteitskaart
1. Sleep vanuit de mappenlijst de kenmerken, segmenten of doelen die u aan de rechterkant aan het [!UICONTROL Selections] deelvenster wilt rapporteren, en zet deze neer.
1. Klik op **[!UICONTROL Run Report]**.

   De resultaten worden weergegeven in een tabel die kan worden geëxporteerd. Klik op de kolomkoppen om de resultaten in oplopende of aflopende volgorde te sorteren.
1. Selecteer de gewenste optieknoop bij de bovenkant van het rapport aan filtergegevens door prestaties ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], of [!UICONTROL Total Trait Population]) of door tijd (1, 7, 14, 30, 60, of 90 dagwaaier).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] worden [!UICONTROL Rule-based Traits] alleen berekend.

1. *Optioneel* klikken **[!UICONTROL Export to CSV]**. Dit exporteert de [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]en [!UICONTROL Total Trait Population] voor alle dagbereiken.

## Algemene resultaten van rapporten {#general-reports-explained}

De getallen in het [!UICONTROL General Reports] bestand worden direct van ons gegenereerd [!UICONTROL User Profile Store]. De resultaten geven het aantal gebruikers weer dat zich in de back-end [!DNL Audience Manager] bevond op het moment dat deze rapportnummers werden gegenereerd.

* Deze aantallen omvatten bezoeker geen IDs met bovenmatig verkeer. Het verkeer van bots wordt gefilterd alvorens ons achterste systeem te bereiken. Ook, wordt wat bot verkeer verworpen tijdens een wekelijkse schoonmaakbaan die in het achterste gedeelte wordt in werking gesteld.
* Als u gegevens aan boord hebt via binnenkomende verwerking die van de [!DNL Audience Manager] UUID is afgehaald, en deze id&#39;s bevatten gebruikers die niet meer actief zijn in ons systeem, bereiken deze inactieve UUID&#39; [!DNL Audience Manager] s nooit de [!UICONTROL User Profile Store] UUID en worden deze niet gerapporteerd.
* [!UICONTROL Total Trait Realizations] worden [!UICONTROL Rule-based Traits] alleen berekend.

## Algemene rapporten Resultaten voor sporen {#general-report-results-traits}

De hieronder metriek is beschikbaar wanneer u een Algemeen rapport in werking stelt en als rapporttype selecteert **[!UICONTROL Trait]** :

**Unieke uitvoeringen**

Deze metrische waarde vertegenwoordigt het unieke aantal unieke gebruikers-id&#39;s (UUID) [](../reference/ids-in-aam.md) van Audience Manager dat in aanmerking kwam voor de eigenschap in het geselecteerde tijdbereik. Als een gebruiker bijvoorbeeld op 10/1 drie keer uw startpagina bezocht, ziet u één Unieke reisrealisatie.

**Totale realisaties van sporen**

Deze metrische waarde geeft de totale hoeveelheid eigenschap aan die wordt geactiveerd voor de eigenschap in het geselecteerde tijdbereik. Als een gebruiker bijvoorbeeld uw homepage bezocht en vervolgens naar het technische nieuws en de secties over de sport navigeert, worden deze in het algemeen rapport weergegeven als drie volledige realisaties van de kenmerken en één unieke realisatie van de kenmerken.

**Totale populatie**

Deze metrisch vertegenwoordigt de totale hoeveelheid UUIDs van de Manager van de Auditie die momenteel voor het bezit gekwalificeerd zijn. Gebruik dit nummer om te begrijpen hoeveel gebruikers u kunt gebruiken voor segmentatie en doelgerichtheid. Meestal blijven gebruikers gedurende [120 dagen](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)deel uitmaken van een eigenschap. Bijvoorbeeld, zou een gebruiker die uw homepage drie keer vandaag bezoekt en nooit daarna terugkeert, als gebruiker in deze bevolking elke dag tot 120 dagen van nu blijven. Op het teken van 120 dagen zouden ze uit de bevolking worden verwijderd. Lees onze [Verwijzing](../features/traits/trait-qualification-reference.md) van de Kwalificatie van het Bedieningsgebied voor meer voorbeelden op het verschil tussen de Unieke Redalisaties van het Bedieningsgebied en de Totale Bevolking van het Bedieningsgebied.

In de onderstaande afbeelding ziet u de resultaten van het uitvoeren van een algemeen rapport voor het rapporttype Trait.

![](assets/general_reports_metrics.png)

## Algemene rapporten Resultaten voor segmenten {#general-report-results-segments}

De hieronder metriek is beschikbaar wanneer u een Algemeen rapport in werking stelt en als rapporttype selecteert **[!UICONTROL Segment]** :

**Realtime segmentpopulatie**

Deze metrisch vertegenwoordigt het daadwerkelijke aantal unieke bezoekers die in real time voor de gespecificeerde tijdwaaier worden gezien en die voor het segment op het ogenblik werden gekwalificeerd zij gezien door de Manager van het Publiek.

**Totale segmentpopulatie**

Deze metrisch vertegenwoordigt het totale aantal UUIDs van de Manager van de Auditie die voor het segment binnen de terugblik-backperiode gekwalificeerd zijn u selecteerde. Uw 1 dag Totale Bevolking van het Segment vertegenwoordigt uw nauwkeurigste gebruikersbasis voor het richten.

>[!NOTE]
>
>Selecteer **[!UICONTROL Include Destination Mappings]** om een uitsplitsing van segmentpopulatie voor geactiveerde bestemmingen te zien.

In de onderstaande afbeelding ziet u de resultaten van het uitvoeren van een algemeen rapport voor het rapporttype Segment.

![](assets/general_reports_segment_metrics.png)

## Algemene rapporten Resultaten voor Doelen {#general-report-results-destinations}

De hieronder metriek is beschikbaar wanneer u een Algemeen rapport in werking stelt en als rapporttype selecteert **[!UICONTROL Destination]** :

**Realtime segmentpopulatie**

Deze metrisch vertegenwoordigt het daadwerkelijke aantal unieke bezoekers die in real time voor de gespecificeerde tijdwaaier worden gezien en die voor het segment op het ogenblik werden gekwalificeerd zij gezien door de Manager van het Publiek.

**Totale segmentpopulatie**

Deze metrisch vertegenwoordigt het totale aantal UUIDs van de Manager van de Audience die tot een segment binnen de terugkijkperiode behoren, die naar een bestemming werden verzonden.

In de onderstaande afbeelding ziet u de resultaten van het uitvoeren van een algemeen rapport voor het rapporttype Doelen.

![](assets/general_reports_destinations.png)
