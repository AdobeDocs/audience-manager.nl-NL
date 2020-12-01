---
description: Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.
seo-description: Beschrijft hoe te om rasvoorwaarden en fout te verhinderen DCS behandeling.
seo-title: Racevoorwaarden en foutafhandeling
solution: Audience Manager
title: Racevoorwaarden en foutafhandeling
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# Racevoorwaarden en foutafhandeling {#race-conditions-and-error-handling}

Beschrijft hoe te om rasvoorwaarden en [!DNL DCS] fout behandeling te verhinderen.

## Voorkomen van wegomstandigheden {#prevent-race-conditions}

Een rasvoorwaarde kan voorkomen als u veelvoudige vraag gelijktijdig (of in snelle opeenvolging) naar [!DNL DCS] verzendt alvorens het aan de aanvankelijke vragen beantwoordt en gegevens aan het koekje van de gebruiker schrijft. Een zeldzame omstandigheid is ongewenst omdat deze gegevens van cookies kan beschadigen of onjuist kan overschrijven. Overweeg de volgende methoden om dit probleem te helpen voorkomen:

* Maak geen gelijktijdige vraag, of vraag snel opeenvolging, aan [!DNL DCS] van de zelfde gebruiker.
* Wacht op elke reactie om terug te komen alvorens verdere vraag te maken.

## Foutverwerking {#error-handling}

Foutafhandeling is beperkt voor ongeldige of onjuist gevormde query&#39;s. Een ongeldig verzoek keert een `HTTP 200 OK` reactie en geen gegevens terug. Ook, beëindigt [!DNL DCS] verwerking van een verzoek, verwerpt de gegevens van de eigenschap, en keert een `HTTP 200 OK` reactie terug wanneer een gebruiker:

* Opteert uit het volgen op het Audience Manager of partnerniveau.
* Komt uit een ongeldig/niet-geselecteerd geografisch gebied.
* Hiermee schakelt u browsercookies uit (alles of van derden).

Zie ook [DCS-foutcodes, -berichten en -voorbeelden](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).