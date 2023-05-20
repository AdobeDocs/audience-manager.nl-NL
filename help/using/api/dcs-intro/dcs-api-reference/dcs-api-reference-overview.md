---
description: Conceptuele informatie, beschrijvingen, en definities voor code DCS API, methodes, en processen.
seo-description: Conceptual information, descriptions, and definitions for DCS API code, methods, and processes in Adobe Audience Manager (AAM).
seo-title: DCS API Reference Overview in Adobe Audience Manager (AAM)
title: Overzicht van DCS-API-referenties
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 14%

---

# Overzicht van DCS-API-referenties

Conceptuele informatie, beschrijvingen en definities voor [!DNL DCS API] code, methoden en processen.

* [DCS-API-methoden](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Gegevens verzenden naar de [!DNL DCS API] met behulp van methoden voor GET of POST.

* [DCS-foutcodes, -berichten en -voorbeelden](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Foutcodes en berichten die worden gegenereerd door de gegevensverzamelingsservers (DCS) in numerieke volgorde op basis van code-id.

* [ID-controle en Voegend op lijst van gewenste personen maken](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   De DCS bewaakt de id&#39;s die het ontvangt en voegt de id&#39;s toe die in een korte periode met een ongewoon hoge snelheid naar een lijst van gewezen personen worden verzonden.

* [Id’s, locaties en hostnamen van DCS-regio’s](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   De regionale DCS servergastheernaam wordt vereist om vraag aan DCS te maken. Dit komt doordat in de DCS informatie wordt opgeslagen in datacenters die geografisch dicht bij sitebezoekers liggen. Uw vragen zullen werken als u hen naar verkeerde DCS verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een DCS-aanvraag wilt maken, moet u de regio-id afstemmen op de corresponderende regionale hostnaam en de query met de juiste hostnaam configureren.

* [Het opmaken van sleutelwaardeparen in DCS-calls](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Wanneer het doen van een vraag, keurt DCS zeer belangrijke-waardegegevens in standaard of geserialiseerde formaat goed. Herzie deze sectie voor informatie over hoe te om standaard en geserialiseerde sleutel-waarde gegevens te formatteren.

* [Racevoorwaarden en foutafhandeling](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.

* [Ondersteunde attributen voor DCS-API-calls](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Hiermee geeft u een overzicht en beschrijving van de syntaxis en ondersteunde kenmerken (of sleutelwaardeparen) die u kunt doorgeven aan de gegevensverzamelingsservers (DCS). Deze informatie kan u helpen uw DCS- verzoeken formatteren en de parameters begrijpen die door dit systeem zijn teruggekeerd.
