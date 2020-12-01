---
description: Server-aan-server (S2S) APIs verstrekt code en methodes die u DCS gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.
seo-description: Server-aan-server (S2S) APIs verstrekt code en methodes die u DCS gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.
seo-title: DCS-API’s voor server-naar-server overdrachten
solution: Audience Manager
title: DCS-API’s voor server-naar-server overdrachten
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 10%

---


# DCS-API’s voor server-naar-server overdrachten{#dcs-apis-for-server-to-server-data-transfers}

Server-aan-server ([!UICONTROL S2S]) [!DNL API]s verstrekt code en methodes die u laten verzenden en [!DNL DCS] gebruikersgegevens ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.

## Veelvoorkomende gevallen van gebruik {#common-use-cases}

[!UICONTROL Server-to-server] met overgangen kunt u landingspagina&#39;s of andere interacties aanpassen op basis van de belangen van de bezoeker. Enkele gangbare gebruiksgevallen zijn:

* Lokaal personaliseren: Leer de ervaring van een bezoeker op uw plaats door relevante inhoud en vraag aan actie dynamisch toe te voegen die op de segmenten wordt gebaseerd zij tot behoren.
* De klantenservice verbeteren: Importeer [!DNL Audience Manager]-segmenten in een [!DNL CRM] of ander systeem via een server-naar-server gegevensoverdracht. Deze gegevens kunnen de vraagdienst of online praatjeexploitanten van relevante, gepersonaliseerde informatie over een klant voorzien.

## Eisen: Gebruiker-id&#39;s en regionale servernamen {#requirements}

[!UICONTROL DCS API] vereist gebruikers-id&#39;s en regio-id&#39;s om gegevensaanvragen te valideren en in te dienen.

* De gebruikers-id is vereist omdat u gegevens aan een bepaalde bezoeker moet koppelen.
* De regio-id is vereist om aanroepen te koppelen aan een servernaam en omdat gebruikersgegevens worden opgeslagen in datacenters die zich geografisch het dichtst bij sitebezoekers bevinden.

## Aan de slag {#getting-started}

Deze handleiding behandelt momenteel het volgende:

* Haal de gebruikers- en regio-id&#39;s op uit de [!DNL DCS]-bestanden die u mogelijk al als [!DNL Audience Manager]-klant ontvangt.

* Haal de gebruikers- en regio-id&#39;s op als u [!DNL Visitor ID Service] gebruikt.
* Maak vraag aan [!DNL DCS] nadat u gebruiker en gebiedsidentiteitskaart hebt.

We voegen nieuwe methoden toe zodra deze beschikbaar zijn. Raadpleeg de volgende secties om aan de slag te gaan.

* [Gebruikers-id’s en -regio’s ontvangen van een DCS-reactie](dcs-aam-ids.md)
* [Gebruikersnaam en -regio&#39;s ophalen via de Experience Cloud-id...](dcs-mcid-ids.md)
* [Server-naar-server DCS-API-calls uitvoeren](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS-API-referenties ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

