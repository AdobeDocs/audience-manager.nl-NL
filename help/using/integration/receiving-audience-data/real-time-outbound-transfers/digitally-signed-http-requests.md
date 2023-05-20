---
description: Audience Manager vereist dat de HTTP(S) server-aan-server verzoeken digitaal worden ondertekend voor geldigheid. In dit document wordt beschreven hoe u HTTP-aanvragen kunt ondertekenen met persoonlijke sleutels.
seo-description: Audience Manager requires the HTTP(S) server-to-server requests to be digitally signed for validity. This document describes how you can sign HTTP(S) requests with private keys.
seo-title: Digitally Signed HTTP(S) Requests
solution: Audience Manager
title: Digitaal ondertekende HTTP(S)-aanvragen
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
exl-id: 55907a25-a361-494a-86b9-c693faea4f0e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 0%

---

# Digitaal ondertekend `HTTP(S)` Verzoeken {#digitally-signed-http-requests}

Audience Manager vereist `HTTP(S)` server-naar-server verzoeken om digitaal te worden ondertekend voor geldigheid. In dit document wordt beschreven hoe u kunt ondertekenen `HTTP(S)` aanvragen met persoonlijke sleutels.

## Overzicht {#overview}

<!-- digitally_signed_http_requests.xml -->

Een persoonlijke sleutel gebruiken die u hebt verschaft en waarmee u een gedeelde sleutel hebt [!DNL Audience Manager], kunnen we de `HTTP(S)` aanvragen die worden verzonden tussen [IRIS](../../../reference/system-components/components-data-action.md#iris) en uw HTTP(S)-server. Dit zorgt ervoor dat:

* **Authenticiteit**: alleen de afzender met de persoonlijke sleutel ([!UICONTROL IRIS]) kan geldig verzenden `HTTP(S)` berichten aan de partner.
* **Berichtintegriteit**: met deze aanpak, zelfs op `HTTP`, bent u beschermd tegen een man in de middelste aanval waar de berichten worden vervormd.

[!UICONTROL IRIS] heeft ingebouwde ondersteuning voor het roteren van de toetsen met 0 downtime, zoals in het dialoogvenster [De persoonlijke sleutel roteren](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) hieronder.

## Informatie die u moet opgeven {#info-to-provide}

Voor een `HTTP(S)` real-time server-aan-server bestemming, contacteer uw [!DNL Audience Manager] adviseur en specificeer:

* De sleutel die wordt gebruikt om het verzoek te ondertekenen.
* De naam van de `HTTP(S)` koptekst die de gegenereerde handtekening zal bevatten (X-handtekening in de voorbeeldkoptekst hieronder).
* Optioneel: het type hash dat wordt gebruikt voor de handtekening (md5, sha1, sha256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## Hoe werkt het {#how-it-works}

1. [!UICONTROL IRIS] maakt de `HTTP(S)` bericht dat naar de partner moet worden verzonden.
1. [!UICONTROL IRIS] maakt een handtekening op basis van de `HTTP(S)` bericht en de privé sleutel die door de partner wordt meegedeeld.
1. [!UICONTROL IRIS] verzendt de `HTTP(S)` verzoek aan de partner. Dit bericht bevat de handtekening en het werkelijke bericht, zoals in het bovenstaande voorbeeld wordt getoond.
1. De partnerserver ontvangt `HTTP(S)` verzoek. Het leest het berichtlichaam en de handtekening die van wordt ontvangen [!UICONTROL IRIS].
1. Gebaseerd op het berichtlichaam dat en de privé sleutel wordt ontvangen, herberekent de partnerserver de handtekening. Zie de [De handtekening berekenen](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) in het onderstaande gedeelte over hoe dit kan worden bereikt.
1. Vergelijk de handtekening die op de partnerserver (ontvanger) wordt gecreeerd met ontvangen van [!UICONTROL IRIS] (afzender).
1. Als de handtekeningen overeenkomen, **authenticiteit** en **berichtintegriteit** zijn gevalideerd. Alleen de afzender, die over de persoonlijke sleutel beschikt, kan een geldige handtekening (authenticiteit) verzenden. Bovendien kan een man in het midden het bericht niet wijzigen en een nieuwe geldige handtekening genereren, aangezien hij of zij niet over de persoonlijke sleutel (berichtintegriteit) beschikt.

![](assets/iris-digitally-sign-http-request.png)

## De handtekening berekenen {#calculate-signature}

[!DNL HMAC] (Hash-based message authentication code) is de methode die door wordt gebruikt [!UICONTROL IRIS] voor het ondertekenen van berichten. Implementaties en bibliotheken zijn in principe beschikbaar in elke programmeertaal. [!DNL HMAC] heeft geen bekende uitbreidingsaanvallen. Zie een voorbeeld in [!DNL Java] hieronder:

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

De RFC voor de [!DNL HMAC] hash-implementatie is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Een testlocatie: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (Let op: [omzetten](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) de hexadecimale codering tot base64).

## De persoonlijke sleutel roteren {#rotate-private-key}

Om de privé sleutel te roteren, moeten de partners de nieuwe privé sleutel aan hun meedelen [!DNL Adobe Audience Manager] consultant. De oude sleutel wordt verwijderd uit [!DNL Audience Manager] en [!UICONTROL IRIS] alleen de nieuwe handtekeningkop verzendt. De toetsen zijn geroteerd.

## Gegevens gebruikt voor ondertekening {#data-signing}

Voor `GET` typebestemmingen, zal het bericht voor het ondertekenen wordt gebruikt het *REQUEST_PATH + QUERY STRING* (bijvoorbeeld */from-aam-s2s?sids=1,2,3*). IRIS houdt geen rekening met de hostnaam of `HTTP(S)` Kopteksten - deze kunnen langs de weg worden gewijzigd/misvormd of verkeerd worden gemeld.

Voor `POST` typebestemmingen, het bericht voor het ondertekenen wordt gebruikt is *VERZOEKINSTANTIE*. Ook hier worden kopteksten of andere aanvraagparameters genegeerd.
