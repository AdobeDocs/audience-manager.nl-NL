---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Rapportage van voorspellende doelgroepen
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Rapportage van voorspellende doelgroepen

Nadat u een [!UICONTROL Predictive Audiences] -model hebt opgeslagen, start Audience Manager de training. Binnen een paar uren, zal het gegevens verwerkte model beginnen publiek op de [ Servers van de Inzameling van Gegevens te analyseren ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Rapportage is de volgende dag beschikbaar.

Ga naar [!UICONTROL Predictive Audiences] > **[!UICONTROL Audience Data]** en klik op het model in de lijst om de resultaten van de **[!UICONTROL Models]** -classificatie te bekijken.

Gebruik de filteropties aan de linkerkant om naar de modelnaam te zoeken of de resultaten te filteren op basis van het modeltype.

![ voorspellend-publiek-filter ](assets/predictive-audiences-filter-models.png)

De modellenlijst toont u de volgende informatie:

* **[!UICONTROL ID]**: de model-id identificeert elk model op unieke wijze in uw Audience Manager-account;
* **[!UICONTROL Name]**: de naam die u hebt opgegeven in de stap voor het maken van het model;
* **[!UICONTROL Description]**: de beschrijving die u hebt opgegeven in de stap voor het maken van het model;
* **[!UICONTROL Model Type]**: het type van elk model ([!UICONTROL Look-Alike Modeling] of [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: de status van elk model:
   * **[!UICONTROL Pending]**: het model wordt geïnitialiseerd en zal binnenkort resultaten opleveren;
   * **[!UICONTROL Active]** : het model wordt uitgevoerd en levert resultaten op;
   * **[!UICONTROL Warning]**: het model heeft geen resultaten opgeleverd omdat er onvoldoende gegevens beschikbaar zijn (lage basislijnpopulatie, gebruikersprofielen zijn niet rijk);
   * **[!UICONTROL Error]** : het model kan niet worden uitgevoerd. Neem contact op met je Adobe-vertegenwoordiger.

## Rapport modeloverzicht{#model-report}

Wanneer u een model hebt gekozen, wordt de rapportpagina geladen. Bovenaan op de pagina ziet u de bovenste 5 grootste voorspellende segmenten, gebaseerd op één dag realtime realisatie, waarop het model uw doelpubliek heeft geclassificeerd. De categorie **[!UICONTROL Other]** bevat de overige personen, die niet waren opgenomen in de bovenste vijf grootste voorspellende segmenten.

Audience Manager geeft zowel een kleurengecodeerde donutgrafiek als een tijdlijngrafiek voor uw [!UICONTROL Predictive Audiences] weer.

Als u op de tabbladen met personen boven aan de pagina klikt, worden deze aan het diagram en de grafiek toegevoegd of eruit verwijderd.

Het donut-diagram toont u een op persoon-gebaseerde uitsplitsing van uw doelpubliek, terwijl de grafiek u de 1 dag in real time bevolkingstrend van uw voorspellende segmenten in de afgelopen 6 dagen toont.

Als de modelstatus [!UICONTROL Pending], [!UICONTROL Warning] of [!UICONTROL Error] is, wordt de modelstatus weergegeven in plaats van de grafieken.

![ slim-persona-rapport ](assets/predictive-audiences-report.png)

De rapportlijst toont u de volgende informatie voor elk [!UICONTROL Predictive Audiences] segment.

1. **[!UICONTROL SEGMENT ID]**: de segment-id van het automatisch gemaakte segment dat aan elke persoon is gekoppeld;
1. **[!UICONTROL NAME]**: de naam van de persoon;
1. **[!UICONTROL STATUS]**: de status van het [!UICONTROL Predictive Audiences] -segment:
   * **[!UICONTROL Succeeded]**: gebruikers worden geclassificeerd in dit segment;
   * **[!UICONTROL Pending]**: het segment wordt nog steeds geïnitialiseerd;
   * **[!UICONTROL Insufficient Training Data]**: gebruikers worden niet geclassificeerd in dit segment vanwege onvoldoende gegevens. De totale basislijnpopulatie is te laag en biedt onvoldoende gegevens om van te leren.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Het aantal segmentrealisaties voor elke persoon in de afgelopen 24 uur.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Het percentage segmentrealisaties voor elke persoon, in de afgelopen 24 uur, van de totale modelpopulatie.

## Influentiële sporen{#influential-traits}

[!UICONTROL Influential Traits] zijn kenmerken die het algoritme [!UICONTROL Predictive Audiences] heeft gedetecteerd als de sterkste voorspellers voor het bepalen van de persoonsclassificatie van een bezoeker.

Hun teken geeft aan of de aanwezigheid van het kenmerk de waarschijnlijkheid dat de gebruiker tot de geselecteerde persoon behoort, vergroot (+) of verkleint (-).

Klik op [!UICONTROL View All Influential Traits] om de invloedrijke kenmerken van al uw personen weer te geven.

In het venster [!UICONTROL Influential Traits] ziet u de volgende informatie voor elke persoon van het geselecteerde model:

![ invloedrijke-trekken ](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: de eigenschap-id van elk invloedrijk kenmerk voor de geselecteerde persoon;
1. **[!UICONTROL NAME]**: de naam van elke invloedrijke eigenschap voor de geselecteerde persoon;
1. **[!UICONTROL DESCRIPTION]**: de beschrijving van elke invloedrijke eigenschap voor de geselecteerde persoon;
1. **[!UICONTROL WEIGHT]** : het gewicht van elk invloedrijk kenmerk voor de geselecteerde persona. [!UICONTROL Influential Traits] worden standaard gesorteerd op gewicht, in aflopende volgorde.  De waarde van de gewichten geeft hun voorspellende vermogen aan. Het teken geeft aan of de aanwezigheid van het kenmerk de kans op het behoren tot een persona vergroot (+) of verkleint (-).
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: het aantal unieke karakteristieken voor elk invloedrijk bezit voor de geselecteerde persoonlijkheid, in de afgelopen 30 dagen.
