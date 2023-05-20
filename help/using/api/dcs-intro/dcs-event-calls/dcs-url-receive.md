---
description: Ga hier voor informatie over hoe te om om een reactie DCS in een /event vraag te verzoeken. Deze sectie omvat een reactievoorbeeld en definities voor gemeenschappelijke gegevenselementen in een reactie.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Data ontvangen van de DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 2%

---

# Data ontvangen van de DCS {#receive-data-from-the-dcs}

Doorgaan hier voor informatie over hoe u een [!DNL DCS] reactie in een `/event` vraag. Deze sectie omvat een reactievoorbeeld en definities voor gemeenschappelijke gegevenselementen in een reactie.

Voordat u deze inhoud gaat controleren, raadpleegt u [Gegevens verzenden naar de DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## DCS-responsparameters: Een revisie {#dcs-response-parameters}

Uw [!DNL DCS] verzoek moet `d_rtbd=json` als u een antwoord van [!DNL DCS]. De [!DNL DCS] gegevens worden niet geretourneerd als u deze parameter weglaat. Een elementaire oproep aan de [!DNL DCS] om gegevens aan te vragen gebruikt u deze syntaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Samplereactie {#sample-response}

Herinneren aan de [Gegevens verzenden naar de DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentatie, de fictieve vennootschap [!DNL Acme, Inc.] deed deze oproep :

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Aangezien deze vraag de vereiste reactieparameter omvat, [!DNL DCS] de [!DNL JSON] hieronder weergegeven object. U kunt gelijkaardig of complexer zijn.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Responsparameters {#response-parameters}

De onderstaande tabel bevat een overzicht en definitie van de meer algemene parameters die u kunt zien in een reactie op het dialoogvenster [!DNL DCS]. Dit is van toepassing op gebeurtenisaanroepen of andere [!DNL DCS] [!DNL API] query&#39;s die gegevens retourneren.

| Parameter | Beschrijving |
|--- |--- |
| `c` | Een URL die is ingesteld als een [URL-doel](../../../features/destinations/create-url-destination.md). |
| `cn` | De naam of id die is ingesteld in het veld met de cookienaam van een [cookie bestemming](../../../features/destinations/create-cookie-destination.md). |
| `cv` | De waarden die naar het doel worden verzonden dat door de parameter &quot;cn&quot;:&quot;(doelnaam) wordt gedefinieerd. |
| `dcs_region` | De [server-aan-server DCS vraag](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dit object bevat informatie voor alle URL-doelen die in de gebruikersinterface zijn geconfigureerd. De lijst van dit object is dynamisch op basis van de acties van de gebruiker. |
| `dmn` | Dit is het domein dat is opgegeven in het veld Cookie-domein voor een cookie-bestemming. Zie [Optionele instellingen voor Cookie-doelen](../../../features/destinations/cookie-destination-options.md).  Voor Server aan de integratie van de Server adviseren wij gebruikend een domein als `aam-api.com`. |
| `e` | De beveiligde URL die is ingesteld in een URL-doel. |
| `stuff` | Dit object bevat informatie voor alle Cookie-doelen. De lijst van dit object is dynamisch op basis van de acties van de gebruiker. |
| `tid` | Transactie-id. Dit is een unieke id van 12 tekens die wordt gebruikt voor foutopsporingsdoeleinden. Elke /event vraag aan DCS ontvangt een tid die u in steunonderzoeken voor een betere en snellere reactie kunt van verwijzingen voorzien. |
| `ttl` | De tijd-tot-live waarde van het cookie in dagen. |
| `u` en `uuid` | Unieke gebruikersnaam toegewezen door Audience Manager. Dit is vereist als u maakt [server-aan-server DCS vraag](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md). |
| `y` | Doeltype, iFrame (`iframe`) of afbeelding (`img`). |

>[!MORELIKETHIS]
>
>* [Belangrijke voorvoegsels en variabelen die door DCS worden ondersteund](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)

