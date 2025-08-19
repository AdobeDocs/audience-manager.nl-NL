---
description: Gegevens naar de DCS API verzenden met GET- of POST-methoden.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: DCS API-methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# [!DNL DCS] [!DNL API] Methoden {#dcs-api-methods}

Gegevens verzenden naar de methoden [!DNL DCS] [!DNL API] using `GET` of `POST` .

U kunt gegevens naar de [!DNL DCS] verzenden met een van de methoden `GET` of `POST` . Neem een blik bij de steekproefvraag hieronder, gebruikend [ krullen ](https://curl.haxx.se/). In alle drie voorbeeldaanroepen voegen we de signalen `c_likes = famous popstar` en `c_loves = famous actress` toe aan het apparaatprofiel `12345678901234567890123456789012345678` .

## Gegevens verzenden via [!DNL GET] {#send-data-via-get}

Merk op dat de maximum toegestane grootte voor `GET` vraag 8K is.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Gegevens verzenden via [!DNL POST] {#send-data-via-post}

Let op de vereisten voor het verzenden van gegevens met de methode `POST` :

* De maximaal toegestane grootte is 32 kB.
* Stel het inhoudstype in op `application/x-www-form-urlencoded` .

### Voorbeeld

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
