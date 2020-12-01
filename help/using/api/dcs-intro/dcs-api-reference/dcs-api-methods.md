---
description: Gegevens verzenden naar de DCS API met behulp van GET- of POST-methoden.
seo-description: Gegevens verzenden naar de DCS API met behulp van GET- of POST-methoden.
seo-title: DCS-API-methoden
solution: Audience Manager
title: DCS-API-methoden
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 5%

---


# [!DNL DCS] [!DNL API] Methoden  {#dcs-api-methods}

Gegevens verzenden naar [!DNL DCS] [!DNL API] met de methoden `GET` of `POST`.

U kunt gegevens naar [!DNL DCS] verzenden gebruikend of `GET` of `POST` methodes. Neem een blik bij de steekproefvraag hieronder, gebruikend [curl](https://curl.haxx.se/). In alle drie steekproefvraag, voegen wij de signalen `c_likes = famous popstar` en `c_loves = famous actress` aan het apparatenprofiel `12345678901234567890123456789012345678` toe.

## Gegevens verzenden via [!DNL GET] {#send-data-via-get}

Merk op dat de maximum toegestane grootte voor `GET` vraag 8K is.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Gegevens verzenden via [!DNL POST] {#send-data-via-post}

Noteer de vereisten voor het verzenden van gegevens met de methode `POST`:

* De maximaal toegestane grootte is 32 kB.
* Stel het inhoudstype in op `application/x-www-form-urlencoded`.

### Voorbeeld

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
