---
description: Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Voorwaarden van ruimte en foutafhandeling
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# De Voorwaarden van de ruimte, het Beperken van het Tarief, en de Behandeling van de Fout {#race-conditions-and-error-handling}

Beschrijft hoe te om rasvoorwaarden en [!DNL DCS] fout behandeling te verhinderen.

## Voorkomen van rasomstandigheden {#prevent-race-conditions}

Een rasvoorwaarde kan voorkomen als u veelvoudige vraag gelijktijdig (of in snelle opeenvolging) naar [!DNL DCS] verzendt alvorens het aan de aanvankelijke vragen beantwoordt en gegevens aan het koekje van de gebruiker schrijft. Een zeldzame omstandigheid is ongewenst omdat deze gegevens van cookies kan beschadigen of onjuist kan overschrijven. Overweeg de volgende methoden om dit probleem te helpen voorkomen:

* Maak geen gelijktijdige vraag, of vraag snel opeenvolging, aan [!DNL DCS] van de zelfde gebruiker.
* Wacht op elke reactie om terug te komen alvorens verdere vraag te maken.

## Snelheidbeperking {#rate-limiting}

Adobe kan tarieflimitering introduceren als het bovenmatige vraag DCS API ontdekt die een negatieve invloed op de dienstbeschikbaarheid zou kunnen hebben.

Als snelheidsbeperking is ingeschakeld, ontvangt u mogelijk een `429 Too Many Requests` HTTP-antwoordstatuscode voor uw DCS-aanroepen. Wanneer u deze HTTP-reactie ontvangt, probeert u de API-aanroepen later opnieuw.

## Foutafhandeling {#error-handling}

Foutafhandeling is beperkt voor ongeldige of onjuist gevormde query&#39;s. Een ongeldige aanvraag retourneert een `HTTP 200 OK` reactie en geen gegevens. Bovendien stopt de [!DNL DCS] met het verwerken van een aanvraag, verwijdert deze gegevens en retourneert deze een `HTTP 200 OK` -reactie wanneer een gebruiker:

* Opteert uit het volgen op het Audience Manager of partnerniveau.
* Komt uit een ongeldig/niet-geselecteerd geografisch gebied.
* Hiermee schakelt u browsercookies uit (alle cookies of cookies van derden).

Zie ook, [&#x200B; Codes van de Fout DCS, Berichten, en Voorbeelden &#x200B;](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
