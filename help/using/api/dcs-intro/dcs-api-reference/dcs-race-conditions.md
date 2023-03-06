---
description: Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Racevoorwaarden en foutafhandeling
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# De Voorwaarden van de ruimte, het Beperken van het Tarief, en de Behandeling van de Fout {#race-conditions-and-error-handling}

Beschrijft hoe te om rasvoorwaarden en [!DNL DCS] foutafhandeling.

## Voorkomen van rasomstandigheden {#prevent-race-conditions}

Een rasvoorwaarde kan voorkomen als u veelvoudige vraag gelijktijdig (of in snelle opeenvolging) naar [!DNL DCS] voordat de toepassing klaar is met het beantwoorden van de eerste query&#39;s en het schrijven van gegevens naar de cookie van de gebruiker. Een zeldzame omstandigheid is ongewenst omdat deze gegevens van cookies kan beschadigen of onjuist kan overschrijven. Overweeg de volgende methoden om dit probleem te helpen voorkomen:

* Maak geen gelijktijdige vraag, of vraag in snelle opeenvolging, aan [!DNL DCS] van dezelfde gebruiker.
* Wacht op elke reactie om terug te komen alvorens verdere vraag te maken.

## Snelheidbeperking {#rate-limiting}

Adobe kan tarief het beperken introduceren als het bovenmatige vraag DCS API ontdekt die een negatieve invloed op de dienstbeschikbaarheid zou kunnen hebben.

Als snelheidsbeperking wordt toegelaten, zou u kunnen ontvangen `429 Too Many Requests` De code van de de reactiestatus van HTTP op uw vraag DCS. Wanneer u deze HTTP-reactie ontvangt, probeert u de API-aanroepen later opnieuw.

## Foutafhandeling {#error-handling}

Foutafhandeling is beperkt voor ongeldige of onjuist gevormde query&#39;s. Een ongeldig verzoek retourneert een `HTTP 200 OK` en geen gegevens. Ook de [!DNL DCS] stopt met het verwerken van een aanvraag, verwijdert gegevens uit de eigenschap en retourneert een `HTTP 200 OK` reactie wanneer een gebruiker:

* Opteert uit het volgen op het Audience Manager of partnerniveau.
* Komt uit een ongeldig/niet-geselecteerd geografisch gebied.
* Hiermee schakelt u browsercookies uit (alles of van derden).

Zie ook: [DCS-foutcodes, berichten en voorbeelden](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
