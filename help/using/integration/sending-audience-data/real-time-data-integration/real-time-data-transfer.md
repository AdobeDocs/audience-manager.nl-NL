---
description: Het in real time binnenkomende proces van gegevensopname gebruikt een reeks verzoeken van HTTP van browser van een gebruiker om gegevens tot de Manager van de Publiek over te gaan.
seo-description: Het in real time binnenkomende proces van gegevensopname gebruikt een reeks verzoeken van HTTP van browser van een gebruiker om gegevens tot de Manager van de Publiek over te gaan.
seo-title: Real-Time Inbound van Gegevens
solution: Audience Manager
title: Real-Time Inbound van Gegevens
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Inbound van Gegevens {#real-time-inbound-data-ingestion}

Het in real time binnenkomende proces van gegevensopname gebruikt een reeks `HTTP` verzoeken van browser van een gebruiker om gegevens tot de Manager van de Publiek over te gaan.

<!-- c_rt_inbound_real_time.xml -->

De binnenkomende gegevens zouden als zeer belangrijk-waardeparen moeten worden geformatteerd genoemd signalen. Typisch, wordt elk signaal in kaart gebracht aan een segment dat door het gebruikersinterface wordt gecreeerd of wordt geleid [!DNL API].

## Parameters URL-tekenreeks en syntaxis {#url-string-syntax}

De [!DNL URL] voor een inkomende gegevensoverdracht moet de hieronder beschreven variabelen bevatten. Vergeet niet om [kenmerken](../../../features/traits/create-onboarded-rule-based-traits.md) en een [mapstructuur](../../../features/traits/trait-storage.md#create-trait-storage-folder) in de [!DNL Audience Manager] gebruikersinterface te maken voordat u gegevensoverdracht in realtime instelt.

>[!NOTE]
>
>Vervang cursieve inhoud door werkelijke parameterwaarden.

| Parameter | Beschrijving |
|---|---|
| `<KEY>` | Een unieke id in een sleutelwaardepaar (bijvoorbeeld geslacht, kleur, prijs). |
| `<VAL>` | Een variabele die tot de gegevensset behoort die door de sleutel wordt gedefinieerd (bijvoorbeeld gender=male, color=green, price=100) |

### URL-syntaxis

Tijdens een real-time binnenkomend proces van gegevensopname, gebruikt een behoorlijk geformatteerde [!DNL URL] koord de volgende syntaxis:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
