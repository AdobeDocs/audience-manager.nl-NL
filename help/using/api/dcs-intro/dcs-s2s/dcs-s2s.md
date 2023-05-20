---
description: Server-aan-server (S2S) APIs verstrekt code en methodes die u DCS gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: DCS-API’s voor server-naar-server overdrachten
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 9%

---

# DCS-API’s voor server-naar-server overdrachten{#dcs-apis-for-server-to-server-data-transfers}

Server-naar-server ([!UICONTROL S2S]) [!DNL API]s verstrekt code en methodes die u verzenden en laten ontvangen [!DNL DCS] gebruikersgegevens en werk met deze gegevens in uw eigen systemen of toepassingen.

## Vaak Gebruik {#common-use-cases}

[!UICONTROL Server-to-server] met overgangen kunt u landingspagina&#39;s of andere interacties aanpassen op basis van de belangen van de bezoeker. Enkele gangbare gebruiksgevallen zijn:

* Lokaal personaliseren: Leer de ervaring van een bezoeker op uw plaats door relevante inhoud en vraag aan actie dynamisch toe te voegen die op de segmenten wordt gebaseerd zij tot behoren.
* De klantenservice verbeteren: Importeren [!DNL Audience Manager] segmenten in een [!DNL CRM] of een ander systeem via een server-naar-server gegevensoverdracht. Deze gegevens kunnen de vraagdienst of online praatjeexploitanten van relevante, gepersonaliseerde informatie over een klant voorzien.

## Eisen: Gebruikers-id&#39;s en regionale servernamen {#requirements}

De [!UICONTROL DCS API] vereist gebruikers-id&#39;s en regio-id&#39;s om gegevensaanvragen te valideren en in te dienen.

* De gebruikers-id is vereist omdat u gegevens aan een bepaalde bezoeker moet koppelen.
* De regio-id is vereist om aanroepen te koppelen aan een servernaam en omdat gebruikersgegevens worden opgeslagen in datacenters die zich geografisch het dichtst bij sitebezoekers bevinden.

## Aan de slag {#getting-started}

Deze handleiding behandelt momenteel het volgende:

* De gebruikers- en regio-id&#39;s ophalen van de [!DNL DCS] bestanden die u al ontvangt als een [!DNL Audience Manager] klant.

* De gebruikers- en regio-id&#39;s ophalen als u de [!DNL Visitor ID Service].
* Maak vraag aan [!DNL DCS] nadat u de gebruikers- en regio-id hebt.

We voegen nieuwe methoden toe zodra deze beschikbaar zijn. Raadpleeg de volgende secties om aan de slag te gaan.

* [Gebruikers-id’s en -regio’s ontvangen van een DCS-reactie](dcs-aam-ids.md)
* [Gebruikersnaam en -regio&#39;s ophalen via de Experience Cloud-id...](dcs-mcid-ids.md)
* [Server-naar-server DCS-API-calls uitvoeren](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS-API-referenties ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

