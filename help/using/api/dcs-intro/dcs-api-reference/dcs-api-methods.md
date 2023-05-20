---
description: Gegevens verzenden naar de DCS API met behulp van GET- of POST-methoden.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS-API-methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 3%

---

# [!DNL DCS] [!DNL API] Methoden {#dcs-api-methods}

Gegevens verzenden naar de [!DNL DCS] [!DNL API] gebruiken `GET` of `POST` methoden.

U kunt gegevens verzenden naar de [!DNL DCS] met een van de `GET` of `POST` methoden. Neem een blik bij de steekproefvraag hieronder, gebruikend [krullen](https://curl.haxx.se/). In alle drie steekproefvraag, voegen wij de signalen toe `c_likes = famous popstar` en `c_loves = famous actress` naar het apparaatprofiel `12345678901234567890123456789012345678`.

## Gegevens verzenden via [!DNL GET] {#send-data-via-get}

Let op: de maximaal toegestane grootte voor `GET` De vraag is 8K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Gegevens verzenden via [!DNL POST] {#send-data-via-post}

Let op de vereisten voor het verzenden van gegevens met de `POST` methode:

* De maximaal toegestane grootte is 32 kB.
* Inhoudstype instellen op `application/x-www-form-urlencoded`.

### Voorbeeld

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
