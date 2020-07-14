---
description: Audience Manager vereist dat de HTTP(S) server-aan-server verzoeken digitaal worden ondertekend voor geldigheid. In dit document wordt beschreven hoe u HTTP-aanvragen kunt ondertekenen met persoonlijke sleutels.
seo-description: Audience Manager vereist dat de HTTP(S) server-aan-server verzoeken digitaal worden ondertekend voor geldigheid. In dit document wordt beschreven hoe u HTTP(S)-aanvragen kunt ondertekenen met persoonlijke sleutels.
seo-title: Digitaal ondertekende HTTP(S)-aanvragen
solution: Audience Manager
title: Digitaal ondertekende HTTP(S)-aanvragen
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 4877aa5391193ee2187609fdc9cb3740c91feb96
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Digitaal ondertekende `HTTP(S)` verzoeken {#digitally-signed-http-requests}

Audience Manager vereist dat de `HTTP(S)` server-aan-server verzoeken digitaal worden ondertekend voor geldigheid. In dit document wordt beschreven hoe u `HTTP(S)` aanvragen met persoonlijke sleutels kunt ondertekenen.

## Overzicht {#overview}

<!-- digitally_signed_http_requests.xml -->

Met behulp van een persoonlijke sleutel die door u wordt verstrekt en waarmee wordt gedeeld, kunnen wij digitaal de [!DNL Audience Manager]verzoeken ondertekenen die tussen `HTTP(S)` IRIS [](../../../reference/system-components/components-data-action.md#iris) en uw server van HTTP(S) worden verzonden. Dit zorgt ervoor dat:

* **Authenticiteit**: alleen de afzender die de persoonlijke sleutel ([!UICONTROL IRIS]) heeft, kan geldige `HTTP(S)` berichten naar de partner verzenden.
* **Berichtintegriteit**: met deze aanpak , zelfs op `HTTP`, bent u beschermd tegen een man in de middelste aanval waar de berichten vervormd worden.

[!UICONTROL IRIS] heeft ingebouwde ondersteuning voor het roteren van de toetsen met 0 downtime, zoals in de sectie [De persoonlijke sleutel](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) roteren hieronder wordt getoond.

## Informatie die u moet opgeven {#info-to-provide}

Voor een `HTTP(S)` real-time server-aan-server bestemming, contacteer uw [!DNL Audience Manager] consultant en specificeer:

* De sleutel die wordt gebruikt om het verzoek te ondertekenen.
* De naam van de `HTTP(S)` header die de gegenereerde handtekening zal bevatten (X-handtekening in de voorbeeldkoptekst hieronder).
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

1. [!UICONTROL IRIS] leidt tot het `HTTP(S)` bericht dat naar de partner moet worden verzonden.
1. [!UICONTROL IRIS] maakt een handtekening op basis van het `HTTP(S)` bericht en de persoonlijke sleutel die door de partner wordt doorgegeven.
1. [!UICONTROL IRIS] verzendt het `HTTP(S)` verzoek naar de partner. Dit bericht bevat de handtekening en het werkelijke bericht, zoals in het bovenstaande voorbeeld wordt getoond.
1. De partnerserver ontvangt het `HTTP(S)` verzoek. Het leest de berichttekst en de handtekening die van [!UICONTROL IRIS].
1. Gebaseerd op het berichtlichaam dat en de privé sleutel wordt ontvangen, herberekent de partnerserver de handtekening. Zie de sectie [Hoe u de handtekening](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) kunt berekenen hieronder over hoe u dit kunt bereiken.
1. Vergelijk de handtekening die op de partnerserver (ontvanger) wordt gecreeerd met ontvangen van [!UICONTROL IRIS] (afzender).
1. Als de handtekeningen overeenkomen, zijn de **authenticiteit** en **berichtintegriteit** gevalideerd. Alleen de afzender, die over de persoonlijke sleutel beschikt, kan een geldige handtekening (authenticiteit) verzenden. Bovendien kan een man in het midden het bericht niet wijzigen en een nieuwe geldige handtekening genereren, aangezien hij of zij niet over de persoonlijke sleutel (berichtintegriteit) beschikt.

![](assets/iris-digitally-sign-http-request.png)

## De handtekening berekenen {#calculate-signature}

[!DNL HMAC] (Hash-based berichtauthentificatiecode) is de methode die door [!UICONTROL IRIS] voor bericht het ondertekenen wordt gebruikt. Implementaties en bibliotheken zijn in principe beschikbaar in elke programmeertaal. [!DNL HMAC] heeft geen bekende uitbreidingsaanvallen. Zie een voorbeeld [!DNL Java] hieronder:

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

RFC voor de [!DNL HMAC] knoeiboelimplementatie is [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). Een testlocatie: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (houd er rekening mee dat u de hexadecimale codering moet [converteren](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) naar base64).

## De persoonlijke sleutel roteren {#rotate-private-key}

Om de privé sleutel te roteren, moeten de partners de nieuwe privé sleutel aan hun [!DNL Adobe Audience Manager] consultant meedelen. De oude sleutel wordt verwijderd uit [!DNL Audience Manager] en [!UICONTROL IRIS] alleen de nieuwe handtekeningheader verstuurt. De toetsen zijn geroteerd.

## Gegevens gebruikt voor ondertekening {#data-signing}

Voor `GET` typebestemmingen, zal het bericht voor het ondertekenen *REQUEST_PATH + QUERY STRING* (b.v. */from-aam-s2s?sids=1,2,3*). IRIS houdt geen rekening met hostname of `HTTP(S)` kopballen - deze kunnen worden gewijzigd/misconfigured langs de weg of verkeerd worden gemeld.

Voor `POST` typebestemmingen, is het bericht voor het ondertekenen wordt gebruikt het *ORGAANDE LICHAAM* dat. Ook hier worden kopteksten of andere aanvraagparameters genegeerd.
