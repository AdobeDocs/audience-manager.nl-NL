---
description: Algemene API-vragen en -problemen.
seo-description: Algemene API-vragen en -problemen.
seo-title: Veelgestelde vragen over API
solution: Audience Manager
title: Veelgestelde vragen over API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# Veelgestelde vragen over API{#api-faq}

Algemene API-vragen en -problemen.

<!-- 

faq_api.xml

 -->

De documentatie van de [REST API](../api/rest-api-main/rest-api-main.md) bevat details over specifieke methodes en codesteekproeven.

<br> 

**Waarom doet[!UICONTROL DIL]u gebeurtenisaanroepen met[!UICONTROL GET]en[!UICONTROL POST]methoden?**

[!UICONTROL DIL] geeft gegevens door aan [!DNL Audience Manager] met een `GET` of `POST` methode die op de lengte van het vraagkoord van de gebeurtenisvraag wordt gebaseerd. Dit gedrag is standaard ingebouwd op `GET` en `POST` methoden. Het is niet specifiek voor [!DNL Audience Manager].

* [!UICONTROL DIL] Hiermee wordt een gebeurtenis aangeroepen `GET` wanneer een URL maximaal 2048 tekens bevat. Een `GET` gebeurtenisaanroep bevat gegevens in de URL als parameters van een querytekenreeks, die worden doorgegeven als sleutel-waardeparen.

* [!UICONTROL DIL] roept een gebeurtenis aan `POST` wanneer een URL meer dan 2048 tekens bevat. Een `POST` gebeurtenisaanroep bevat gegevens in de hoofdtekst van het verzoek. [!UICONTROL DIL] Hiermee worden gegevens in sleutelwaardeparen geplaatst en wordt informatie als formuliergegevens doorgegeven in plaats van in de URL-queryreeks.

Hoewel elke methode gegevens op een andere manier doorgeeft, heeft dit geen invloed op de functionaliteit. Bijvoorbeeld, met één van beide methode, verzendt [!DNL Audience Manager] nog gegevens naar bestemmingen, werkt de syncs van identiteitskaart normaal, en u kunt eigenschappen van gegevenssignalen tot stand brengen.

<br> 

**Wat[!UICONTROL REST API]laten ze me doen?**

Met [!UICONTROL REST API]s kunt u programmatisch werken met de meeste [!DNL Audience Manager] functies en functies die beschikbaar zijn in de gebruikersinterface.

<br> 

**Hoe verkrijg ik een[!UICONTROL REST API]cliënt ID en geheim?**

Contacteer uw vertegenwoordiger van de Oplossingen van de Partner om [!DNL API] toegangsgeloofsbrieven te verkrijgen. Onze API&#39;s gebruiken [OAuth 2.0](https://oauth.net/2/) -standaarden voor tokenverificatie, -autorisatie en -vernieuwing. Zie [OAuth-verificatie](../api/rest-api-main/aam-api-getting-started.md#oauth) voor meer informatie.
