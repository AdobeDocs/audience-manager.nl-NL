---
description: We gebruiken Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing. Waarom?
seo-description: We gebruiken Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing. Waarom?
seo-title: We gebruiken Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing. Waarom?
solution: Audience Manager
title: We gebruiken Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing. Waarom?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 99%

---

# Wij zijn geen klant van de Audience Manager, maar we zien wel JavaScript-calls van Audience Manager op onze website

## Vraag

We gebruiken Adobe Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing.

Waarom gebeurt dit?

## Antwoord

Waarschijnlijk voert u de [Experience Cloud Identity Service](https://docs.adobe.com/content/help/nl-NL/id-service/using/home.html) uit op uw eigendom. Als dat zo is, deze verwijzing naar Audience Manager niet noodzakelijkerwijs naar het eigendom waarop Audience Manager wordt uitgevoerd. Het betekent dat Audience Manager deze service aanstuurt.

De server call van Audience Manager wordt meestal uitgevoerd om [klant-id’s te synchroniseren](https://docs.adobe.com/content/help/nl-NL/id-service/using/id-service-api/methods/setcustomerids.html).
