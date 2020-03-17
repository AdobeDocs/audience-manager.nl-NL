---
description: Wanneer het publiceren van segmenten aan de partnerbestemming via een server-aan-server integratie in realtime, kan de Manager van de Publiek opstelling zijn om het gebruiken van OAuth 2.0 voor authentiek te verklaren wanneer het maken van de verzoeken. Dit stelt de capaciteit voor om voor authentiek verklaarde verzoeken van de Manager van het Publiek aan uw eindpunt uit te geven.
seo-description: Wanneer het publiceren van segmenten aan de partnerbestemming via een server-aan-server integratie in realtime, kan de Manager van de Publiek opstelling zijn om het gebruiken van OAuth 2.0 voor authentiek te verklaren wanneer het maken van de verzoeken. Dit stelt de capaciteit voor om voor authentiek verklaarde verzoeken van de Manager van het Publiek aan uw eindpunt uit te geven.
seo-title: OAuth 2.0 Integratie voor Uitgaande Overdrachten in real time
solution: Audience Manager
title: OAuth 2.0 Integratie voor Uitgaande Overdrachten in real time
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
translation-type: tm+mt
source-git-commit: 1cc8afd25331528fd67922183b6550288b9939bc

---


# [!DNL OAuth 2.0] Integratie voor Uitgaande Overdrachten in real time{#oauth-integration-for-real-time-outbound-transfers}

Wanneer het publiceren van segmenten aan de partnerbestemming via een server-aan-server integratie in real time, kan de Manager van de Publiek opstelling zijn om het gebruiken voor authentiek te verklaren [!DNL OAuth 2.0] wanneer het maken van de verzoeken. Dit stelt de capaciteit voor om voor authentiek verklaarde verzoeken van de Manager van het Publiek aan uw eindpunt uit te geven.

## Verificatiestroom {#auth-flow}

De [!DNL Adobe Audience Manager] OAuth 2.0 [](https://tools.ietf.org/html/rfc6749#section-4.4) authentificatieimplementatie is gebaseerd op de de subsidiestroom van de Credentials van de Cliënt en volgt deze stappen:

1. U moet ons voorzien van:
   * Het [!DNL OAuth 2.0] eindpunt dat het authentificatietoken produceert.
   * De referenties die worden gebruikt om een token te genereren.
1. Een [!DNL Audience Manager] consultant stelt de [bestemming](../../../features/destinations/destinations.md) in met de informatie die u hebt opgegeven.
1. Zodra een segment aan deze bestemming in kaart wordt gebracht, doet ons systeem van de gegevensoverdracht in real time, [IRIS](../../../reference/system-components/components-data-action.md#iris), een `POST` verzoek aan het symbolische eindpunt om de geloofsbrieven voor een dragertoken uit te wisselen.
1. Voor elk segment dat verzoek aan het partnereindpunt publiceert, [!UICONTROL IRIS] gebruikt het dragertoken voor authentiek te verklaren.

![](assets/oauth2-iris.png)

## Vereisten {#auth-requirements}

Als [!DNL Audience Manager] partner, zijn de volgende eindpunten nodig om voor authentiek verklaarde verzoeken te ontvangen:

### Eindpunt 1 dat door IRIS wordt gebruikt om een token voor toonder te verkrijgen

Dit eindpunt zal de geloofsbrieven goedkeuren die bij stap 1 worden verstrekt en zal een tovenaarstoken produceren die op verdere verzoeken zal worden gebruikt.

* Het eindpunt moet `HTTP POST` verzoeken goedkeuren.
* Het eindpunt moet de [!DNL Authorization] kopbal goedkeuren en bekijken. De waarde voor deze header is: `Basic <credentials_provided_by_partner>`.
* Het eindpunt moet de [!DNL Content-type] kopbal bekijken en bevestigen dat zijn waarde is `application/x-www-form-urlencoded ; charset=UTF-8`.
* De inhoud van het verzoek zal worden `grant_type=client_credentials`.

### Voorbeeld verzoek dat door de Manager van het Publiek aan het partnereindpunt wordt gemaakt om een dragertoken te verkrijgen

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### De reactie van het voorbeeld van het partnereindpunt

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Eindpunt 2 dat door IRIS wordt gebruikt om segmenten te publiceren die het dragerteken gebruiken

[!DNL Audience Manager] verzendt gegevens naar dit eindpunt in dichtbij real time aangezien de gebruikers voor segmenten kwalificeren. Bovendien, kan deze methode partijen off-line of aan boord genomen gegevens zo vaak verzenden zoals om de 24 uur.

Het dragerteken dat door eindpunt 1 wordt geproduceerd wordt gebruikt om verzoeken aan dit eindpunt uit te geven. Het [!DNL Audience Manager] systeem van de gegevensoverdracht in real time, [IRIS](../../../reference/system-components/components-data-action.md#iris), bouwt een normale HTTPS- verzoek en omvat een kopbal van de Vergunning. De waarde voor deze header is: Drager `<bearer token from step 1>`.

### De reactie van het voorbeeld van het partnereindpunt

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>Deze aanvraag bevat een standaardlading (inhoud aanvragen).

## Belangrijke overwegingen {#considerations}

### Tokens zijn wachtwoorden

De geloofsbrieven die door de partner en de tekenen worden voorgesteld door [!DNL Audience Manager] wanneer het voor authentiek verklaren van het gebruiken van de [!DNL OAuth 2.0] stroom worden verkregen, zijn gevoelige informatie en moeten niet met derden worden gedeeld.

### [!DNL SSL] is vereist

[!DNL SSL] moet worden gebruikt om een veilig verificatieproces te onderhouden. Alle verzoeken, met inbegrip van die worden gebruikt om de tokens te verkrijgen en te gebruiken moeten `HTTPS` eindpunten gebruiken.