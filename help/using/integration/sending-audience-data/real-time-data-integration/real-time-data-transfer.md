---
description: Het proces van de in real time binnenkomende gegevensinvoer gebruikt een reeks HTTP- verzoeken van browser van een gebruiker om gegevens tot Audience Manager over te gaan.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Real-Time Inbound van Gegevens
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 0%

---

# Real-Time Inbound van Gegevens {#real-time-inbound-data-ingestion}

Bij het proces voor het invoeren van gegevens in real time wordt een reeks `HTTP` -aanvragen van de browser van een gebruiker gebruikt om gegevens door te geven aan Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

De binnenkomende gegevens zouden als zeer belangrijk-waardeparen moeten worden geformatteerd genoemd signalen. Doorgaans wordt elk signaal toegewezen aan een segment dat is gemaakt of beheerd via de gebruikersinterface of [!DNL API] .

## Parameters URL-tekenreeks en syntaxis {#url-string-syntax}

De [!DNL URL] voor een inkomende gegevensoverdracht moet de hieronder beschreven variabelen bevatten. Herinner me om [ eigenschappen ](../../../features/traits/create-onboarded-rule-based-traits.md) en a [ omslagstructuur ](../../../features/traits/trait-storage.md#create-trait-storage-folder) in [!DNL Audience Manager] UI tot stand te brengen alvorens de gegevensoverdrachten in real time te vestigen.

>[!NOTE]
>
>Vervang cursieve inhoud door werkelijke parameterwaarden.

| Parameter | Beschrijving |
|---|---|
| `<KEY>` | Een unieke id in een sleutelwaardepaar (bijvoorbeeld geslacht, kleur, prijs). |
| `<VAL>` | Een variabele die tot de gegevensset behoort die door de sleutel wordt gedefinieerd (bijvoorbeeld gender=male, color=green, price=100) |

### URL-syntaxis

Tijdens een real-time proces van binnenkomende gegevensinvoer gebruikt een correct opgemaakte [!DNL URL] -tekenreeks de volgende syntaxis:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
