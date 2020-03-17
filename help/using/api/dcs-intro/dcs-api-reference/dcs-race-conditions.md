---
description: Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.
seo-description: Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.
seo-title: Voorwaarden van ruimte en foutafhandeling
solution: Audience Manager
title: Voorwaarden van ruimte en foutafhandeling
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Voorwaarden van ruimte en foutafhandeling {#race-conditions-and-error-handling}

Beschrijft hoe te om rasvoorwaarden en [!UICONTROL DCS] foutenbehandeling te verhinderen.

## Voorkomen van rasomstandigheden {#prevent-race-conditions}

Een rasvoorwaarde kan voorkomen als u veelvoudige vraag gelijktijdig (of in snelle opeenvolging) naar het verzendt [!UICONTROL DCS] alvorens het aan de aanvankelijke vragen beantwoordt en gegevens aan het koekje van de gebruiker schrijft. Een zeldzame omstandigheid is ongewenst omdat deze gegevens van cookies kan beschadigen of onjuist kan overschrijven. Overweeg de volgende methoden om dit probleem te helpen voorkomen:

* Maak geen gelijktijdige vraag, of vraag in snelle opeenvolging, aan de [!UICONTROL DCS] van de zelfde gebruiker.
* Wacht op elke reactie om terug te komen alvorens verdere vraag te maken.

## Foutafhandeling {#error-handling}

Foutafhandeling is beperkt voor ongeldige of onjuist gevormde query&#39;s. Een ongeldig verzoek retourneert een `HTTP 200 OK` reactie en geen gegevens. Ook, [!UICONTROL DCS] houdt op verwerkend een verzoek, verwerpt karaktergegevens, en keert een `HTTP 200 OK` reactie terug wanneer een gebruiker:

* Opteert uit het volgen op de Manager van het Publiek of partnerniveau.
* Komt uit een ongeldig/niet-geselecteerd geografisch gebied.
* Hiermee schakelt u browsercookies uit (alles of van derden).

Zie ook [DCS-foutcodes, berichten en voorbeelden](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).