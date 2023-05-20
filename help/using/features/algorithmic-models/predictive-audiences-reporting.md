---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Rapportage in Predictieve doelgroepen
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# Rapportage in Predictieve doelgroepen

Nadat u een [!UICONTROL Predictive Audiences] model, Audience Manager begint het te trainen. Binnen een paar uur zal het berekende model het publiek analyseren op de [Gegevensverzamelingsservers](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Rapportage is de volgende dag beschikbaar.

Als u de resultaten van uw [!UICONTROL Predictive Audiences] classificatie, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** en klik op het model in de lijst.

Gebruik de filteropties aan de linkerkant om naar de modelnaam te zoeken of de resultaten te filteren op basis van het modeltype.

![voorspellend publiek-filter](assets/predictive-audiences-filter-models.png)

De modellenlijst toont u de volgende informatie:

* **[!UICONTROL ID]**: de model-id identificeert elk model op unieke wijze in uw Audience Manager-account;
* **[!UICONTROL Name]**: de naam die u hebt opgegeven in de stap voor het maken van het model;
* **[!UICONTROL Description]**: de beschrijving die u hebt opgegeven in de stap voor het maken van het model;
* **[!UICONTROL Model Type]**: het type van elk model ([!UICONTROL Look-Alike Modeling] of [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: de status van elk model:
   * **[!UICONTROL Pending]**: het model wordt geïnitialiseerd en zal binnenkort resultaten opleveren ;
   * **[!UICONTROL Active]**: het model functioneert met succes en levert resultaten op;
   * **[!UICONTROL Warning]**: het model heeft geen resultaten opgeleverd omdat er onvoldoende gegevens beschikbaar zijn (d.w.z. een lage basislijnpopulatie, gebruikersprofielen zijn niet rijk);
   * **[!UICONTROL Error]**: het model is niet uitgevoerd. Neem contact op met uw Adobe-vertegenwoordiger.

## Rapport modeloverzicht{#model-report}

Wanneer u een model hebt gekozen, wordt de rapportpagina geladen. Bovenaan op de pagina ziet u de bovenste 5 grootste voorspellende segmenten, gebaseerd op één dag realtime realisatie, waarop het model uw doelpubliek heeft geclassificeerd. De **[!UICONTROL Other]** de categorie omvat de overige personen , die niet in de vijf grootste voorspellende segmenten waren opgenomen .

Audience Manager geeft zowel een kleurgecodeerde donutgrafiek als een tijdlijngrafiek voor uw [!UICONTROL Predictive Audiences].

Als u op de tabbladen met personen boven aan de pagina klikt, worden deze aan het diagram en de grafiek toegevoegd of eruit verwijderd.

Het donut-diagram toont u een op persoon-gebaseerde uitsplitsing van uw doelpubliek, terwijl de grafiek u de 1 dag in real time bevolkingstrend van uw voorspellende segmenten in de afgelopen 6 dagen toont.

Als de modelstatus [!UICONTROL Pending], [!UICONTROL Warning], of [!UICONTROL Error]De modelstatus wordt weergegeven in plaats van de grafieken.

![smart-persona-rapport](assets/predictive-audiences-report.png)

De rapportlijst toont u de volgende informatie voor elke [!UICONTROL Predictive Audiences] segment.

1. **[!UICONTROL SEGMENT ID]**: de segment-id van het automatisch gemaakte segment dat aan elke persoon is gekoppeld;
1. **[!UICONTROL NAME]**: de naam van de persoon;
1. **[!UICONTROL STATUS]**: de status van de [!UICONTROL Predictive Audiences] segment:
   * **[!UICONTROL Succeeded]**: gebruikers worden ingedeeld in dit segment;
   * **[!UICONTROL Pending]**: het segment wordt nog steeds geïnitialiseerd;
   * **[!UICONTROL Insufficient Training Data]**: gebruikers worden niet in dit segment geclassificeerd omdat er onvoldoende gegevens zijn. De totale basislijnpopulatie is te laag en biedt onvoldoende gegevens om van te leren.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Het aantal segmentrealisaties voor elke persoon, in de afgelopen 24 uur.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Het percentage segmentrealisaties voor elke persoon, in de afgelopen 24 uur, van de totale modelpopulatie.

## Influente sporen{#influential-traits}

[!UICONTROL Influential Traits] zijn kenmerken die [!UICONTROL Predictive Audiences] algoritme die de sterkste voorspellers bleek te zijn voor het bepalen van de personaclassificatie van een bezoeker.

Hun teken geeft aan of de aanwezigheid van het kenmerk de waarschijnlijkheid dat de gebruiker tot de geselecteerde persoon behoort, vergroot (+) of verkleint (-).

Klik op [!UICONTROL View All Influential Traits].

De [!UICONTROL Influential Traits] toont u de volgende informatie, voor elke persoon van het geselecteerde model:

![invloedrijke eigenschappen](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: de eigenschap-id van elk invloedrijk kenmerk voor de geselecteerde persoon;
1. **[!UICONTROL NAME]**: de naam van elke invloedrijke eigenschap voor de geselecteerde persoon;
1. **[!UICONTROL DESCRIPTION]**: de beschrijving van elk invloedrijk kenmerk voor de geselecteerde persoon;
1. **[!UICONTROL WEIGHT]**: het gewicht van elke invloedrijke eigenschap voor de geselecteerde persoon. [!UICONTROL Influential Traits] standaard gesorteerd op gewicht, in aflopende volgorde.  De waarde van de gewichten geeft hun voorspellende vermogen aan. Het teken geeft aan of de aanwezigheid van het kenmerk de kans op het behoren tot een persona vergroot (+) of verkleint (-).
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: het aantal unieke karakteristieken voor elk invloedrijk kenmerk voor de geselecteerde persoon in de afgelopen 30 dagen.
