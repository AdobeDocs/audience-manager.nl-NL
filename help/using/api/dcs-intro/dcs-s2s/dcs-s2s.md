---
description: Server-aan-server (S2S) APIs verstrekt code en methodes die u DCS gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: DCS API's voor gegevensoverdracht van server naar server
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# DCS API&#39;s voor gegevensoverdracht van server naar server{#dcs-apis-for-server-to-server-data-transfers}

Server-aan-server ([!UICONTROL S2S]) [!DNL API] verstrekt code en methodes die u [!DNL DCS] gebruikersgegevens verzenden en laten ontvangen en met deze informatie in uw eigen systemen of toepassingen werken.

## Vaak voorkomende gevallen {#common-use-cases}

Met [!UICONTROL Server-to-server] -overdrachten kunt u landingspagina&#39;s of andere interacties op basis van bezoekersbelangen aanpassen. Enkele gangbare gebruiksgevallen zijn:

* Onsite personalisatie: Tailor de ervaring van een bezoeker op uw site door dynamisch relevante inhoud en aanroepen toe te voegen aan actie op basis van de segmenten waartoe deze behoren.
* Verbeter de klantenservice: importeer [!DNL Audience Manager] -segmenten in een [!DNL CRM] -systeem of in een ander systeem via gegevensoverdracht van server naar server. Deze gegevens kunnen de vraagdienst of online praatjeexploitanten van relevante, gepersonaliseerde informatie over een klant voorzien.

## Vereisten: gebruikers-id&#39;s en regionale servernamen {#requirements}

In [!UICONTROL DCS API] moeten gebruikers-id&#39;s en regio-id&#39;s worden gevalideerd en moeten gegevensaanvragen worden ingediend.

* De gebruikers-id is vereist omdat u gegevens aan een bepaalde bezoeker moet koppelen.
* De regio-id is vereist om aanroepen te koppelen aan een servernaam en omdat gebruikersgegevens worden opgeslagen in datacenters die zich geografisch het dichtst bij sitebezoekers bevinden.

## Aan de slag {#getting-started}

Deze handleiding behandelt momenteel het volgende:

* Haal de gebruikers- en regio-id&#39;s op uit de [!DNL DCS] -bestanden die u mogelijk al als [!DNL Audience Manager] -klant ontvangt.

* Haal de gebruikers- en regio-id&#39;s op als u de [!DNL Visitor ID Service] gebruikt.
* Roep de [!DNL DCS] aan nadat u de gebruikers- en regio-id hebt.

We voegen nieuwe methoden toe zodra deze beschikbaar zijn. Raadpleeg de volgende secties om aan de slag te gaan.

* [Gebruikersnaam en -regio&#39;s ophalen uit een DCS-reactie](dcs-aam-ids.md)
* [Gebruikersnaam en -regio&#39;s ophalen via de Experience Cloud-id...](dcs-mcid-ids.md)
* [Server-aan-Server DCS API Vraag maken](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [ Verwijzing DCS API ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
