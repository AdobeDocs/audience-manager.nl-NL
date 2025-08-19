---
description: Algemene vragen en problemen in verband met API’s.
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: Veelgestelde vragen over API’s
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

---

# Veelgestelde vragen over API’s{#api-faq}

Algemene vragen en problemen in verband met API’s.

<!-- 

faq_api.xml

 -->

De [REST-API](../api/rest-api-main/rest-api-main.md)-documentatie bevat details over specifieke methodes en codevoorbeelden.

<br>

**Waarom worden met [!UICONTROL DIL] gebeurteniscalls uitgevoerd met de methoden [!UICONTROL GET] en [!UICONTROL POST]?**

[!UICONTROL DIL] geeft data door aan [!DNL Audience Manager] met een `GET`- of `POST`-methode die is gebaseerd op de lengte van de querytekenreeks van de gebeurtenisquery. Dit gedrag is in de methoden `GET` en `POST` standaard ingebouwd. Deze is niet specifiek voor [!DNL Audience Manager].

* Met [!UICONTROL DIL] worden gebeurteniscalls uitgevoerd met `GET` wanneer een URL 2048 of minder tekens bevat. Een `GET`-gebeurteniscall bevat data in de URL als querytekenreeksparameters, die worden doorgegeven als sleutelwaardeparen.

* [!UICONTROL DIL] voert gebeurteniscalls uit met `POST` wanneer een URL meer dan 2048 tekens bevat. Een `POST`-gebeurteniscall bevat data in de hoofdtekst van de aanvraag. Met [!UICONTROL DIL] worden data in sleutelwaardeparen geplaatst en wordt informatie als formulierdata doorgegeven in plaats van in de URL-querytekenreeks.

Met elke methode worden data op een andere manier doorgegeven, maar dit maakt niet uit voor de functionaliteit. Zo verzendt [!DNL Audience Manager] bij beide methoden nog steeds data naar bestemmingen, werkt de id-synchronisatie normaal, en kunt u eigenschappen maken op basis van datasignalen.

<br>

**Wat kan ik met de [!UICONTROL REST API]’s doen?**

Met [!UICONTROL REST API]’s kunt u programmatisch werken met de meeste onderdelen en functies van [!DNL Audience Manager] die beschikbaar zijn in de gebruikersinterface.

<br>

**Hoe krijg ik een [!UICONTROL REST API]-client-id en -geheim?**

Neem contact op met uw Partner Solutions-vertegenwoordiger om [!DNL API]-toegangsgegevens te krijgen. Onze API’s gebruiken [OAuth 2.0](https://oauth.net/2/)-standaarden voor de verificatie, autorisatie en vernieuwing van tokens. Zie [OAuth-verificatie](../api/rest-api-main/aam-api-getting-started.md#oauth) voor meer informatie.
