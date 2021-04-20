---
description: Het in real time binnenkomende proces van gegevensinvoer gebruikt een reeks verzoeken van HTTP van browser van een gebruiker om gegevens tot Audience Manager over te gaan.
seo-description: Het in real time binnenkomende proces van gegevensinvoer gebruikt een reeks verzoeken van HTTP van browser van een gebruiker om gegevens tot Audience Manager over te gaan.
seo-title: Opname van binnenkomende realtimedata
solution: Audience Manager
title: Opname van binnenkomende realtimedata
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# Opname van binnenkomende realtimedata {#real-time-inbound-data-ingestion}

Het proces van de inkomende gegevens in real time gebruikt een reeks `HTTP` verzoeken van browser van een gebruiker om gegevens tot Audience Manager over te gaan.

<!-- c_rt_inbound_real_time.xml -->

De binnenkomende gegevens zouden als zeer belangrijk-waardeparen moeten worden geformatteerd genoemd signalen. Typisch, wordt elk signaal in kaart gebracht aan een segment dat door het gebruikersinterface of [!DNL API] wordt gecreeerd of wordt geleid.

## Parameters URL-tekenreeks en syntaxis {#url-string-syntax}

De [!DNL URL] voor een binnenkomende gegevensoverdracht moet de hieronder beschreven variabelen bevatten. Vergeet niet om [kenmerken te maken](../../../features/traits/create-onboarded-rule-based-traits.md) en een [mapstructuur](../../../features/traits/trait-storage.md#create-trait-storage-folder) in de [!DNL Audience Manager]-interface voordat u gegevensoverdracht in real time instelt.

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
