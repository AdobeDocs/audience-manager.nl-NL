---
description: We gebruiken Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing. Waarom?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: We gebruiken Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing. Waarom?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 90%

---

# Wij zijn geen klant van de Audience Manager, maar we zien wel JavaScript-calls van Audience Manager op onze website

## Vraag

We gebruiken Adobe Audience Manager niet, maar we zien wel JavaScript-calls van Audience Manager in JavaScript-foutopsporing.

Waarom gebeurt dit?

## Antwoord

Waarschijnlijk voert u de [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) uit op uw eigendom. Als dat zo is, deze verwijzing naar Audience Manager niet noodzakelijkerwijs naar het eigendom waarop Audience Manager wordt uitgevoerd. Het betekent dat Audience Manager deze service aanstuurt.

De server call van Audience Manager wordt meestal uitgevoerd om [klant-id’s te synchroniseren](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html).
