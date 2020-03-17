---
description: Gegevens naar de DCS API verzenden met GET- of POST-methoden.
seo-description: Gegevens naar de DCS API verzenden met GET- of POST-methoden.
seo-title: DCS API-methoden
solution: Audience Manager
title: DCS API-methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# DCS API-methoden {#dcs-api-methods}

Gegevens naar de [!UICONTROL DCS] server verzenden [!DNL API] met `GET` behulp van `POST` methoden.

U kunt gegevens naar de [!UICONTROL DCS] server verzenden met een van de `GET` of `POST` methoden. Neem een blik bij de steekproefvraag hieronder, gebruikend [krullen](https://curl.haxx.se/). In alle drie steekproefvraag, voegen wij de signalen `c_likes = famous popstar` en `c_loves = famous actress` aan het apparatenprofiel toe `12345678901234567890123456789012345678`.


## Gegevens verzenden via GET {#send-data-via-get}

Merk op dat de maximum toegestane grootte voor `GET` vraag 8K is.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Gegevens verzenden via POST {#send-data-via-post}

Let op de vereisten voor het verzenden van gegevens met de `POST` methode:

* De maximaal toegestane grootte is 32 kB.
* Stel het inhoudstype in op `application/x-www-form-urlencoded`.

### Voorbeeld

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
