---
description: Wij gebruiken geen Audience Manager maar wij zien Audience Manager Javascript vraag in debugger Javascript - waarom?
seo-description: Wij gebruiken niet maar wij zien Audience Manager Javascript vraag in debugger Javascript - waarom?
seo-title: Wij gebruiken geen Audience Manager maar wij zien Audience Manager Javascript vraag in debugger Javascript - waarom?
solution: Audience Manager
title: Wij gebruiken geen Audience Manager maar wij zien Audience Manager Javascript vraag in debugger Javascript - waarom?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---


# Wij zijn geen klant van de Audience Manager, maar zie de vraag van Javascript van de Audience Manager op onze plaats

## Vraag

Wij gebruiken geen Adobe Audience Manager maar wij zien Audience Manager Javascript vraag in debugger Javascript.

Waarom gebeurt dit?

## Antwoord

Waarschijnlijk voert u de [Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) op uw eigendom uit. Als u bent, verwijst het hebben van deze Audience Manager verwijzing niet noodzakelijk naar het bezit dat Audience Manager in werking stelt. In plaats daarvan betekent het dat de Audience Manager deze dienst aan de macht brengt.

De de servervraag van de Audience Manager wordt gewoonlijk gemaakt om klant IDs te [synchroniseren](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html).
