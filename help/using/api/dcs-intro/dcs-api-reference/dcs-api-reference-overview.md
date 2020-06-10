---
description: Conceptuele informatie, beschrijvingen, en definities voor code DCS API, methodes, en processen.
seo-description: Conceptuele informatie, beschrijvingen en definities voor DCS API-code, -methoden en -processen in Adobe Audience Manager (AAM).
seo-title: Overzicht DCS API-naslaggids in Adobe Audience Manager (AAM)
title: Overzicht DCS API-naslaggids
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# Overzicht DCS API-naslaggids

Conceptuele informatie, beschrijvingen, en definities voor code DCS API, methodes, en processen.

* [DCS API-methoden](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   Gegevens naar de DCS API verzenden met GET- of POST-methoden.

* [DCS-foutcodes, berichten en voorbeelden](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   Foutcodes en berichten die worden gegenereerd door de gegevensverzamelingsservers (DCS) in numerieke volgorde op basis van code-id.

* [ID-controle en Afwijzing](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS controleert identiteitskaarts het ontvangt en voegt die toe die tegen een ongebruikelijk hoog tarief over een korte periode aan ontkent lijst worden verzonden.

* [Id&#39;s, locaties en hostnamen van DCS-regio&#39;s](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   De regionale DCS servergastheernaam wordt vereist om vraag aan DCS te maken. Dit komt doordat in de DCS informatie wordt opgeslagen in datacenters die geografisch dicht bij sitebezoekers liggen. Uw vragen zullen werken als u hen naar verkeerde DCS verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een DCS-aanvraag wilt maken, moet u de regio-id afstemmen op de corresponderende regionale hostnaam en de query met de juiste hostnaam configureren.

* [Het opmaken van zeer belangrijke-waardeparen in Vraag DCS](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   Wanneer het doen van een vraag, keurt DCS zeer belangrijke-waardegegevens in standaard of geserialiseerde formaat goed. Herzie deze sectie voor informatie over hoe te om standaard en geserialiseerde sleutel-waarde gegevens te formatteren.

* [Voorwaarden van ruimte en foutafhandeling](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.

* [Ondersteunde kenmerken voor DCS API-aanroepen](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   Hiermee geeft u een overzicht en beschrijving van de syntaxis en ondersteunde kenmerken (of sleutelwaardeparen) die u kunt doorgeven aan de gegevensverzamelingsservers (DCS). Deze informatie kan u helpen uw DCS- verzoeken formatteren en de parameters begrijpen die door dit systeem zijn teruggekeerd.
