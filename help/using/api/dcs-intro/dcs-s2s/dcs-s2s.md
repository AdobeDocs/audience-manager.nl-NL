---
description: Server-aan-server (S2S) APIs verstrekt code en methodes die u DCS gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.
seo-description: Server-aan-server (S2S) APIs verstrekt code en methodes die u DCS gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.
seo-title: DCS API's voor gegevensoverdracht van server naar server
solution: Audience Manager
title: DCS API's voor gegevensoverdracht van server naar server
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# DCS API&#39;s voor gegevensoverdracht van server naar server{#dcs-apis-for-server-to-server-data-transfers}

Server-aan-server ([!UICONTROL S2S]) [!DNL API]s verstrekt code en methodes die u [!UICONTROL DCS] gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.

## Vaak Gebruik {#common-use-cases}

[!UICONTROL Server-to-server] met overgangen kunt u landingspagina&#39;s of andere interacties aanpassen op basis van de belangen van de bezoeker. Enkele gangbare gebruiksgevallen zijn:

* Lokaal personaliseren: Leer de ervaring van een bezoeker op uw plaats door relevante inhoud en vraag aan actie dynamisch toe te voegen die op de segmenten wordt gebaseerd zij tot behoren.
* De klantenservice verbeteren: Importeer [!DNL Audience Manager] segmenten in een [!DNL CRM] of ander systeem via gegevensoverdracht van server naar server. Deze gegevens kunnen de vraagdienst of online praatjeexploitanten van relevante, gepersonaliseerde informatie over een klant voorzien.

## Eisen: Gebruikers-id&#39;s en regionale servernamen {#requirements}

De id&#39;s van gebruikers en regio-id&#39;s [!UICONTROL DCS API] zijn vereist voor het valideren en indienen van gegevensaanvragen.

* De gebruikers-id is vereist omdat u gegevens aan een bepaalde bezoeker moet koppelen.
* De regio-id is vereist om aanroepen te koppelen aan een servernaam en omdat gebruikersgegevens worden opgeslagen in datacenters die zich geografisch het dichtst bij sitebezoekers bevinden.

## Aan de slag {#getting-started}

Deze handleiding behandelt momenteel het volgende:

* Haal de gebruikers- en regio-id&#39;s op uit de [!UICONTROL DCS] bestanden die u al als [!DNL Audience Manager] klant ontvangt.

* Hiermee haalt u de gebruikers- en regio-id&#39;s op als u de id [!DNL Visitor ID Service]gebruikt.
* Maak vraag aan het [!UICONTROL DCS] nadat u de gebruiker en gebiedsidentiteitskaart hebt.

We voegen nieuwe methoden toe zodra deze beschikbaar zijn. Raadpleeg de volgende secties om aan de slag te gaan.

* [Gebruikersnaam en regio&#39;s ophalen uit een DCS-reactie](dcs-aam-ids.md)
* [Gebruikersnaam en regio&#39;s ophalen via de Cloud-id voor ervaring...](dcs-mcid-ids.md)
* [Server-aan-Server DCS API Vraag maken](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API-naslag](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

