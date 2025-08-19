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
source-wordcount: '520'
ht-degree: 0%

---

# Digitaal ondertekende `HTTP(S)` aanvragen {#digitally-signed-http-requests}

Audience Manager vereist dat de serveraanvragen van `HTTP(S)` digitaal worden ondertekend voor geldigheid. In dit document wordt beschreven hoe u `HTTP(S)` -aanvragen kunt ondertekenen met persoonlijke sleutels.

## Overzicht {#overview}

<!-- digitally_signed_http_requests.xml -->

Gebruikend een privé sleutel die door u wordt verstrekt en met [!DNL Audience Manager] wordt gedeeld, kunnen wij de `HTTP(S)` verzoeken digitaal ondertekenen die tussen [ IRIS ](../../../reference/system-components/components-data-action.md#iris) en uw server van HTTP(S) worden verzonden. Dit zorgt ervoor dat:

* **Authenticiteit**: slechts kan de afzender die de privé sleutel ([!UICONTROL IRIS]) heeft geldige `HTTP(S)` berichten naar de partner verzenden.
* **integriteit van het Bericht**: met deze benadering, zelfs op `HTTP`, bent u beschermd tegen een man in de middelste aanval waar de berichten worden vervormd.

[!UICONTROL IRIS] heeft ingebouwde steun om de sleutels met nul onderbreking, zoals aangetoond in [ roterend de privé sleutel ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) hieronder sectie te roteren.

## Informatie die u moet opgeven {#info-to-provide}

Neem voor een `HTTP(S)` realtime server-naar-server bestemming contact op met uw [!DNL Audience Manager] -consultant en geef de volgende gegevens op:

* De sleutel die wordt gebruikt om het verzoek te ondertekenen.
* De naam van de header van `HTTP(S)` die de gegenereerde handtekening zal bevatten (X-handtekening in de voorbeeldkoptekst hieronder).
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

1. [!UICONTROL IRIS] maakt het `HTTP(S)` -bericht dat naar de partner moet worden verzonden.
1. [!UICONTROL IRIS] maakt een handtekening op basis van het `HTTP(S)` -bericht en de persoonlijke sleutel die door de partner wordt doorgegeven.
1. [!UICONTROL IRIS] verzendt het `HTTP(S)` -verzoek naar de partner. Dit bericht bevat de handtekening en het werkelijke bericht, zoals in het bovenstaande voorbeeld wordt getoond.
1. De partnerserver ontvangt de `HTTP(S)` aanvraag. De berichttekst en de handtekening die zijn ontvangen van [!UICONTROL IRIS] worden gelezen.
1. Gebaseerd op het berichtlichaam dat en de privé sleutel wordt ontvangen, herberekent de partnerserver de handtekening. Zie [ hoe te om de handtekening ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) sectie enkel hieronder op te berekenen hoe te om dit te bereiken.
1. Vergelijk de handtekening die op de partnerserver (ontvanger) wordt gemaakt met de handtekening die van [!UICONTROL IRIS] (afzender) wordt ontvangen.
1. Als de handtekeningen aanpassen, dan zijn de **authenticiteit** en **berichtintegriteit** bevestigd. Alleen de afzender, die over de persoonlijke sleutel beschikt, kan een geldige handtekening (authenticiteit) verzenden. Bovendien kan een man in het midden het bericht niet wijzigen en een nieuwe geldige handtekening genereren, aangezien hij of zij niet over de persoonlijke sleutel (berichtintegriteit) beschikt.

![](assets/iris-digitally-sign-http-request.png)

## De handtekening berekenen {#calculate-signature}

[!DNL HMAC] (Hash-based message authentication code) is de methode die door [!UICONTROL IRIS] wordt gebruikt voor het ondertekenen van berichten. Implementaties en bibliotheken zijn in principe beschikbaar in elke programmeertaal. [!DNL HMAC] heeft geen bekende uitbreidingsaanvallen. Zie een voorbeeld in [!DNL Java] hieronder:

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

RFC voor de [!DNL HMAC] knoeiboelimplementatie is [ https://www.ietf.org/rfc/rfc2104.txt ](https://www.ietf.org/rfc/rfc2104.txt). Een testplaats: [ https://asecuritysite.com/encryption/hmac ](https://asecuritysite.com/encryption/hmac) (merk op dat u [ ](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) hexcodering in base64 moet omzetten).

## De persoonlijke sleutel roteren {#rotate-private-key}

Om de persoonlijke sleutel te roteren, moeten partners de nieuwe persoonlijke sleutel aan hun [!DNL Adobe Audience Manager] consultant meedelen. De oude sleutel wordt verwijderd uit [!DNL Audience Manager] en [!UICONTROL IRIS] verzendt alleen de nieuwe handtekeningheader. De toetsen zijn geroteerd.

## Gegevens gebruikt voor ondertekening {#data-signing}

Voor `GET` typebestemmingen, zal het bericht dat voor het ondertekenen wordt gebruikt *REQUEST_PATH + QUERY STRING* (b.v. */from-aam-s2s?sids=1,2,3*) zijn. IRIS houdt geen rekening met hostname of `HTTP(S)` kopballen - deze kunnen worden gewijzigd/misconfigured langs de weg of verkeerd worden gemeld.

Voor `POST` typebestemmingen, is het bericht dat voor het ondertekenen wordt gebruikt het *LICHAAM VAN HET VERZOEK*. Ook hier worden kopteksten of andere aanvraagparameters genegeerd.
