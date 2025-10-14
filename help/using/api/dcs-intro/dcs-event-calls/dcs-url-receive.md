---
description: Ga hier voor informatie over hoe te om om een reactie DCS in een /event vraag te verzoeken. Deze sectie omvat een reactievoorbeeld en definities voor gemeenschappelijke gegevenselementen in een reactie.
seo-description: Continue here for information about how to request a DCS response in a /event call. This section includes a response example and definitions for common data elements in a response.
seo-title: Receive Data From the DCS
solution: Audience Manager
title: Gegevens ontvangen van de DCS
uuid: fbb77197-8530-48a8-b708-d785f7214494
feature: DCS
exl-id: c6a87e5a-63cc-44d7-b6f0-ac8ee845fd00
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Gegevens ontvangen van de DCS {#receive-data-from-the-dcs}

Ga hier verder voor informatie over het aanvragen van een [!DNL DCS] reactie in een `/event` oproep. Deze sectie omvat een reactievoorbeeld en definities voor gemeenschappelijke gegevenselementen in een reactie.

Alvorens deze inhoud te herzien, zie [&#x200B; Gegevens naar DCS &#x200B;](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) verzenden.

## DCS-responsparameters: een revisie {#dcs-response-parameters}

Uw [!DNL DCS] -aanvraag moet `d_rtbd=json` bevatten als u een antwoord van de [!DNL DCS] wilt ontvangen. De [!DNL DCS] retourneert geen gegevens als u deze parameter weglaat. Een basisaanroep van de [!DNL DCS] om gegevens aan te vragen, gebruikt deze syntaxis:

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

## Samplereactie {#sample-response}

Herinnering dat van [&#x200B; Gegevens naar de DCS &#x200B;](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md) documentatie verzendt, maakte het fictieve bedrijf [!DNL Acme, Inc.] deze vraag:

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

Aangezien deze aanroep de vereiste responsparameter bevat, wordt het [!DNL DCS] -object dat hieronder wordt weergegeven, teruggestuurd. [!DNL JSON] U kunt gelijkaardig of complexer zijn.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Responsparameters {#response-parameters}

De onderstaande tabel bevat een lijst met en definieert de meer algemene parameters die u kunt zien in een reactie van de [!DNL DCS] . Dit geldt voor gebeurtenisaanroepen of andere [!DNL DCS] [!DNL API] -query&#39;s die gegevens retourneren.

| Parameter | Beschrijving |
|--- |--- |
| `c` | Een URL die als a [&#x200B; bestemming URL &#x200B;](../../../features/destinations/create-url-destination.md) is geplaatst. |
| `cn` | De naam of identiteitskaart die op het gebied van de koekjesnaam van a [&#x200B; wordt geplaatst koekjesbestemming &#x200B;](../../../features/destinations/create-cookie-destination.md). |
| `cv` | De waarden die naar het doel worden verzonden dat door de parameter &quot;cn&quot;:&quot;(doelnaam) wordt gedefinieerd. |
| `dcs_region` | De [&#x200B; server-aan-server DCS vraag &#x200B;](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md). |
| `dests` | Dit object bevat informatie voor alle URL-doelen die in de gebruikersinterface zijn geconfigureerd. De lijst van dit object is dynamisch op basis van de acties van de gebruiker. |
| `dmn` | Dit is het domein dat is opgegeven in het veld Cookie-domein voor een cookie-bestemming. Zie [&#x200B; Facultatieve Montages voor de Doelen van het Koekje &#x200B;](../../../features/destinations/cookie-destination-options.md).  Voor Server-naar-server-integratie raden we u aan een domein als `aam-api.com` te gebruiken. |
| `e` | De beveiligde URL die is ingesteld in een URL-doel. |
| `stuff` | Dit object bevat informatie voor alle Cookie-doelen. De lijst van dit object is dynamisch op basis van de acties van de gebruiker. |
| `tid` | Transactie-id. Dit is een unieke id van 12 tekens die wordt gebruikt voor foutopsporingsdoeleinden. Elke /event vraag aan DCS ontvangt een tid die u in steunonderzoeken voor een betere en snellere reactie kunt van verwijzingen voorzien. |
| `ttl` | De tijd-tot-live waarde van het cookie in dagen. |
| `u` en `uuid` | Unieke gebruikersnaam toegewezen door Audience Manager. Dit wordt vereist als u [&#x200B; server-aan-server DCS vraag &#x200B;](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md) maakt. |
| `y` | Doeltype, iFrame (`iframe`) of afbeelding (`img`). |

>[!MORELIKETHIS]
>
>* [&#x200B; zeer belangrijk-Waarde prefixen en Variabelen die door DCS &#x200B;](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md) worden gesteund
